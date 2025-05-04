---
title: "Advanced technology for Neuromorphic Systems"
collection: teaching
type: "Graduate course at ETH"
permalink: /teaching/2024-fall-NE1
venue: "ETH"
date: 2024-12-09
location: "Zurich, CH"
---

This lecture traced the evolution of transistor technology from planar CMOS to cutting-edge nanosheet architectures, emphasizing their implications for neuromorphic computing. It analyzed short-channel effects and how FinFETs and FDSOI help mitigate them. The talk then explored the memory technology landscape, from traditional SRAM/DRAM to emerging RRAM, MRAM, and PCM. Special focus was given to In-Memory Computing (IMC), especially its synergy with neuromorphic systems. Finally, the challenges and solutions around variability in RRAM-based spiking neural networks were discussed.

> Find the lecture's slides at this [link](https://docs.google.com/presentation/d/1ctYzLZ3J9WrgcVcC-jSBhLwSUJXFi77_puWjmSK5FKE/edit?usp=sharing)

---

## Key points from the lecture

1. Transistor Technology Evolution
- Moore’s Law: Historical context and present-day implications.
- Challenges of scaling: Short-channel effects like velocity saturation, DIBL, and punch-through.
- FDSOI: Advantages for low-power applications like neuromorphic engineering.
- FinFETs: How vertical structures increase density and extend Moore’s Law.
- Gate-All-Around and Nanosheet transistors: Latest industry directions and roadmap.

2. Memory Technology Landscape
- Memory hierarchy: Endurance, access time, density trade-offs.
- Traditional technologies: SRAM, DRAM, NAND Flash (with scaling trends and limitations).
- Why DRAM isn’t used on-chip and the rise of 3D NAND Flash.
- Floating gate transistors: Core principle behind non-volatile memories.

3. Emerging Non-Volatile Memories
- RRAM: Resistance-based with multilevel potential.
- MRAM: Magnetization-based with high endurance.
- PCM: Phase-change with thermal switching.
- Application examples from STMicroelectronics and Infineon.

4. In-Memory Computing (IMC)
- Addresses the Von Neumann bottleneck by co-locating compute and memory.
- Key for efficient Multiply-Accumulate (MAC) operations in edge-AI and neuromorphic processors.
- IMC core architecture: memory arrays, WL/BL drivers, ADCs, local logic.

5. Neuromorphic IMC and RRAM Variability
- Exploiting sparsity in Spiking Neural Networks (SNNs) for ultra-efficient computing.
- Challenges: Device-to-device and cycle-to-cycle variability in RRAMs.
- Solutions: Read-and-verify schemes and variability-aware training (including your own work: Memristor-Aware Training).