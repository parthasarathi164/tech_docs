>This report summarizes our technical discussion on the challenges of **double integration** in inertial navigation and vibration engineering—a critical hurdle for your aerospace project.

---

## **Technical Report: Inertial Data Integration & The Drift Phenomenon**

### **1. Executive Summary**

While the mathematical relationship between acceleration ($a$), velocity ($v$), and displacement ($d$) is a simple derivative chain, the **inverse** (integration) is computationally "unstable" when using real-world sensors. Small errors at the acceleration level do not stay small; they grow over time, leading to a phenomenon known as **Sensor Drift**.

### **2. The Mathematical Problem: Error Propagation**

In a vibrating system, an accelerometer produces a signal containing the true motion plus a tiny amount of **Bias** ($\epsilon$).

- **First Integration (Velocity):** The bias is integrated over time ($t$), creating a **Linear Error**.
    
    $$v(t) = \int (a_{true} + \epsilon) dt = v_{true} + \epsilon t$$
    
- **Second Integration (Displacement):** The linear error is integrated again, creating a **Quadratic Error**.
    
    $$d(t) = \int (v_{true} + \epsilon t) dt = d_{true} + \frac{1}{2}\epsilon t^2$$
    

### **3. Analysis of the Implementation (The Code)**

The Python implementation we used relies on **Numerical Integration** via the `scipy.integrate.cumulative_trapezoid` function.

**How the Code Logic Works:**

1. **Sampling:** The code takes discrete data points at a specific frequency ($f_s$).
    
2. **Trapezoidal Rule:** Instead of simple rectangular sums, it calculates the area of a trapezoid between two points: $\text{Area} = \frac{(a_1 + a_2)}{2} \cdot \Delta t$. This is more accurate for curved signals like vibrations.
    
3. **Accumulation:** It performs a "Running Sum." Each new area calculated is added to the previous total.
    
4. **The Result:** Even with real IMU data (where $a \approx 0$), the tiny non-zero average in the "Raw Accel" leads to a velocity graph that slopes upward and a displacement graph that curves away exponentially.
    

---

### **4. Addressing the Integration Constant ($C$)**

The integration constant represents the **Initial Conditions** of the system. In your quadcopter project, you cannot ignore them.

|**Constant**|**Physical Meaning**|**Engineering Solution**|
|---|---|---|
|**$C_1$ (Velocity)**|Initial Speed ($v_0$)|**Zeroing:** Calibrate the drone while stationary to force $v_0 = 0$.|
|**$C_2$ (Position)**|Initial Position ($d_0$)|**Reference Point:** Set the "Home" coordinate (GPS or local origin).|

**What to do with $C$ in practice:**

- **For Vibration Analysis:** We usually don't care about the absolute position ($C$), only the "wiggles." We use a **High-Pass Filter** to mathematically remove the DC component (which is essentially the constant $C$), forcing the signal to always return to zero.
    
- **For Navigation:** Since we need the absolute position, we use **Sensor Fusion (Kalman Filtering)**. We use a second sensor (like GPS) to "reset" the constants periodically so the accelerometer drift doesn't accumulate indefinitely.
    

---

### **5. Concluding Recommendations**

For your flight controller project, never rely on raw integration for position. Your pipeline should follow this order:

1. **Calibrate** the IMU to find and subtract the Bias ($\epsilon$).
    
2. **Filter** the acceleration using a Band-Pass or High-Pass filter to remove low-frequency drift.
    
3. **Integrate** using the Trapezoidal rule for short-term estimates.
    
4. **Correct** the result using a global reference (GPS/Barometer) via a Kalman Filter.

---

