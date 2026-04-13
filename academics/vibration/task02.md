### **Technical Report: Mitigating Integration Drift in Accelerometer Data**

**1. Objective**

To accurately derive velocity and displacement time-series data from raw experimental acceleration data (e.g., from a drone's IMU) by mitigating the severe drift errors inherent in numerical integration.

**2. Problem Statement**

When deriving kinematic data, velocity is the integral of acceleration, and displacement is the integral of velocity:

$v(t) = \int a(t) dt + C_1$

$d(t) = \int v(t) dt + C_2$

In discrete numerical integration, raw sensor noise, low-frequency biases, and the static gravity vector ($9.81$ m/s²) act as the integration constants ($C$). This causes a snowball effect: a constant error in acceleration results in a linear drift in velocity, which compounds into an exponential/quadratic drift in displacement, rendering the final data unusable.

**3. Methodology: The "Clean-Integrate-Clean" Pipeline**

To resolve this, the analysis employs a sequential zero-phase filtering technique to eliminate low-frequency drift at each integration step.

- **Step 1: Mean Removal (Detrending).** The static mean of the raw acceleration data is subtracted. This explicitly removes the gravity vector and constant sensor biases, centering the signal at zero.
    
- **Step 2: First Integration.** Acceleration is integrated into velocity using the cumulative trapezoidal rule.
    
- **Step 3: High-Pass Filtering (Zero-Phase).** A high-pass filter is applied to the velocity data. The cutoff frequency (e.g., $2$ Hz) is chosen to be strictly below the system's lowest structural resonant frequency. This removes the linear integration drift. **Crucially**, the filter is applied both forward and backward in time (zero-phase filtering) to prevent any phase delay, ensuring peaks and valleys remain temporally synchronized.
    
- **Step 4: Second Integration.** The cleaned velocity is integrated into displacement.
    
- **Step 5: Final Filtering.** The displacement data undergoes the same zero-phase high-pass filter to remove the secondary integration drift.
    

**4. Implementation Details**

The method is implemented in Python, utilizing open-source libraries to bypass proprietary software limitations (such as MATLAB toolboxes):

- **Data Handling:** `pandas` and `numpy` are used for extracting and manipulating the time-series arrays.
    
- **Integration:** `scipy.integrate.cumulative_trapezoid` performs the numerical integration.
    
- **Filtering:** `scipy.signal.butter` is used to design a 4th-order Butterworth high-pass filter. `scipy.signal.filtfilt` executes the forward-backward zero-phase filtering.
    

**5. Conclusion**

The Filter-Integrate-Filter method successfully isolates dynamic structural vibrations from static biases and mathematical drift. By utilizing a zero-phase high-pass filter, the integrity of the signal's time-domain amplitude and phase is preserved, yielding highly accurate displacement data suitable for downstream modal analysis and frequency profiling.

---
