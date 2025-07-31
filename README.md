# BldC-MOTOR-speed-control-  
*Speed control of a BLDC motor using PID Controller & Neural Network*

---

## 🎯 Overview
This repository provides an end-to-end reference design for **sensorless BLDC motor speed control** that you can:

- **Simulate** in MATLAB-Simulink  
- **Auto-tune** with classic PID **or** a lightweight neural network  
- **Deploy** to an STM32 MCU with one `make flash`

---

## 🔍 Quick-Start

| Step | MATLAB-Simulink | Firmware |
|------|-----------------|----------|
| **Plant Model** | 6-step, trapezoidal BEMF, inverter + buck converter | — |
| **Controller** | Outer **speed PI** **or** **Neural Network** | Same structure, C-coded |
| **Auto-tune** | `Closed-Loop PID Autotuner` or `nn_tune_script.m` | Export gains automatically |
| **Validation** | Monte-Carlo, locked-rotor, thermal corners | HIL with STM32 as plant |

---

## 📂 Simulation Tree
BLDC_SpeedControl.slx
├─ Plant
│  ├─ Three-Phase Inverter (IGBT)
│  ├─ BLDC Motor (Trapezoidal BEMF)
│  └─ Buck Converter
├─ Control
│  ├─ Speed PI Controller  (or Neural Net)
│  ├─ Commutation Logic (Hall / sensorless)
│  └─ PWM Generator
└─ Visualization
├─ Scope: RPM vs Reference
└─ Scope: Phase currents

## 🚀 5-Minute Run

1. **Clone**
   ```bash
   git clone https://github.com/<user>/BldC-MOTOR-speed-control-.git
   cd BldC-MOTOR-speed-control-

   Open & Simulate
matlab
Copy
open_system('BLDC_SpeedControl.slx')
sim('BLDC_SpeedControl.slx')
Tune PID
matlab
Copy
run tools/mscript_tune_pid.m   % classic PI
run tools/nn_tune_script.m     % optional neural network
