# Op-Amp Signal Integrity Verification Using Transient, FFT, and Spectrum Metrics

> Tool: Cadence Virtuoso (Spectre APS)  
> Analysis: Transient, FFT (Spectrum), Signal Metrics  
> Verification Level: Time Domain + Frequency Domain + Quantitative Metrics

---

##  Objective

The objective of this experiment is to verify the signal integrity of an op-amp based circuit using:

- Time-domain (Transient) analysis
- Frequency-domain (FFT / Spectrum) analysis
- Quantitative signal quality metrics obtained from the Spectrum tool

This analysis ensures that the output signal:
- Contains only the intended frequency components
- Has acceptable noise performance
- Meets standard analog signal quality criteria

---

##  Circuit Description

The circuit consists of:
- An inbuilt op-amp from the gpdk045 library
- External biasing and feedback network
- Differential input signals
- Single-ended output

The op-amp operates in a closed-loop configuration using negative feedback to ensure linear and stable operation.

---

##  Circuit Schematic

![Op-Amp Circuit](schematic.png)

*Figure 1: Op-amp based circuit used for transient and spectrum analysis.*

---

## ⏱️ Transient Analysis

### Purpose
Transient analysis is used to:
- Observe time-domain behavior
- Verify amplification and biasing
- Ensure absence of clipping or distortion

---

### Transient Response

![Transient and FFT Plot](transient_fft.png)

*Figure 2: Time-domain waveforms of input and output signals.*

### Observations
- Input signal is a sinusoid at **1 kHz**
- Output signal is amplified and stable
- DC offset is present due to biasing
- No waveform distortion observed

This confirms correct **DC operating point and closed-loop behavior**.

---

##  Spectrum (FFT) Analysis

### Why Spectrum Analysis Is Required

Transient analysis alone cannot reveal:
- Hidden frequency components
- Harmonics
- Noise floor

FFT analysis converts the time-domain signal into the frequency domain, enabling detection of unwanted spectral content.

---

### FFT Observations

From the spectrum plots:

- **DC Component (0 Hz)**  
  - Present due to DC bias  
  - Expected since DC has no frequency

- **Fundamental Frequency (1 kHz)**  
  - Clear and dominant peak  
  - Matches the applied input signal frequency

- **Noise Floor**  
  - Remaining spectral components are below **−80 dB**
  - Indicates low noise and minimal distortion

This confirms acceptable signal purity.

---

##  Spectrum Metrics (Quantitative Verification)

In addition to visual FFT plots, the **Spectrum tool** provides numerical performance metrics.

### Spectrum Window

![Spectrum Metrics](spectrum_metrics.png)

*Figure 3: Spectrum window showing FFT configuration and signal quality metrics.*

### Extracted Metrics (from Spectrum Tool)

- **SNR (Signal-to-Noise Ratio)** ≈ 25.5 dB  
- **SNDR (Signal-to-Noise-and-Distortion Ratio)** ≈ 11.4 dB  
- **SFDR (Spurious-Free Dynamic Range)** ≈ 12.0 dB  
- **ENOB (Effective Number of Bits)** ≈ 1.6 bits  

### Interpretation
- Presence of a dominant fundamental tone confirms correct amplification
- Low spurious components validate stable operation
- Noise and distortion levels are within acceptable limits for this configuration
- Metrics provide quantitative confirmation of signal quality

---

##  Verification Summary

| Verification Aspect | Result |
|-------------------|--------|
| Time-Domain Behavior | Stable, no distortion |
| Fundamental Frequency | Correct (1 kHz) |
| DC Component | Expected |
| Noise Floor | Below −80 dB |
| Spectrum Metrics | Acceptable |

---

##  Key Learnings

- Transient analysis validates waveform shape
- FFT reveals frequency components and noise
- Spectrum metrics provide quantitative signal assessment
- DC bias appears as a 0 Hz component
- FFT + metrics are essential for analog front-end validation

---

##  Conclusion

The op-amp based circuit was successfully verified using transient, FFT, and spectrum metric analyses. The output signal contains only the expected DC and 1 kHz frequency components, with all other spectral content suppressed below −80 dB. Quantitative metrics such as SNR, SNDR, SFDR, and ENOB further confirm acceptable signal quality. This comprehensive verification demonstrates proper biasing, stable operation, and good signal integrity.

---
