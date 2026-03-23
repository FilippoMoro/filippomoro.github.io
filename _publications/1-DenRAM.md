---
title: "DenRAM: neuromorphic dendritic architecture with RRAM for efficient temporal processing with delays"
collection: publications
category: manuscripts
permalink: /publication/DenRAM
#excerpt: 'This paper is about the number 1. The number 2 is left for future work.'
date: 2024-04-24
venue: 'Nature Communications'
paperurl: 'https://www.nature.com/articles/s41467-024-47764-w#Abs1'
citation: #'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
---

---

## Taking inspuration from dendritic arbors
Biological neurons are far more computationally powerful than the simplified "point neuron" models commonly used in artificial neural networks. A key yet often overlooked contributor to this power is the **dendritic tree**: the branching structure through which neurons receive their inputs. Dendrites do not merely relay spikes passively — they introduce **propagation delays** that allow a neuron to detect temporal correlations across its inputs, a mechanism known as coincidence detection. Inspired by this principle, we present **DenRAM**, a neuromorphic feed-forward spiking neural network architecture that explicitly incorporates dendritic compartments and synaptic delays, enabling rich spatio-temporal processing without the need for recurrent connections.

<p align="center">
  <img src="/images/Blog_Cosyne2026/DenRAM.png" width="90%" alt="DenRAM - Dendritic architecture with delays"/>
</p>
<p align="center">
  <em>DenRAM mimics dendritic arbors with synaptic elements that delay and weigh input spikes, converging to an output Leaky-Integrate-and-Fire neuron.</em>
</p>

## The DenRAM architecture
To realize delays and synaptic weights compactly on chip, DenRAM leverages **Resistive RAM (RRAM)**, an emerging non-volatile memory technology integrated on top of a 130 nm CMOS process. Each dendritic circuit uses two RRAM devices per synapse: one sets the RC time constant that controls the propagation delay, while the other modulates the synaptic weight. Because RRAM devices are non-volatile and consume zero static power, this design minimizes both **area footprint** and **leakage power** compared to purely active analog or digital delay implementations. Crucially, DenRAM exploits the natural device-to-device variability of RRAM to provide a rich spectrum of delays across the dendritic array, turning hardware heterogeneity from a challenge into a computational asset.

We benchmark DenRAM on two representative edge-computing tasks: **ECG heartbeat anomaly detection** and **keyword spotting** on the Spiking Heidelberg Digits dataset. On the heartbeat task, DenRAM achieves 95.3% accuracy with only 16 parameters — **35× fewer parameters** than an iso-accuracy spiking recurrent neural network (SRNN) — and consumes **5× less power** (5.30 nW vs. the equivalent SRNN). On the keyword spotting task, DenRAM reaches up to 87.5% accuracy under realistic RRAM noise conditions, consistently outperforming recurrent architectures with the same parameter budget. Together, these results demonstrate that dendritic delays are a powerful and hardware-friendly inductive bias for temporal sequence processing.
