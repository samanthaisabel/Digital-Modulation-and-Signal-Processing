<a id="readme-top"></a>

> [!IMPORTANT]
> **Field:** `RF Engineering` • **Simulation:** `netTIMS (Telecoms Bench)`  
> **Core Objective:** Validated digital modulation (ASK, PSK, QPSK, DSSS) and SDR undersampling theories to optimize spectral efficiency and noise immunity.

# 📡 Digital Modulation & Signal Processing
> **A systematic evaluation of digital keying, spread spectrum (DSSS), and SDR undersampling theories, focusing on spectral efficiency and noise immunity via the netTIMS simulator.**

---

### 🛠️ Technical Skillset
*   **Digital Modulation:** Implementation of **ASK**, **FSK**, and Phase-reversal techniques (**BPSK/QPSK**).
*   **Spread Spectrum:** Bandwidth spreading and despreading using **Direct Sequence Spread Spectrum (DSSS)** and PN codes.
*   **SDR & Sampling:** Advanced signal processing involving **Undersampling** and intentional aliasing for SDR optimization.

---

### 🔬 System Analysis & Key Findings
*   **Modulation Robustness:** Confirmed that **BPSK/QPSK** provides superior noise rejection compared to amplitude-based keying (ASK).
*   **Spectral Efficiency:** Successfully doubled data throughput within a fixed bandwidth using **Quadrature Phase States**.
*   **Interference Mitigation:** Validated that **DSSS** significantly reduces the impact of narrowband interference through processing gain.
*   **SDR Optimization:** Proved that **Undersampling** allows for accurate reconstruction of high-frequency carriers using lower sampling rates.

---

