## C code explanation (stm cube IDE)

### **1. System Overview**

This firmware implements an **Attitude and Heading Reference System (AHRS)** on an STM32F446RE Nucleo board. It interfaces with two primary sensors via the I2C bus to determine the orientation of the vehicle in 3D space:

- **MPU6050:** A 6-axis Inertial Measurement Unit (IMU) providing Accelerometer and Gyroscope data.
- **QMC5883L (or compatible clone):** A 3-axis Magnetometer providing compass heading data.

The system fuses these sensor inputs to calculate **Pitch**, **Roll**, and **Yaw (Heading)** and streams the telemetry via UART in JSON format.

---

### **2. Communication Protocol & Hardware Interface**

The sensors communicate with the microcontroller over the **I2C1** bus (Inter-Integrated Circuit).

- **Bus Speed:** configured to Standard Mode (100 kHz).
- **Addressing:**
    - **MPU6050:** Address `0xD0` (7-bit `0x68` shifted left by 1).
    - **Magnetometer:** Address `0x58` (7-bit `0x2C` shifted left by 1).

> **Note on HAL Addressing:** The STM32 HAL library requires the 8-bit I2C address (which includes the Read/Write bit position). Therefore, the standard 7-bit addresses are left-shifted by 1 bit in the definitions.

---

### **3. Sensor Initialization Phase**

Before the main loop begins, the system configures the sensors to ensure correct data output rates and ranges.

#### **3.1 MPU6050 Configuration**

The `MPU6050_Init` function performs the following steps:

1. **ID Check:** Reads the `WHO_AM_I` register (`0x75`) to verify the device ID is `0x68`.
2. **Power Management:** Writes `0x00` to the Power Management 1 register (`0x6B`) to wake the sensor from sleep mode.
3. **Sample Rate:** Writes `0x07` to the SMPLRT_DIV register (`0x19`), setting the gyroscope output rate to 1 kHz.

#### **3.2 Magnetometer Configuration**

The `Magnetometer_Init` function configures the QMC sensor (often found on GY-271 modules):

1. **Soft Reset:** Writes `0x01` to Register `0x0B` to reset the period/set pointer.
2. **Control Register 1:** Writes `0x0D` to Register `0x0A`. This configures the sensor for:
    - **Continuous Measurement Mode**
    - **Output Data Rate:** 200 Hz
    - **Range:** 8 Gauss
    - **Over Sampling Ratio:** 512

---

### **4. Data Acquisition Strategy**

The `Read_Sensors` function handles the retrieval of raw data, managing the different "Endianness" (byte order) of the two sensors.

- **MPU6050 (Big Endian):**
    - A burst read of **14 bytes** is performed starting at register `0x3B`.
    - Data includes Accel (X,Y,Z), Temperature, and Gyro (X,Y,Z).
    - The High Byte is received first. The code constructs the 16-bit integer using: `(HighByte << 8) | LowByte`.
    - **Scaling:** Raw values are divided by their sensitivity factors (`16384.0` for Accelerometer, `131.0` for Gyroscope) to convert them into units of **g** and **degrees/second**.
- **Magnetometer (Little Endian):**
    - A burst read of **6 bytes** is performed starting at register `0x00`.
    - The Low Byte is received first (typical for QMC sensors).
    - The code constructs the 16-bit integer using: `LowByte | (HighByte << 8)`.

---

### **5. Signal Processing & Sensor Fusion**

This is the core algorithm determining the aircraft's attitude.

#### **5.1 Accelerometer Attitude Calculation**

The code calculates the pitch and roll angles based on the gravity vector detected by the accelerometer.

$$\text{Pitch}_{acc} = \arctan2(A_y, \sqrt{A_x^2 + A_z^2}) \times \frac{180}{\pi}$$

$$\text{Roll}_{acc} = \arctan2(-A_x, A_z) \times \frac{180}{\pi}$$

- **Limitation:** Accelerometers are noisy and susceptible to vibration and lateral acceleration. They are only accurate when the system is static.

#### **5.2 Complementary Filter**

To mitigate accelerometer noise and gyroscope drift, a **Complementary Filter** is implemented. It combines the short-term accuracy of the gyroscope with the long-term stability of the accelerometer.

The formula used in the code is:

$$\theta_{new} = 0.96 \times (\theta_{old} + \text{GyroRate} \times dt) + 0.04 \times \theta_{acc}$$

- **0.96 (High Pass):** Trusts the Gyro integration for fast movements.
- **0.04 (Low Pass):** Slowly corrects the Gyro drift using the Accelerometer gravity vector.
- **`dt`:** The delta time between loop iterations, calculated using `HAL_GetTick()`, ensuring accurate integration regardless of loop execution speed.

