# chip_top
<div align="center">

# RTL to GDSII Physical Design

**A complete RTL-to-GDSII physical design implementation of a 32×32 Radix-4 Booth Multiplier**

![Node](https://img.shields.io/badge/Technology-45nm-blue)
![Tool](https://img.shields.io/badge/Tool-Cadence%20Innovus%2023.16--s070__1-informational)
![Status](https://img.shields.io/badge/Setup%20WNS--0.118ns-red)
![Status](https://img.shields.io/badge/Hold%20WNS-0.000ns-brightgreen)
![Freq](https://img.shields.io/badge/Frequency-185.185MHz-orange)

</div>

## 🔍 Overview

| | |
|---|---|
| **Project** | 32×32 Booth Multiplier — Full RTL-to-GDSII Physical Design |
| **Technology Node** | 45nm |
| **Tool Flow** | RTL → Genus (Synthesis) → Innovus (PnR) → GDSII |
| **Innovus Version** | 23.16-s070_1 |

---

## 🧩 Design Specification

| Parameter | Value |
|---|---|
| **Type** | Synchronous Radix-4 Booth Multiplier (MAC: X×Y+Z) |
| **Operand Width** | 32 × 32 bits (+32-bit accumulate, Z) |
| **Output Width** | 32 bits + 1-bit overflow |
| **Recoding** | Modified Booth, Radix-4 |
| **Partial Products** | 16 |
| **PP Reduction** | Wallace tree, 4:2 CSAs |
| **Final Adder** | Carry Look-Ahead Adder (CLA) |
| **Pipelining** | None (single-cycle combinational) |
| **Latency** | 1 clock cycle |
| **Reset** | Synchronous (polarity as coded appears inverted) |

---

## 🏗️ Floorplan & Physical Metrics

| Metric | Value |
|---|---|
| **Chip Area** | 1,302,530.94 µm² (≈ 1.303 mm²) |
| **Standard Cell + Macro Area** | 849,057.506 µm² |
| **Utilization** | 65.18% |
| **Standard Cell Count** | 42,669 |
| **Macro Count** | 16 |

---

## ⏱️ Timing Closure Summary

**Clock Period:** 5.400 ns → **Frequency:** 185.185 MHz

### Path Group Summary
| Path Group | WNS (ns) | TNS (ns) | FEP |
|---|---|---|---|
| View: ALL | -0.118 | -1.421 | 29 |
| in2out | +1.918 | 0.000 | 0 |
| reg2out | -0.118 | -1.421 | 29 |
| in2reg | +3.106 | 0.000 | 0 |
| reg2reg | +0.300 | 0.000 | 0 |

### Design Rule Checks (DRC)
| Check | WNS | TNS | FEP |
|---|---|---|---|
| max_transition | -0.062 | -2.284 | 137 |
| max_fanout | -49.000 | -11,421.000 | 1,132 |

---

## ⚡ Power Summary

**Operating Frequency:** 185.185 MHz (Clock Period = 5.4 ns)

| Power Type | Value | % of Total |
|---|---|---|
| **Internal Power** | 2.347 mW | 0.15% |
| **Switching Power** | 4.063 mW | 0.25% |
| **Leakage Power** | 1600.006 mW | 99.60% |
| **Total Power** | **1606.416 mW** | 100% |

⚠️ Leakage power is dominated by the MEM1_256X32 macros, which currently use a simplified 1mW/instance leakage estimate — **not silicon-calibrated**. Total power should be treated as a placeholder until macro leakage is characterized from a real library.

### Power by Category
| Category | Share |
|---|---|
| Macro (MEM1_256X32 × 16) | 99.62% |
| Combinational | 0.23% |
| Sequential (flops) | 0.08% |
| Clock network | 0.07% |

---

## 🖼️ Visuals

### Floorplan
<img width="1920" height="1080" alt="floorplan" src="https://github.com/user-attachments/assets/6d8f4d71-4676-4143-b3e9-fb9504271aee" />

### Port Placement
<img width="1920" height="1080" alt="port_placement" src="https://github.com/user-attachments/assets/8d4c2236-aa32-4087-bf9b-e79a442ac674" />

### Power Plan
<img width="1920" height="1080" alt="power_plan" src="https://github.com/user-attachments/assets/51fc6dcd-2bad-4680-9a5d-5aa9c3f38607" />

### Standard Cells Placed
<img width="1920" height="1080" alt="standard_cells_placed" src="https://github.com/user-attachments/assets/ef71d86a-4cac-4c6c-ab3b-b65425ec4911" />

### Metal Layers (M9 → M1)
<img width="1920" height="1080" alt="layer9" src="https://github.com/user-attachments/assets/3f8e7873-c058-46e2-9e12-c667107e8c80" />
<img width="1920" height="1080" alt="layer8" src="https://github.com/user-attachments/assets/734e750c-1eff-46a6-a982-2b9b61660c34" />
<img width="1920" height="1080" alt="layer6" src="https://github.com/user-attachments/assets/6071a323-2aa3-46af-9c50-f5303637a259" />
<img width="1920" height="1080" alt="layer5" src="https://github.com/user-attachments/assets/a7e73291-ed43-4959-bebe-82baec6110ef" />
<img width="1920" height="1080" alt="layer4" src="https://github.com/user-attachments/assets/556b759f-6b2b-4877-a94f-cfd9fd29f75f" />
<img width="1920" height="1080" alt="layer3" src="https://github.com/user-attachments/assets/6a8355bc-e4bb-4066-84d1-bb90da78963f" />
<img width="1920" height="1080" alt="layer2" src="https://github.com/user-attachments/assets/94b885dc-c99d-4b41-ba42-9ac502d5f055" />
<img width="1920" height="1080" alt="layer2" src="https://github.com/user-attachments/assets/7f143544-e027-45e3-bd3f-4b353da2a627" />

### Pre-CTS
<img width="1920" height="1080" alt="pre_cts" src="https://github.com/user-attachments/assets/45fc096e-3edd-4f55-a163-167bcc45b611" />

### Post-CTS
<img width="1920" height="1080" alt="post_cts" src="https://github.com/user-attachments/assets/a2395760-0ddb-4358-a48d-67031bf13313" />

### Clock Tree
<img width="1920" height="1080" alt="clocktree" src="https://github.com/user-attachments/assets/e2886077-1b8c-41e9-b0c3-297077b713c0" />

---

<div align="center">

**Built using the Cadence RTL-to-GDSII flow — Genus (Synthesis) → Innovus (Place & Route)**

</div>
