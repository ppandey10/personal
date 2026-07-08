---
title: Research
---

This page highlights two research directions: my current work on [Aging and Longevity](#aging-and-longevity), and my previous MSc research in [Gravitational Waves](#msc-thesis).

## Aging and Longevity

Over the past few months, I have been working with [Dr. Mark Olenik](https://donertas-group.github.io/people/) and [Dr. Melike Dönertaş](https://www.leibniz-fli.de/research/research-groups/associated-research-groups/d%C3%B6nertas-group) on a project aimed at understanding the stochastic nature of aging.

Chronological age simply measures the time elapsed since birth. Aging, however, refers to the progressive decline in biological function that increases vulnerability to disease and death. Quantifying this process, often described as estimating an individual’s biological age, is central to understanding age-related diseases and designing interventions that promote healthy longevity. One widely used framework for this purpose is the concept of an aging clock.

A key open question in the development of aging clocks is whether aging is fundamentally deterministic or whether it emerges from stochastic, cumulative molecular changes over time[^1]. Our work addresses this question by developing a dynamical model of DNA methylation that explicitly incorporates stochasticity. The goal is to understand how variability accumulates across CpG sites and how this accumulation gives rise to measurable age acceleration in individuals.

By combining mechanistic modeling with statistical learning approaches, we aim to bridge the gap between molecular-level noise and population-level aging patterns.

## MSc Thesis

I built a machine-learning surrogate to speed up gravitational-wave waveform generation for binary neutron star mergers.

Extracting physical source parameters from a detected GW signal requires sampling the posterior probability distribution over a high-dimensional parameter space. Each likelihood evaluation involves generating an accurate waveform model that simulates the signal emitted by a compact binary system. In practice, analyzing a single event can require tens of millions of waveform evaluations, making waveform generation the dominant computational bottleneck.

This challenge will intensify with next-generation detectors such as [Einstein Telescope](https://www.et-gw.eu/) and [Cosmic Explorer](https://cosmicexplorer.org/), which are expected to detect orders of magnitude more events than current facilities like [LIGO](https://www.ligo.caltech.edu/) and [Virgo](https://www.virgo-gw.eu/). Improving waveform generation speed is therefore essential to fully exploit the scientific potential of upcoming large-scale GW experiments.

A promising strategy is the construction of machine-learning-based surrogate models that emulate expensive waveform generators. While significant progress has been made for binary black hole systems, binary neutron stars (BNS) present additional complexity due to tidal effects, matter interactions, and richer waveform structure.

Building upon the published `mlgw_bns` framework, I developed [`mlgw_bns_HOM`](https://github.com/ppandey10/mlgw_bns_HOM), a neural-network-based surrogate model designed to accelerate the generation of Effective-One-Body (EOB) waveforms for binary neutron stars.

My contributions focused on:

- Incorporating **higher-order modes** beyond the dominant quadrupole emission
- Extending the model to include **spin-precession effects**
- Ensuring robust generalization across the relevant parameter space

This work contributes to enabling scalable Bayesian inference for future high-rate GW observations.

[^1]: Issa J. P. (2014). Aging and epigenetic drift: a vicious cycle. *The Journal of Clinical Investigation*, 124(1), 24–29. https://doi.org/10.1172/JCI69735
