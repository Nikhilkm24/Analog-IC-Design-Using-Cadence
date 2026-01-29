# Common Source (CS) Amplifier with PMOS Active Load

> Designed and verified using **Cadence Virtuoso**  
> Analyses performed: **DC, Transient, and AC**

---

##  Objective

The objective of this design is to implement and verify a **Common Source (CS) amplifier** using an **NMOS transistor with a PMOS active load**.  
The experiment focuses on:

- Establishing a correct **DC operating point**
- Ensuring **saturation operation** of both MOSFETs
- Verifying **voltage amplification and phase inversion**
- Extracting **small-signal gain** using AC analysis

This circuit represents a **fundamental gain stage** used in most analog ICs.

---

##  Circuit Description

### Topology
- **NMOS (NM0)** configured in common source
- **PMOS (PM0)** used as an active load (current source)
- **Input (Vin)** applied to the gate of NMOS
- **Output (Vout)** taken at the drain of NMOS
- PMOS source connected to **VDD**
- NMOS source connected to **GND**

  This topology is widely used in:
- Operational amplifiers
- Bandgap reference circuits
- Analog signal conditioning blocks

---

##  Why CS Amplifier with PMOS Active Load?

- Provides **high voltage gain**
- PMOS active load offers **high output resistance**
- Requires **less silicon area** than resistive loads
- Suitable for **low-voltage CMOS technologies**
- Forms the basic building block for multistage analog amplifiers

---

##  DC Analysis (Bias Point Design)

### Purpose of DC Analysis
DC analysis is critical to:
- Set the **operating point (Q-point)**
- Ensure both NMOS and PMOS are in **saturation**
- Place the output voltage near **mid-supply** for maximum swing

> Without proper DC biasing, AC and transient results are invalid.

---

### Initial DC Observation
After annotating the schematic:
- PMOS drain-to-source voltage  
  **VDS ≈ −596 mV** (initial)

This operating point does not provide optimal output swing.

 **Target condition:**
- |VDS(PMOS)| ≈ 500 mV  
- |VDS(NMOS)| ≈ 500 mV  

This ensures both devices remain in saturation during signal variations.

---

##  Parametric DC Sweep (PMOS Width Optimization)

To achieve the desired operating point, a **parametric analysis** was performed by sweeping the PMOS width (**W2**):

- Sweep range: **120 nm → 2 µm**

### Observations
- Increasing PMOS width increases drain current
- Output node voltage (Vout) shifts accordingly

### Final Result
- At **W2 ≈ 924.4 nm**
- **VDS(PMOS) ≈ −500.143 mV**

  This confirms:
- Proper current matching
- Saturation operation of both transistors
- Stable and optimal DC bias point

---

##  Transient Analysis

### Purpose
Transient analysis is used to verify:
- Time-domain amplification
- Phase relationship between input and output
- Absence of clipping or distortion

### Observations
- A sinusoidal input (Vin) is applied
- Output (Vout) shows:
  - Increased amplitude
  - **180° phase inversion**

This confirms correct **Common Source amplifier behavior**.

---

##  AC Analysis (Small-Signal Frequency Response)

### Purpose
AC analysis evaluates:
- Small-signal voltage gain
- Frequency response
- Effect of parasitic capacitances

### Results
- **Midband gain ≈ 6.7 V/V**
- Flat response at low and mid frequencies
- Gain roll-off at higher frequencies

Theoretical relation:

\[
A_v \approx -g_m \cdot (r_{o,n} \parallel r_{o,p})
\]

The obtained gain closely matches theoretical expectations.

---

##  Verification Checklist

### DC Verification
- VDS(NMOS) > VOV,NMOS
- |VDS(PMOS)| > |VOV,PMOS|
- Output voltage near mid-supply

### Transient Verification
- Clean sinusoidal output
- No clipping or distortion
- 180° phase inversion

### AC Verification
- Realistic midband gain
- Flat frequency response
- Expected high-frequency roll-off

✔️ All checks were successfully satisfied.

---

##  Key Learnings

- DC biasing defines amplifier performance
- PMOS width is a critical design parameter
- Saturation operation is mandatory for analog amplification
- DC, transient, and AC analyses together validate a design

---

##  Conclusion

A **Common Source amplifier with PMOS active load** was successfully designed and verified in Cadence Virtuoso. Proper DC biasing was achieved using parametric width optimization, transient analysis confirmed voltage amplification with phase inversion, and AC analysis validated the small-signal gain. This circuit serves as a foundational gain stage for advanced analog IC designs.

---
