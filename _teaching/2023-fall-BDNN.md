---
title: "Introduction to Neuromorphic Engineerings"
collection: teaching
type: "Graduate course at ETH"
permalink: /teaching/2023-fall-Learning in Deep Artificial and Biological Neuronal Networks
venue: "ETH"
date: 2023-12-21
location: "Zurich, CH"
---

This lecture introduced the core principles of neuromorphic engineering, focusing on the design of real-time, adaptive, and energy-efficient systems that emulate the brain. It explored how sparsity, locality, and event-based computation underpin biological efficiency and how these are translated into hardware. The talk presented neuromorphic sensors, analog and digital implementations, and in-memory computing as enabling technologies. Special emphasis was placed on training and architecture strategies for event-driven systems, including the Mosaic framework and delay-based SNNs. Finally, it highlighted how physical dynamics and enriched computational units can enhance neuromorphic processing.

> Find the lecture's slides at this [link](https://docs.google.com/presentation/d/1V5jBSsgxQfN2C7Bzp7vBWDnKEsLttT3t/edit?usp=sharing&ouid=103941732477067461400&rtpof=true&sd=true)

---

## Key points from the lecture

1. Vision and Motivation
- Goal: Build intelligent, adaptive machines that close the sensory-motor loop in real time.
- Key challenge: Edge computing under severe constraints (power, memory, latency).
- Strategy: Learn from the brain's mechanisms—sparsity, locality, dynamics, and adaptation.

2. Sparsity and Event-Driven Paradigm
- Sparsity in time and space: Only respond to meaningful events.
- Neuromorphic sensors: Vision (DVS), audio (cochlea), touch, olfaction, etc.
- Event-driven processing: SNNs that compute only when spikes occur, reducing power and computation.

3. Neuromorphic Hardware Implementations
- Digital vs Analog: Digital offers precision; analog exploits physical properties for ultra-efficiency.
- Local computation: MAC operations using RRAM crossbars for in-memory computation.
- Event-based In-Memory Computing: Mosaic architecture with small-world connectivity and local communication.

4. Training and Optimization
- Hardware-aware training: Penalizing non-local connections, RRAM-aware quantization (using STE).
- Delay-based SNNs: Using spike timing as a computational variable.
- Online learning strategies: Local, sparse updates to preserve memory lifespan and reduce energy.

5. Physical Dynamics & Rich Computation
- Temporal processing: Matching time scales between hardware and signal dynamics.
- Analog substrates: Using RC time constants, volatile memory, and dendritic delays.
- Enriched neuron models: Moving beyond ReLU to multi-compartment spiking neurons with temporal logic.