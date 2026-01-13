# Project Technical Report: Real-Time Attitude Indicator

## 1. System Overview

This project implements a digital flight instrument system (Glass Cockpit) consisting of two main subsystems:

- **Embedded Flight Controller (Firmware):** Runs on an STM32 Nucleo-F446RE. It acquires raw data from an MPU6050 IMU and a Magnetometer, performs sensor fusion, and transmits calculated flight attitude data via UART.
- **Flight Display (GUI):** A web-based application utilizing the Web Serial API to receive live telemetry and render a Primary Flight Display (PFD) using HTML5 Canvas.

---

## 2. Firmware Architecture (STM32 Code Analysis)

The firmware is written in C using the HAL (Hardware Abstraction Layer) library. The core logic operates in a continuous `while(1)` loop with a refresh rate of approximately 50Hz.

### 2.1 Sensor Initialization & Communication

- **Communication Protocol:** The system uses I2C1 (fast mode, 100kHz) to communicate with sensors.
- **MPU6050 (IMU):** Initialized at address `0xD0`. The code wakes the sensor from sleep mode and sets the sample rate divider. It reads 14 bytes of raw data sequentially to acquire Accelerometer (X, Y, Z) and Gyroscope (X, Y, Z) readings.
- **Magnetometer:** Initialized at address `0x58` (0x2C << 1). It is configured for continuous measurement mode (200Hz, 8G range). The code handles the specific little-endian data format required by this sensor.

### 2.2 Data Processing & Sensor Fusion

Raw sensor data is noisy and subject to drift. The firmware implements signal processing to ensure stable readings:

- **Unit Conversion:** Raw integer values are converted to physical units (g-force for accelerometers, deg/sec for gyroscopes) using sensitivity scale factors (e.g., `/ 16384.0f` for accel).
- **Pitch & Roll Calculation:**
    
    - _Accelerometer:_ Calculates absolute angles using trigonometry (`atan2f`). This provides a stable reference but is susceptible to vibration.
    - _Gyroscope:_ Integrates angular velocity (`Gx * dt`) to estimate angle changes over time. This is smooth but drifts over time.
    - Complementary Filter: The system fuses these two sources using the formula:
        $$Angle = 0.96 \times (Gyro) + 0.04 \times (Accel)$$
        
        This effectively filters out high-frequency noise from the accelerometer while correcting the long-term drift of the gyroscope.

### 2.3 Telemetry Transmission

The processed data is formatted into a JSON string for easy parsing by the GUI.

- **Format:** `{"p": [Pitch], "r": [Roll], "rr": [RollRate], "h": [Heading]}`
- **Interface:** UART2 is used at a baud rate of **115200 bps**.
- **Timing:** Data is transmitted every ~20ms, ensuring a smooth frame rate on the display.

---

## 3. Graphical User Interface (GUI) Architecture

The interface is a single-page HTML application (`final_ai.htm`) that acts as a ground station display. It uses modern browser features to render high-frequency graphics without external software.

### 3.1 Serial Connectivity (Web Serial API)

Unlike traditional methods requiring a bridge application, this project connects directly to the COM port via the browser:

- **Connection Handshake:** The `navigator.serial.requestPort()` function opens a secure connection to the Nucleo board at 115200 baud.
- **Stream Reader:** An asynchronous loop (`readSerialLoop`) continuously reads the incoming byte stream, reassembles it into lines, and parses the JSON packets.

### 3.2 Smoothing & Data Handling

To prevent "jitter" in the animation, the GUI applies a secondary Low-Pass Filter (LPF) to the incoming data:

- **Smoothing Factor:** Set to `0.15`.
- **Logic:** `CurrentVal = (NewVal * 0.15) + (OldVal * 0.85)`
- **Heading Wrap Fix:** Special logic is included to handle the 0°/360° crossover, ensuring the compass doesn't spin wildly when crossing North.

### 3.3 Visualization (HTML5 Canvas)

The display is drawn using the 2D Canvas API, updated every frame via `requestAnimationFrame` for smooth performance (60fps).

- **Attitude Indicator (Artificial Horizon):**
    - Translates and rotates the entire canvas context based on the **Roll** and **Pitch** values.
    - Draws the sky (blue) and ground (brown) rectangles, keeping the horizon line level relative to the "virtual" earth.
    - Overlays a pitch ladder (white lines) that moves vertically to indicate climb or dive.
- **Heading Indicator:** A scrolling tape at the bottom of the screen displays the magnetic heading
- **Roll Rate & Angle:** Digital readouts provided in boxes at the top left and right corners

---

## 4. System Interconnection Summary

1. **Acquisition:** STM32 reads raw I2C data from sensors.
2. **Processing:** STM32 applies Complementary Filter to compute Pitch/Roll.
3. **Transmission:** STM32 sends JSON string via USB-UART (`{"p":...}`).
4. **Reception:** Browser (Chrome/Edge) reads Serial stream and parses JSON.
5. **Rendering:** JavaScript updates the Canvas graphics to reflect the new orientation.

---
