# CHIP_TOP
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

### Port Placement
<img width="1920" height="1080" alt="port_placement" src="https://github.com/user-attachments/assets/457cfc79-f7ce-4c99-b761-c8d6dce36b55" />  

### macros Placed
<img width="1920" height="1080" alt="macros_placed_chiptop" src="https://github.com/user-attachments/assets/165e4fa3-90ba-41d4-8832-d2892f51b722" />

### physical cells Placed
<img width="1920" height="1080" alt="physical_cells_chiptop" src="https://github.com/user-attachments/assets/b4d0b469-79c9-423d-ac6f-0b9c62dde0de" />


### Power Plan
<img width="1920" height="1080" alt="power_plan_chiptop" src="https://github.com/user-attachments/assets/438e4a76-c5e6-4397-9aec-788d42cc7cb2" />


### Standard Cells Placed
<img width="1920" height="1080" alt="stdcells_chiptop" src="https://github.com/user-attachments/assets/89835b95-8658-4055-9123-0279b62641c2" />

### Post-CTS
<img width="1920" height="1080" alt="cts_chiptop" src="https://github.com/user-attachments/assets/1553c2d0-ec86-41ac-adc0-af88842c3e37" />

### routed
<img width="1920" height="1080" alt="routed_chiptop" src="https://github.com/user-attachments/assets/dc662fbd-fc64-4645-ae07-4cdb541404b3" />

### Metal Layers (M9 → M1)
<img width="1920" height="1080" alt="stdcells_chiptop" src="https://github.com/user-attachments/assets/48f75e7f-3e5e-4d2c-9836-07a9f73ffa28" />
<img width="1920" height="1080" alt="m9" src="https://github.com/user-attachments/assets/7e7e0046-4464-4e71-8278-ae1fb9345d3d" />
<img width="1920" height="1080" alt="m8" src="https://github.com/user-attachments/assets/0513e491-a8d0-4309-a349-b6204529c096" />
<img width="1920" height="1080" alt="m7" src="https://github.com/user-attachments/assets/2c3cd557-1e3e-48b0-87d0-01443e93744e" />
<img width="1920" height="1080" alt="m5" src="https://github.com/user-attachments/assets/35db367d-e448-4710-8b2e-64bd106eed1e" />
<img width="1920" height="1080" alt="m4" src="https://github.com/user-attachments/assets/c156824c-775e-4ad6-ac94-ec439de8ba80" />
<img width="1920" height="1080" alt="m3" src="https://github.com/user-attachments/assets/109f0d63-6fa7-49a8-b761-e66d203f40a4" />
<img width="1920" height="1080" alt="m2" src="https://github.com/user-attachments/assets/329b0b68-c3aa-483e-bbc2-dc75d77b0836" />
<img width="1920" height="1080" alt="m1" src="https://github.com/user-attachments/assets/b7b506ea-9dbb-4e6b-8d5f-58d8fb6c84e5" />

### Clock Tree
<img width="1920" height="1080" alt="clock_Tree_chiptop" src="https://github.com/user-attachments/assets/624fbcd3-7781-47aa-928c-1eb5b2e63fb7" />

---

<div align="center">

**Built using the Cadence RTL-to-GDSII flow — Genus (Synthesis) → Innovus (Place & Route)**

</div>
