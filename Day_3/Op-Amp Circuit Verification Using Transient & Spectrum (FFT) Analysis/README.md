# Op-Amp Based Circuit Verification Using Transient and Spectrum Analysis

> Tool: Cadence Virtuoso (Spectre APS)  
> Analysis Tools: Transient Analysis, Calculator, Spectrum (FFT)  
> Objective: Signal integrity and noise verification

---

##  Objective

The objective of this experiment is to analyze and verify the behavior of an op-amp based circuit using:

- Time-domain (Transient) analysis
- Frequency-domain (Spectrum / FFT) analysis using the Calculator tool

The goal is to confirm that:
- The output signal faithfully follows the input signal
- Only the intended frequency components are present
- Noise and unwanted harmonics are within acceptable limits

---

##  Circuit Description

The circuit consists of:
- An op-amp (inbuilt gpdk045 model)
- External biasing and feedback network
- Differential and bias inputs
- Single-ended output

The op-amp is operated in its **linear region using negative feedback**, ensuring predictable amplification and stability.

---

### Schematic

![Op-Amp Circuit](schematic.png)

*Figure 1: Op-amp based circuit used for transient and spectrum analysis.*

---

##  Transient Analysis

### Purpose
Transient analysis is performed to:
- Observe time-domain waveforms
- Verify amplification behavior
- Ensure no clipping or distortion

---

### Transient Response

![Transient Response](transient_fft.png)

*Figure 2: Transient waveforms of input and output signals.*

### Observations
- Input signal is a sinusoidal waveform at **1 kHz**
- Output signal is amplified and stable
- No clipping or distortion observed
- DC operating point is correctly set

This confirms correct **biasing and closed-loop operation** of the op-amp.

---

##  Spectrum (FFT) Analysis Using Calculator

### Why Spectrum Analysis Is Needed

While transient analysis shows waveform shape, it does **not reveal frequency purity**.  
Spectrum (FFT) analysis is used to:
- Identify frequency components
- Detect harmonics and noise
- Quantify signal purity

This is critical in:
- Analog front-end circuits
- ADC driver stages
- Precision amplifiers

---

### FFT Setup
- FFT computed using **Calculator**
- Signals analyzed:
  - Input (`Vinp`)
  - Output (`Vout`)
- Frequency range up to several kHz

---

### Spectrum Results

From the FFT plots:

- **DC Component (0 Hz)**  
  - Present due to DC bias  
  - Expected and correct (DC has no frequency)

- **AC Component at 1 kHz**  
  - Dominant frequency component  
  - Matches the applied input signal frequency

- **Noise Floor**  
  - All other frequency components are below **−80 dB**
  - Indicates low noise and minimal harmonic distortion

---

### Key Observation Summary

| Component | Observation |
|---------|-------------|
| DC (0 Hz) | Present due to biasing |
| Signal Frequency | Clear peak at **1 kHz** |
| Harmonics | Negligible |
| Noise Floor | Below **−80 dB** |
| Signal Integrity | Acceptable by design standards |

---

##  Acceptance Criteria

According to common analog design guidelines:
- Noise below **−60 dB** is generally acceptable
- Noise below **−80 dB** indicates **good signal integrity**

✔ The circuit meets and exceeds standard requirements.

---

##  Key Learnings

- Transient analysis confirms time-domain correctness
- Spectrum analysis validates frequency-domain behavior
- DC bias appears as a 0 Hz component
- FFT is essential to detect hidden noise and harmonics
- Calculator tool enables advanced signal validation in Cadence

---

##  Conclusion

The op-amp based circuit was successfully verified using both transient and spectrum analysis. FFT results show that the output signal contains only the expected DC and 1 kHz AC components, with all other frequency components suppressed below −80 dB. This confirms proper biasing, stable operation, and acceptable noise performance of the circuit.

This analysis demonstrates the importance of frequency-domain verification in analog IC design.

---

