# ⚡ Real-Time Input Lag Detection using Hybrid Spiking Neural Networks

## 📌 Project Overview

This project presents a **hybrid hardware–software framework** for real-time input lag detection in interactive media systems such as online gaming and cloud-based applications.

Input lag is defined as the delay between a user action and the corresponding on-screen response. It typically arises due to the simultaneous occurrence of:

- 🌐 High Network Latency (Ping > 150 ms)
- 🎮 Low Framerate (FPS < 30)

The proposed system detects lag **only when both conditions occur simultaneously**, ensuring accurate and noise-free detection.

---

## 🧠 Core Concept

Traditional monitoring systems rely on continuous numerical computation, which introduces additional processing delay.

This project instead adopts an **event-driven neuromorphic approach** using:

- ⚙️ Analog Leaky Integrate-and-Fire (LIF) Neuron for latency violation detection  
- 🧮 Software-based framerate analysis  
- 🔗 Fusion logic implementing logical AND correlation  

This hybrid approach enables:

✔ Low-latency detection  
✔ Deterministic response  
✔ Hardware-level event processing  
✔ Sub-millisecond reaction time  

---

## 🏗 System Architecture

The system consists of three main layers:

### 1️⃣ Hardware Layer (LTspice Simulation)

- Comparator-based threshold detection  
- Voltage divider for latency boundary generation  
- RC differentiator for spike generation  
- Diode-based noise suppression  
- Analog LIF neuron implementation  

The hardware neuron generates a spike when:


V_ping > V_threshold


The spike response follows:


V_spike(t) = V_out · e^(-t/τ)


Measured response time: **~0.16 ms**

---

### 2️⃣ Software Layer (Python-Based Analysis)

- Framerate monitoring
- Timestamp logging
- Ground-truth lag labeling
- Temporal event verification

Lag condition is formally defined as:


L(t) = 1 if P(t) > P_th AND F(t) < F_th


Where:
- P(t) → Network latency  
- F(t) → Framerate  
- P_th → 150 ms  
- F_th → 30 FPS  

---

### 3️⃣ Fusion Logic

Lag is declared only when:


Latency Spike Detected AND Framerate Degradation Detected


This prevents false positives caused by isolated metric violations.

---

## 📊 Experimental Results

| Event        | Game Log Time | HW Spike Time | Detection Delay |
|--------------|--------------|--------------|----------------|
| Lag Event 1  | 0.00200 s   | 0.00216 s   | 0.16 ms        |
| Lag Event 2  | 0.01200 s   | 0.01216 s   | 0.16 ms        |
| Non-Lag Case | 5.00000 s   | None        | —              |

### ✅ Observations

- Deterministic hardware response  
- No false positives during non-lag intervals  
- Consistent sub-millisecond detection delay  
- Stable analog behavior  

---

## 🔬 Technical Highlights

- Analog implementation of LIF neuron
- Event-driven spike-based detection
- Hardware–software co-design
- Temporal correlation validation
- Comparison with LSTM-based detection models
- Neuromorphic-inspired architecture

---

## 🛠 Tools & Technologies Used

- LTspice (Analog Circuit Simulation)
- Python (Data Processing & Correlation)
- Spiking Neural Networks (SNN)
- Analog VLSI Concepts
- Threshold-Based Detection Systems
- Hybrid Computing Architecture

---

## 📄 Research Paper

The full implementation details, mathematical derivations, circuit schematics, and verification methodology are available in:

📘 **Hybrid_SNN_Input_Lag_Detection_2025.pdf**

This includes:

- LIF neuron circuit design
- Fusion logic schematic
- Mathematical modeling
- Correlation equations
- Comparative performance analysis
- Experimental validation tables

---

## 🎯 Why This Work is Important

Interactive systems demand ultra-low latency to preserve Quality of Experience (QoE).

This project demonstrates that:

- Neuromorphic hardware can detect latency events faster than traditional software-only approaches
- Analog SNN circuits can provide deterministic and energy-efficient monitoring
- Hybrid architectures can improve real-time system reliability

---

## 🚀 Future Scope

- FPGA-based integration of fusion logic  
- Adaptive threshold mechanisms  
- Extension to additional QoE metrics (jitter, packet loss)  
- Real hardware prototype implementation  

---

## 👨‍🎓 Academic Context

This research was conducted in the domain of:

- Neuromorphic Computing  
- Real-Time Systems  
- Analog Circuit Design  
- Hardware–Software Co-Design  
- AI and Embedded Systems  

---
