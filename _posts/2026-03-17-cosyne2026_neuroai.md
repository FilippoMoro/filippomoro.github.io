---
title: "Three Levels of Biological Inspiration: Bridging NeuroAI and Neuromorphic Engineering"
collection: talks
type: "Conference proceedings talk"
permalink: /talks/2026-03-17-Cosyne2026_NeuroAI
date: 2026-03-21
location: "Lisbon, PT"
tags: [neuromorphic, neuroai, cosyne, spiking-neural-networks, biological-inspiration]
layout: single
---

Artificial Intelligence is advancing at ever increasing speed, learning from massive data and running in huge datacenters. Modern AI does not look much like biological intelligence. So what role does neuroscience play in the context of AI? This question was at the center of a recent workshop organized at Cosyne 2026: "Biologically-Inspired Artificial Intelligence". Here I show my perspective on this intriguing research question, structuring inspiration from biology into three distinct levels: mechanical, system-level, and behavioral. As a neuromorphic engineer, I am used to working at the mechanical level, replicating the biophysics of neurons and synapses with electronics. However, I see great opportunities to work at a higher level of abstraction by drawing inspiration from biological computation. This hints at the unification of NeuroAI with Neuromorphic Computing.

---

I had the fantastic opportunity to speak at [Cosyne 2026](https://www.cosyne.org/), in the workshop on [*Biologically-Inspired Artificial Intelligence*](https://sites.google.com/view/cosyne-neuroai/). Cosyne is one of the leading conferences in (computational) neuroscience, and it was my first time attending it. The community is creative, welcoming, and genuinely curious about the deep questions at the intersection of biology and computation. Being an engineer surrounded by computational neuroscientists for a few days was as humbling as inspiring.

## What Role Does Neuroscience Play in the Age of AI?

It is hard to ignore that AI is advancing at a pace that would have seemed implausible just a few years ago. Large language models are reshaping the concept of intelligence and, notably, do not look much like brains. Backpropagation through deep networks, attention mechanisms, and massive parallelism on GPU clusters are a long way from local plasticity, spike-timing-dependent learning, and the roughly 20 watts of power consumed by the human brain.

So what role does neuroscience play in this context? Is biological inspiration still a useful guide for building intelligent systems, or has it become more of an aesthetic preference?

As a neuromorphic engineer, I share some of these same tensions. Neuromorphic computing has historically drawn deep inspiration from biology, often at the level of mimicking individual neurons and synapses. But as the gap between neuromorphic hardware and state-of-the-art AI grows wider, it becomes worth asking: are we drawing the right kind of inspiration?

---

## Three Levels of Biological Inspiration

I find it useful to distinguish between three levels, which map onto different parts of the stack of engineering intelligence — from devices and circuits all the way up to applications and algorithms.

<p align="center">
  <img src="/images/Blog_Cosyne2026/Three_Level_BioInspiration.jpg" width="70%" alt="Three levels of biological inspiration: mechanical, system, and behavioral"/>
</p>
<p align="center">
  <em>Curtesy of Melika Payvand</a>.</em>
</p>

### 1. Mechanical Level

The mechanical level is about faithfully mimicking the biophysics of neural computation: the dynamics of individual neurons, synapses, axons, and dendrites. This is where traditional neuromorphic engineering has lived, designing circuits that reproduce the biophysical dynamics of real neurons, memristive devices that implement synaptic plasticity, or architectures that implement dendritic compartmentalisation.

The mechanical level asks: *can we build hardware that replicates the physics of biological computation?*

### 2. System Level

The system level takes a step up. Here, we adopt the machinery of machine learning — artificial neural networks and backpropagation — but inject biological *system-level* features: heterogeneity across neurons, functional specialization of different brain areas, sparse connectivity, modularity, or principles like neurogenesis. We are not trying to replicate the biophysics; we are asking whether the *organisational principles* of biological neural systems make our artificial ones better.

The system level asks: *can biological organizational principles improve the function of artificial networks?*

### 3. Behavioral Level

The behavioral level draws inspiration from how brains *act*, rather than how they are built. This is closest to classical AI: designing systems that exhibit intelligent behaviors — perception, decision-making, creativity — observed in animals, without necessarily caring about the underlying substrate.

---

## Where Neuromorphic and NeuroAI Currently Live

Neuromorphic engineering has traditionally operated at the **mechanical level**, while NeuroAI has worked mainly between the **system** and **behavioral** levels. But I believe both fields have much to gain from moving across this hierarchy, forming a synergy.

This is exactly the direction my lab — the [Emergent Intelligent Substrates (EIS) Lab](https://esl.epfl.ch/research/the-eis-lab/), led by Prof. Melika Payvand — has been pursuing.

---

## What We Work On

### Mechanical Level: Dendritic Delays

Dendrites exhibit a rich repertoire of computational primitives, one of which is the **propagation delay** of pre-synaptic stimuli as they travel toward the soma. This delay is a form of temporal memory built directly into the morphology of the neuron.

<p align="center">
  <img src="/images/Blog_Cosyne2026/DenRAM.png" width="90%" alt="DenRAM - Dendritic architecture with delays"/>
</p>
<p align="center">
  <em>DenRAM mimics dendritic arbors with synaptic elements that delay and weigh input spikes, converging to an output Leaky-Integrate-and-Fire neuron.</a>.</em>
</p>

In **DenRAM** ([D'Agostino, Moro et al., *Nature Communications* 2024](https://www.nature.com/articles/s41467-024-57108-x)), we built a neuromorphic hardware architecture that uses Resistive RAM (RRAM) to implement dendritic delays with ultra-low power consumption. Delay-based spiking networks turn out to be significantly more efficient than recurrent models: we demonstrated a **5× reduction in power** and up to a **35× reduction in memory footprint** on ECG anomaly detection and keyword spotting benchmarks.

One limitation of DenRAM was that we did not train the delays — we fixed them. This motivated **DelGrad** ([Göltz, Weber, Kriener et al., *Nature Communications* 2025](https://www.nature.com/articles/s41467-025-57628-w)), an algorithm that derives exact, event-based gradients for both synaptic weights *and* delays in spiking networks. DelGrad is compatible with LIF neurons and has been validated on neuromorphic hardware (BrainScaleS), where training axonal delays reduces test error meaningfully even under the noise of analog hardware.

Together, DenRAM and DelGrad make the case that the mechanical richness of dendrites — specifically, their temporal structure — is a powerful computational resource.

### System Level: Heterogeneous Memory, Temporal Hierarchy, and Neurogenesis

Moving up the hierarchy, we have been working on how biological system-level principles can improve artificial networks trained with backpropagation.

<p align="center">
  <img src="/images/Blog_Cosyne2026/System_level.png" width="90%" alt="System-level of biological inspiration"/>
</p>
<p align="center">
  <em>In the system-level of biological inspuration, we leverage machine-learning computational mechanisms in conjunction with high-level features of biological computations.</a>.</em>
</p>

**mGRADE** ([Torchet et al., *arXiv* 2025](https://arxiv.org/abs/2507.01829)) combines two ideas: the minimal gated recurrent unit (minGRU) for processing slow temporal dynamics, and dilated convolutions with learnable spacings (DCLS) for capturing fast temporal features. The result is a deep recurrent network with **heterogeneous memory** — inspired by the fact that brains exhibit heterogeneous strategies for memory formation. mGRADE achieves state-of-the-art performance on the Long Range Arena benchmark and on raw-audio keyword spotting, while being the only architecture in its class small enough to fit on common microcontrollers.

**Temporal Hierarchy in SNNs** ([Moro et al., *arXiv* 2024](https://arxiv.org/abs/2407.18838)) investigates whether the hierarchy of intrinsic timescales observed in the mammalian cortex — where deeper cortical areas process information over longer timescales — is also useful as an inductive bias in artificial spiking networks. The answer is yes: imposing a structured gradient of time constants across hidden layers consistently improves performance on temporal tasks, and interestingly, this hierarchy *also emerges spontaneously from optimization* when networks are trained on sequential data.

**GroHess** takes inspiration from adult hippocampal neurogenesis — the brain's ability to grow new neurons as a mechanism for continual learning — and implements a biologically-motivated artificial counterpart. Using information-geometry-based triggers (effective dimensionality and Fisher saturation metrics), the algorithm decides *when* and *where* to grow new neurons, and initialises them orthogonally to the existing representations to minimise interference. On both Split MNIST and Permuted MNIST, GroHess achieves better performance with smaller final models than static baselines.

---

## Looking Ahead: A Synergy Worth Pursuing

I believe the future of both fields lies in their convergence.

**NeuroAI** would benefit from engaging more seriously with neuromorphic hardware. Energy-efficient substrates impose structure that may turn out to be a feature rather than a limitation: sparse connectivity, modular networks and local learning rules are all biologically motivated and increasingly attractive from an engineering standpoint.

**Neuromorphic engineering** needs to break free from an exclusive focus on the mechanical level. The most impactful near-term opportunities may lie in the system level: using the organizational principles of biological brains — hierarchy of time-scales, heterogeneous dynamics, modular connectivity — to build systems that are simultaneously more efficient and more functional.

The question is how to make it happen. I hope that conversations like the one we had at this workshop are a step in that direction.

---

*Filippo Moro is a Postdoc in the [EIS Lab](https://esl.epfl.ch/research/the-eis-lab/) at UZH and ETH Zurich, led by Prof. Melika Payvand. His research sits at the intersection of neuromorphic hardware, spiking neural networks, and biologically-inspired machine learning.*
