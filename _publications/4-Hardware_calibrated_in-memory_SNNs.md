---
title: "Hardware calibrated learning to compensate heterogeneity in analog RRAM-based Spiking Neural Networks"
collection: publications
category: conferences
permalink: /publication/2022_Hardware_calibrated_in-memory_SNNs
#excerpt: 'This paper is about fixing template issue #693.'
date: 2022-05-27
venue: 'ISCAS 2022'
paperurl: 'https://ieeexplore.ieee.org/abstract/document/9937820'
citation: 'F. Moro. (2022). &quot;PHardware calibrated learning to compensate heterogeneity in analog RRAM-based Spiking Neural Networks.&quot; <i>ISCAS</i>. 1(3).'
---

---

## In-Memory Computing with Non-Volatile Memory
In-memory computing (IMC) with Non-Volatile Memory (NVM) — and RRAM in particular — is a compelling match for neural network inference: synaptic weights are stored directly in the memory array, and the multiply-accumulate operation is performed in place, avoiding costly data movement. The catch is scalability. In conventional Artificial Neural Networks (ANNs), dense input activations cause all rows of the crossbar to fire simultaneously, driving large currents through each column resulting in large power density. Spiking Neural Networks (SNNs) are the solution to this problem: their inherently sparse, binary activations mean that only a small fraction of rows are active at any moment, keeping column currents — and therefore power — low without any architectural compromise.

## Analog circuits non-idealities require calibration during training
The practical challenge is that analog CMOS circuits and RRAM devices are not ideal: neuron and synapse time constants vary by ~30% across a chip, RRAM conductance levels drift due to relaxation and retention effects, and read-to-read noise introduces cycle-to-cycle fluctuations. Naively ignoring these non-idealities during training causes accuracy to collapse by more than 10% at inference time. We address this with a Neuromorphic Hardware Calibrated (NHC) training procedure, where device-level measurements of both circuit variability and RRAM conductance distributions are injected directly into the surrogate-gradient learning loop. The result is an SNN that self-corrects for its own substrate imperfections — matching full-precision software accuracy on MNIST, ECG arrhythmia classification, and spoken-digit recognition (SHD). Remarkably, the heterogeneity in neuron and synapse time constants improves accuracy on temporally structured tasks, since the spread of dynamics enriches the effective temporal representation of the network.

## Hardware-calibrated SNNs are energy efficient
We evaluated the energy cost of the full RRAM-based IMC system via SPICE-level simulations and compared it against DYNAP-SE, a state-of-the-art mixed-signal neuromorphic processor using Address-Event Representation (AER) for network connectivity. Across all three benchmarks, the RRAM-based SNN consumes more than one order of magnitude less energy per inference, with the gap driven by two compounding factors: the elimination of the AER routing overhead (which dominates DYNAP's energy budget) and the sparse row-access pattern of SNN computation, which minimizes the current drawn from the RRAM array during inference.

<p align="center">
  <img src="/images/Blog_Cosyne2026/NHC_energy.png" width="80%" alt="NHC energy efficiency"/>
</p>
<p align="center">
  <em>IMC-based SNNs, using RRAMs, are one order of magnitude more energy efficient than current neuromorphic systems, evaluated on three tasks (Electro-Cardiogram anomaly detection, Keyword spotting SHD, image recognition MNIST).</em>
</p>