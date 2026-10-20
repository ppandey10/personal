---
title: Research
---

This page covers two research directions: my current work on [Aging and Longevity](#aging-and-longevity) and my previous MSc research in [Gravitational Waves](#msc-thesis).

## Aging and Longevity

I am working with [Dr. Mark Olenik](https://donertas-group.github.io/people/) and [Dr. Melike Dönertaş](https://www.leibniz-fli.de/research/research-groups/associated-research-groups/d%C3%B6nertas-group) on the regulation and stochasticity of aging.

People of the same chronological age can differ substantially in their molecular profiles and biological function. **What drives these differences? Do molecular systems lose their capacity to maintain stable states, do stochastic influences grow stronger, or do both processes contribute?** 

I build mathematical models that connect these divergences with transcriptomic data, turning them into testable hypotheses about how regulation and noise shape diverse aging trajectories.

## MSc Thesis

I built a machine-learning surrogate to speed up gravitational-wave waveform generation for binary neutron star mergers.

The detection of a gravitational-wave signal involves inferring the physical parameters of its source such as masses, spins, tidal deformabilities etc. by sampling a posterior distribution over a high-dimensional parameter space. The bottleneck is that each likelihood evaluation requires an accurate waveform, and a single event can demand tens of millions of them. 

This challenge of faster waveform generation will only grow with the next-generation detectors like [Einstein Telescope](https://www.et-gw.eu/) and [Cosmic Explorer](https://cosmicexplorer.org/) which are expected to observe orders of magnitude more events than current facilities like [LIGO](https://www.ligo.caltech.edu/) and [Virgo](https://www.virgo-gw.eu/).

For my MSc thesis, I developed [`mlgw_bns_HOM`](https://github.com/ppandey10/mlgw_bns_HOM), a surrogate for Effective-One-Body (EOB) waveforms of BNS systems, building on the `mlgw_bns` framework. 

My contributions focused on:

- Incorporating higher-order modes beyond the dominant quadrupole emission
- Extending the model to include spin-precession effects
- Ensuring robust generalization across the relevant parameter space

This work contributes to enabling scalable Bayesian inference for future high-rate GW observations.