#### **5.3 Heading Calculation**

The heading is calculated using the Magnetometer's X and Y axes:

$$\text{Heading} = \arctan2(Mag_Y, Mag_X) \times \frac{180}{\pi}$$

The result is normalized to a 0–360° range.

- _Note:_ The current implementation uses a "2D" heading calculation. If the sensor tilts (pitch/roll is not zero), the heading will drift. A robust flight controller typically implements "Tilt Compensation" here using the calculated Pitch and Roll to rotate the Magnetometer vector back to the horizontal plane.

---

### **6. Output Telemetry**

The system outputs the processed data via UART2 (connected to the ST-Link Virtual COM port) at **115200 baud**.

- **Format:** JSON (JavaScript Object Notation).
- **Structure:** `{"p": pitch, "r": roll, "rr": roll_rate, "h": heading}`
- **Frequency:** The loop includes a `HAL_Delay(20)`, resulting in an update rate of approximately **50 Hz**.

This JSON format allows for easy parsing by external visualization tools (like Serial Plotter, Python scripts, or Mission Planner ground stations).

## terms and concepts

### communication protocols

#### I2C

**I2C (Inter-Integrated Circuit)** is a synchronous, multi-master, multi-slave serial communication protocol that operates using only two lines: serial data (SDA) and serial clock (SCL). The master device generates the clock and initiates communication, while each slave is identified by a unique address. Data transfer occurs in packets with addressing and acknowledgment mechanisms, supporting multiple devices with minimal wiring—making I2C very popular for connecting various sensors, memory chips, and peripherals to microcontrollers in embedded systems.​

#### USART

**USART (commonly used as UART—Universal Asynchronous Receiver/Transmitter)** is an asynchronous, point-to-point serial communication protocol that uses two lines: transmit (Tx) and receive (Rx). Unlike I2C, UART communication does not require a shared clock; instead, both devices agree on a fixed baud rate. Data transmission involves encapsulating payloads with start and stop bits for synchronization. UART is favored for simple, direct data exchange between two devices, such as microcontroller debugging, GPS modules, or serial communication with computers.​

### web serial API

The Web Serial API provides a mechanism for websites to interact with serial devices connected to a user's computer, such as microcontrollers, 3D printers, and other serial-based hardware. This API bridges the gap between web applications and the physical world by enabling communication over a serial port.

### hardware abstraction layer (HAL)

A [Hardware Abstraction Layer](https://www.google.com/search?q=Hardware+Abstraction+Layer&sca_esv=0b1bbd70689b2a31&sxsrf=AE3TifNOeVWMqJsDATA53fIQHdYbp9ZZqA%3A1761801118563&ei=nvMCafmMIpL2seMPn6jvwQo&oq=hardware+ab&gs_lp=Egxnd3Mtd2l6LXNlcnAiC2hhcmR3YXJlIGFiKgIIADIFEAAYgAQyChAAGIAEGBQYhwIyBRAAGIAEMgUQABiABDIFEAAYgAQyCxAuGIAEGMcBGK8BMgUQABiABDIFEAAYgAQyBRAAGIAEMgUQABiABEiMGFDrBljBEnADeAGQAQCYAYYBoAHACaoBAzQuN7gBA8gBAPgBAZgCDqAC8AnCAgoQABiwAxjWBBhHwgIKECMYgAQYJxiKBcICBBAjGCfCAgsQABiABBiRAhiKBcICEBAAGIAEGLEDGEMYgwEYigXCAgoQABiABBhDGIoFwgILEAAYgAQYsQMYgwHCAhEQLhiABBixAxjRAxiDARjHAcICEBAjGPAFGIAEGCcYyQIYigXCAhYQLhiABBixAxjRAxhDGIMBGMcBGIoFwgIQEC4YgAQY0QMYQxjHARiKBcICDRAAGIAEGLEDGEMYigXCAggQLhiABBixA8ICCxAuGIAEGLEDGNQCwgINEAAYgAQYsQMYFBiHAsICCBAAGIAEGMkDwgILEAAYgAQYkgMYigXCAggQABiABBixA8ICDRAAGIAEGEMYyQMYigWYAwCIBgGQBgiSBwM1LjmgB7hksgcDMi45uAfnCcIHBjAuMTAuNMgHIw&sclient=gws-wiz-serp&ved=2ahUKEwjU2rTTlMuQAxUvRmwGHbz7KFQQgK4QegYIAAgAEAU) (HAL) is ==a software layer that acts as an interface between a computer's hardware and its operating system or other software==. It hides the low-level, device-specific details of the hardware from the rest of the software, allowing developers to write programs that are portable across different hardware configurations. A HAL provides a standardized set of functions and protocols, simplifying communication and saving development time.

---
