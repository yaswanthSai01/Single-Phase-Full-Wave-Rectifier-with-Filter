# ⚡ Single-Phase Full-Wave Rectifier with Capacitor Filter

## 🧩 1. Overview

This project demonstrates a **single-phase, center-tapped, full-wave rectifier with a capacitor filter**, a fundamental power electronics circuit.  
The circuit was **designed and simulated in Multisim**.

### 🎯 Objective
To convert a **120 Vrms, 60 Hz AC input** (wall outlet simulation) into a **smooth, stable, low-voltage DC output** using rectification and filtering.

---

## 🔌 2. Circuit Diagram and Components

### 🧱 Circuit with Filter

| Component | Description |
|:-----------|:-------------|
| **V1** | 120 Vrms, 60 Hz AC source |
| **T1** | Center-tapped transformer (100:5:5 turns ratio → 20:1 step-down per secondary) |
| **D1, D2** | 1N4007G diodes |
| **C1** | 5 μF capacitor (filter) |
| **R1** | 100 kΩ load resistor |
| **XSC1** | Oscilloscope (Channel A: transformer secondary, Channel B: load output) |

---

## ⚙️ 3. Circuit Operation

The conversion from **AC → DC** occurs in two stages:

### 🔁 **A. Rectification (Without Filter)**
Converts the AC waveform into **pulsating DC**.

1. **Transformer:** Steps 120 Vrms down to ~6 Vrms on each secondary.
2. **Positive Half-Cycle:**  
   - Top secondary = positive  
   - **D1** conducts, **D2** blocks  
   - Current flows through D1 → Load  
3. **Negative Half-Cycle:**  
   - Bottom secondary = positive  
   - **D2** conducts, **D1** blocks  
   - Current flows through D2 → Load (same direction)  

🔸 Result: Both halves of the AC waveform produce positive pulses — a **full-wave rectified** signal.

---

### ⚡ **B. Filtering (With Capacitor)**
Smooths the pulsating DC using a capacitor.

- **Capacitor Placement:** C1 (5 μF) is connected in parallel with the load (R1).  
- **Charging:** During each voltage peak, C1 charges up to the peak voltage (~7.9 V).  
- **Discharging:** As input voltage drops, diodes turn OFF and C1 slowly discharges through R1, maintaining voltage.  
- **Cycle:** Each new peak recharges the capacitor, reducing ripple and stabilizing output.

---

## 📈 4. Simulation Results and Waveforms

### 🧪 **Case 1: Without Filter**
Circuit simulated with only the load resistor (R1) to visualize pure rectification.

- **Channel A (Red):** Secondary AC waveform (~8.5 V peak).  
- **Channel B (Blue):** Full-wave rectified output — a series of positive bumps dropping to 0 V twice per cycle (120 Hz ripple).

![Oscilloscope Output Without Filter](Oscilloscope%20Output%20Without%20Filter.png)

---

### 🔋 **Case 2: With Filter**
After adding the 5 μF capacitor filter:

- **Channel A (Red):** Same AC input.  
- **Channel B (Blue):** Filtered DC output — smooth and stable around **7.91 V**, with minimal ripple.

![Oscilloscope Output With Filter](Oscilloscope%20Output%20With%20Filter.png)

---

## ✅ 5. Conclusion

This **Multisim simulation** successfully demonstrates **AC-to-DC conversion** using a center-tapped, two-diode **full-wave rectifier** with a **capacitor filter**.  

Key Results:
- **Unfiltered output:** Pulsating DC with high ripple.  
- **Filtered output:** Smooth DC of approximately **7.9 V**.  

> The circuit effectively converts a 120 Vrms AC input into a clean DC output, suitable for powering low-voltage electronic devices.

---

### 🧰 Tools Used
- NI Multisim 14.x  
- Oscilloscope for waveform analysis  

---

### 🧑‍💻 Author
**Kotyada Yaswanth Sai**  
B.Tech Electrical Engineering, NIT Rourkela  
