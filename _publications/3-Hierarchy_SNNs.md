---
title: "The Role of Temporal Hierarchy in Spiking Neural Networks"
collection: publications
category: manuscripts
permalink: /publication/2024_Hierarchy_of_timescales_SNNs
#excerpt: 'This paper is about the number 2. The number 3 is left for future work.'
date: 2024-07-26
venue: 'ArXiv'
paperurl: 'https://arxiv.org/html/2407.18838v1'
citation: 'F. Moro et al. (2024). &quot;The Role of Temporal Hierarchy in Spiking Neural Networks.&quot; <i>ArXiv</i>. 1(2).'
---

---

## Drawing inspiration from cortical features
The mammalian cortex is organized as a hierarchy of time scales: neural activity becomes progressively slower from sensory to association areas, a pattern observed consistently across species. Whether this property is merely a biological curiosity or carries genuine computational benefits for artificial systems is an open question. We investigate this through Spiking Neural Networks (SNNs), which are uniquely suited for this study: as biologically inspired models with inherent temporal dynamics, SNNs offer multiple mechanisms for computing in time, including neuronal time constants, synaptic delays, and recurrent connectivity — each offering a distinct "knob" for controlling the speed of temporal processing across layers.

<p align="center">
  <img src="/images/Blog_Cosyne2026/TH_SNN_F1.png" width="90%" alt="TH_SNN_F1"/>
</p>
<p align="center">
  <em>The hierarchy of time-scales is reproduced in SNNs leveraging neuronal dynamics, delays and recurrent connections. The hypotheses are that the hierarchy is both a positive inductive bias and an emerging property from optimization.</em>
</p>

## Two hypotheses
We formulate two hypotheses. First, that temporal hierarchy acts as a useful inductive bias: initializing SNNs with a structured progression of time scales — fast in early layers, slow in deeper ones — should improve classification accuracy over a reference model with homogeneous time constants. Second, that temporal hierarchy emerges naturally from optimization: when time constants are left free to be learned via backpropagation, gradient descent should discover a hierarchical arrangement on its own, without any explicit prior.


<p align="center">
  <img src="/images/Blog_Cosyne2026/TH_SNN_time_constants.png" width="90%" alt="TH_SNN_time_constants"/>
</p>
<p align="center">
  <em>The experiments in a keyword spotting task, forming a hierarchy of time constants in SNNs, show the positive effect of such Inductive Bias on task performance.</em>
</p>

## The benefits of Temporal Hierarchy
Both hypotheses are confirmed. As an inductive bias, a hierarchy of time constants and synaptic delays yields accuracy gains of 2–6% on keyword spotting and multi-timescale tasks, with the benefit most pronounced in smaller networks — reducing the required parameter count by up to 5× for the same target accuracy. In the optimization setting, gradient descent reliably discovers a fast-to-slow progression of time constants and recurrent eigenvalues across layers, confirming that temporal hierarchy is not merely a useful prior but a naturally preferred solution when learning temporal tasks. Together, these results establish temporal hierarchy as a principled and transferable architectural feature for efficient SNN design, with direct implications for resource-constrained neuromorphic computing.