## 📋 Table of Contents
* [Amplitude Shift Keying (ASK)](#ask)
* [Frequency Shift Keying (FSK)](#fsk)
* [Binary Phase Shift Keying (BPSK)](#bpsk)
* [Quadrature Phase Shift Keying (QPSK)](#qpsk)
* [DSSS Modulation and Demodulation](#dsss)
* [Undersampling in Software Defined Radio (SDR)](#sdr)

---

<a name="ask"></a>
## 📶 Amplitude Shift Keying (ASK)
*Digital information represented by varying carrier amplitude via netTIMS modulation blocks.*

<details>
<summary>Learn more</summary>

### Introduction
ASK is a digital modulation technique where the amplitude of a carrier signal is varied according to the digital data. Binary information is represented by different amplitude levels while frequency and phase remain constant.

### Objectives
* Understand the working principle of ASK.
* Generate an ASK signal from digital data input.
* Observe waveform behavior using signal monitoring equipment.
* Analyze performance in the presence of noise.

### Theoretical Background
The ASK modulated signal $s(t)$ is defined as:

$$s(t) = A_c \cos(2\pi f_c t) \quad \text{for binary 1}$$
$$s(t) = 0 \quad \text{for binary 0}$$

**Where:**
* $A_c$ = Carrier amplitude
* $f_c$ = Carrier frequency

### Laboratory Results
* Binary input signals were successfully converted into ASK waveforms.
* Carrier amplitude appeared only during the transmission of binary 1.
* Small amplitude distortions were observed when interference was present.

### Discussion
The experiment demonstrated that ASK encodes data through variations in carrier amplitude. While easy to implement, it is highly sensitive to noise because interference can easily alter the signal amplitude. This limits its use to short-range or low-power systems.

### Conclusion
Successfully verified that digital information can be transmitted by controlling carrier amplitude. However, results confirmed that ASK is susceptible to noise, affecting signal reliability.

### Documentation
<details>
<summary><b>View Laboratory Documentation</b></summary>

  <p align="center">
    <strong>Signal Analysis</strong><br>
    <img src="assets/Amplitude%20Shift%20Keying/Experiment-15-Part-A.png" height="250">
    <img src="assets/Amplitude%20Shift%20Keying/Experiment-15-Part-A%20%282msdiv%29.png" height="250">
    <img src="assets/Amplitude%20Shift%20Keying/Experiment15-PartA-step7.png" height="250">
  </p>

  <p align="center">
    <img src="assets/Amplitude%20Shift%20Keying/Experiment-15-Part-A-step13.png" height="250">
    <img src="assets/Amplitude%20Shift%20Keying/Experiment-15-Part-B-step17.png" height="250">
    <img src="assets/Amplitude%20Shift%20Keying/Experiment-15-Part-C-step20.png" height="250">
  </p>

  <div align="center">
    <strong>Noise Performance</strong><br>
    <img src="assets/Amplitude%20Shift%20Keying/Experiment-15-Noise-step3.png" height="250"><img src="assets/Amplitude%20Shift%20Keying/Experiment-15-Noise-step5.png" height="250">
    <br>
    <img src="assets/Amplitude%20Shift%20Keying/Experiment-15-Noise-step6.png" height="250"><img src="assets/Amplitude%20Shift%20Keying/Experiment-15-Noise-step8.png" height="250">
  </div>

</details>
</details>

---

<a name="fsk"></a>
## 〰️ Frequency Shift Keying (FSK)
*Frequency-based encoding for improved noise immunity.*

<details>
<summary>Learn more</summary>

### Introduction
FSK is a digital modulation method in which the frequency of a carrier signal changes according to the digital input data. Unlike ASK, the carrier amplitude remains constant while two different frequencies represent binary values.

### Objectives
* Understand the concept of FSK modulation.
* Generate FSK signals from binary data.
* Observe frequency switching between binary states.

### Theoretical Background
Binary FSK uses two distinct frequencies:
* $f_1$ for binary 1: $s(t) = A_c \cos(2\pi f_1 t)$
* $f_2$ for binary 0: $s(t) = A_c \cos(2\pi f_2 t)$

### Laboratory Results
* Carrier frequency switched between two values based on digital input.
* Binary states were clearly distinguishable in the waveform.
* Carrier amplitude remained stable throughout the experiment.

### Discussion
Results showed that FSK effectively transmits data through frequency variation, demonstrating improved reliability over ASK since noise primarily impacts signal amplitude rather than frequency.

### Conclusion
FSK provides improved signal reliability by encoding digital information in frequency variations rather than amplitude changes.

### Documentation
<details>
<summary><b>View Laboratory Documentation</b></summary>
<p align="center">
  <strong>Frequency Modulation & Step Analysis</strong><br>
  <img src="assets/Frequency%20Shift%20Keying/Experiment16-Part-A-step12.png" height="220">
  <img src="assets/Frequency%20Shift%20Keying/Experiment16-Part-B-step18.png" height="220">
  <img src="assets/Frequency%20Shift%20Keying/Experiment16-Part-B-step21.png" height="220">
</p>
<p align="center">
  <strong>Final Signal Output</strong><br>
  <img src="assets/Frequency%20Shift%20Keying/Experiment16-Part-C-Output.png" height="220">
</p>
</details>
</details>

---

<a name="bpsk"></a>
## 🔄 Binary Phase Shift Keying (BPSK)
*Phase-reversal modulation for high-reliability data links.*

<details>
<summary>Learn more</summary>

### Introduction
BPSK is a digital modulation technique where the phase of the carrier signal is shifted according to the binary input data. It is one of the simplest and most reliable phase modulation schemes.

### Objectives
* Study the operation of BPSK modulation.
* Generate BPSK signals from digital input.
* Observe phase transitions in the waveform.

### Theoretical Background
In BPSK, the phase shifts by 180° depending on the binary input:
* Binary 1: $s(t) = A_c \cos(2\pi f_c t)$
* Binary 0: $s(t) = -A_c \cos(2\pi f_c t)$

### Laboratory Results
* Phase inversion was observed when the binary input changed.
* Carrier amplitude and frequency remained constant.
* The waveform flipped by 180° between binary states.

### Discussion
The experiment confirmed that BPSK transmits information through phase changes. This makes it more resistant to noise and signal attenuation compared to ASK or FSK.

### Conclusion
BPSK is an efficient and reliable digital modulation technique widely used in wireless communication systems.

### Documentation
<details>
<summary><b>View Laboratory Documentation</b></summary>
<p align="center">
  <strong>Phase Transition Analysis</strong><br>
  <img src="assets/Binary%20Phase%20Shift%20Keying/Part%20A.png" height="220">
  <img src="assets/Binary%20Phase%20Shift%20Keying/Part%20B.png" height="220">
  <img src="assets/Binary%20Phase%20Shift%20Keying/Part%20C.png" height="220">
</p>

<p align="center">
  <strong>Noise</strong><br>
  <img src="assets/Binary%20Phase%20Shift%20Keying/Part%20Noise%280dB%29.png" height="220">
  <img src="assets/Binary%20Phase%20Shift%20Keying/Part%20Noise%28-6dB%29.png" height="220">
  <img src="assets/Binary%20Phase%20Shift%20Keying/Part%20Noise%28-20dB%29.png" height="220">
</p>
</details>
</details>

---

<a name="qpsk"></a>
## ⏹️ Quadrature Phase Shift Keying (QPSK)
*Four-phase modulation for doubled spectral efficiency.*

<details>
<summary>Learn more</summary>

### Introduction
QPSK is a digital modulation technique that transmits two bits of information per symbol by using four different phase states. This improves spectral efficiency compared to BPSK.

### Objectives
* Understand the operation of QPSK modulation.
* Observe the four phase states of QPSK.
* Analyze symbol representation.

### Theoretical Background
QPSK uses four phase angles representing bit pairs:
* **00:** 0° | **01:** 90° | **11:** 180° | **10:** 270°

### Laboratory Results
* Four distinct phase states were observed.
* Each symbol represented two bits of digital information.
* Carrier amplitude remained constant during transmission.

### Discussion
QPSK improves data transmission efficiency while maintaining the same bandwidth as BPSK. However, the receiver design is more complex due to the need for accurate phase detection.

### Conclusion
QPSK provides improved spectral efficiency and is widely used in modern networks such as satellite and wireless systems.

### Documentation
<details>
<summary><b>View Laboratory Documentation</b></summary>
<p align="center">
  <strong>Generating a QPSK Signal</strong><br>
  <img src="assets/Quadrature%20Phase%20Shift%20Keying/Part%20A%20Step%201-10.png" height="180">
  <img src="assets/Quadrature%20Phase%20Shift%20Keying/Part%20A%20Step%2011-17.png" height="180">
  <img src="assets/Quadrature%20Phase%20Shift%20Keying/Part%20A%20Step%2018-21.png" height="180">
</p>
<p align="center">
  <img src="assets/Quadrature%20Phase%20Shift%20Keying/Part%20A%20Step%2022-24.png" height="180">
  <img src="assets/Quadrature%20Phase%20Shift%20Keying/Part%20A%20Step%2025.png" height="180">
</p>
<p align="center">
  <strong>Using phase discrimination to pick out one of the QPSK signal's BPSK signals</strong><br>
  <img src="assets/Quadrature%20Phase%20Shift%20Keying/Part%20B%20Phase%20Shifter%20Clockwise%200%20deg.png" height="220">
  <img src="assets/Quadrature%20Phase%20Shift%20Keying/Part%20B%20Phase%20Shifter%20Clockwise%20180%20deg.png" height="220">
</p>
<p align="center">
  <img src="assets/Quadrature%20Phase%20Shift%20Keying/Part%20B%20Phase%20Shifter%20Counter%20Clockwise%200%20deg.png" height="220">
  <img src="assets/Quadrature%20Phase%20Shift%20Keying/Part%20B%20Phase%20Shifter%20Counter%20Clockwise%20180%20deg.png" height="220">
</p>
</details>
</details>

---

<a name="dsss"></a>
## 🛰️ DSSS Modulation and Demodulation
*Wideband signal spreading for secure and interference-resistant communication.*

<details>
<summary>Learn more</summary>

### Introduction
Direct Sequence Spread Spectrum (DSSS) spreads the transmitted signal across a wider frequency band using a pseudo-random code. This improves signal security and noise immunity.

### Objectives
* Understand DSSS modulation principles.
* Observe signal spreading using a pseudo-random sequence.
* Recover the original signal through demodulation.

### Theoretical Background
The original data signal is multiplied by a high-rate pseudo-random spreading code. This spreads the signal energy over a wide frequency band. At the receiver, the same code is used for reconstruction.

### Laboratory Results
* Transmitted signal bandwidth increased after spreading.
* The receiver successfully recovered original data using the same spreading code.
* Interference effects were reduced due to spreading.

### Discussion
DSSS improves communication reliability by distributing energy across a wider range. This makes the signal more resistant to narrowband interference and improves security.

### Conclusion
DSSS modulation enhances signal robustness and is widely used in GPS and Wi-Fi communication.

### Documentation
<details>
<summary><b>View Laboratory Documentation</b></summary>

<p align="center">
  <strong>Signal Spreading & PN Code</strong><br>
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20A.png" height="220">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20C-no18.png" height="220">
</p>
<p align="center">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20C-no19.png" height="220">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20C-no21.png" height="220">
</p>

<p align="center">
  <strong>Demodulation</strong><br>
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no28.png" height="220">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no29.png" height="220">
</p>
<p align="center">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no30-1.png" height="220">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no30-2.png" height="220">
</p>

<p align="center">
  <strong>Frequency Bounds & Optimization</strong><br>
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no31-1%20minfreq.png" height="220">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no31-2%20maxfreq.png" height="220">
</p>
<p align="center">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no34.png" height="220">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no38.png" height="220">
</p>
<p align="center">
  <strong>Advanced Signal Characterization</strong><br>
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no40.png" height="220">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no42.png" height="220">
  <img src="assets/DSSS%20Modulation%20and%20Demodulation/Lab%2019%20Part%20D-no44.png" height="220">
</p>
</details>
</details>

---

<a name="sdr"></a>
## 📻 Undersampling in Software Defined Radio (SDR)
*Efficient high-frequency processing through intentional aliasing.*

<details>
<summary>Learn more</summary>

### Introduction
SDR uses digital signal processing for functions traditionally handled by hardware. Undersampling allows high-frequency signals to be sampled at lower rates while preserving the information.

### Objectives
* Study undersampling techniques in SDR systems.
* Observe aliasing effects in sampled signals.
* Analyze signal recovery using digital processing.

### Theoretical Background
Undersampling intentionally uses aliasing to shift high-frequency signals into a lower frequency band. If the sampling frequency is carefully selected, the desired signal can be reconstructed digitally.

### Laboratory Results
* High-frequency signals were successfully sampled at lower rates.
* Aliased signals appeared in lower frequency regions.
* Digital filtering techniques successfully recovered the original signal.

### Discussion
Undersampling can simplify receiver hardware in SDR systems, though careful design is required to prevent unwanted aliasing interference.

### Conclusion
Undersampling enables efficient digital processing of high-frequency signals in SDR systems, reducing hardware complexity while maintaining signal integrity.

### Documentation
<details>
<summary><b>View Laboratory Documentation</b></summary>

<p align="center">
  <strong>Setting up a bandwidth limited signal</strong><br>
  <img src="assets/Undersampling%20in%20%20Software%20defined%20radio/Lab%2020%20Part%20A-no6.png" height="280">
</p>

<p align="center">
  <strong>Direct down-conversion using undersampling</strong><br>
  <img src="assets/Undersampling%20in%20%20Software%20defined%20radio/Lab%2020%20Part%20B-no8.png" height="280">
  <img src="assets/Undersampling%20in%20%20Software%20defined%20radio/Lab%2020%20Part%20B-no10.png" height="280">
</p>

<p align="center">
  <strong>Synchronisation</strong><br>
  <img src="assets/Undersampling%20in%20%20Software%20defined%20radio/Lab%2020%20Part%20C-no19.png" height="280">
  <img src="assets/Undersampling%20in%20%20Software%20defined%20radio/Lab%2020%20Part%20C-no21.png" height="280">
</p>
</details>
</details>

---

### 💡 Overall Takeaways & Analysis
*Practical insights into digital link performance and signal processing.*

*   **Modulation Gained Knowledge:** Evaluated the trade-offs between low-complexity hardware (ASK/RFID) and high-reliability links (PSK), identifying why certain schemes are preferred for mission-critical telemetry.
*   **Bandwidth Efficiency Validation:** Successfully simulated **QPSK** to achieve double the data throughput within a fixed bandwidth—directly replicating the spectral efficiency standards used in **5G** and **Wi-Fi** networks.
*   **Interference Recovery Skills:** Used **DSSS** (Spread Spectrum) to observe how processing gain allows a signal to be recovered even when buried under narrowband interference or a high noise floor.
*   **SDR Theory Testing:** Confirmed **Software Defined Radio** architectures by using intentional aliasing/undersampling to prove that high-frequency carriers can be reconstructed with lower ADC requirements.

### 📈 Final Conclusion
This laboratory series served as a bridge between theoretical communication models and practical system constraints. By leveraging the netTIMS Simulator, I was able to stress-test digital links against noise and bandwidth limitations that are difficult to isolate in raw hardware. This experience provides a solid foundation for validating, troubleshooting, and optimizing modern RF and SDR systems in a controlled, data-driven environment.

---

<p align="right"><a href="#readme-top">Back to top ↑</a></a></p>
