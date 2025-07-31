# BldC-MOTOR-speed-control-
speed control of the bldc motor using Pid controller and neural network 
| Step            | MATLAB-Simulink                                     | Firmware                              |
| --------------- | --------------------------------------------------- | ------------------------------------- |
| **Plant Model** | 6-step, trapezoidal BEMF, inverter + buck converter | —                                     |
| **Controller**  | Outer **speed PI** + optional **current PI**        | Same structure, C-coded               |
| **Auto-tune**   | Use `Closed-Loop PID Autotuner` block               | Export gains via `mscript_tune_pid.m` |
| **Validation**  | Monte-Carlo, locked-rotor, thermal corners          | HIL with STM32 acting as plant        |
