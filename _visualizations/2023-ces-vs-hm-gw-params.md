---
title: 'Comparison of Calibration Methods for Gravity Wave Parameterization'
date: 2023-12-12
permalink: /visualizations/2023_ces_vs_hm_gw_params
excerpt: Work led by Rob King to compare calibration and uncertainty quantification techniques for a gravity wave parameterization
collection: visualizations
tags:
  - calibration
  - uncertainty quantification
  - emulators
  - gravity waves
  - parameterizations
---


------

This work was led by [Rob King](https://www.robertcking.com/), a grad student at Stanford University. 
We compare two calibration methods in the context of calibrating a gravity wave parameterization
in an intermediate complexity climate model, to obtain statistics of the Quasi-Biennial Oscillation (QBO) consistent with observations. 
It is a continuation of [my previous work that used Ensemble Kalman Inversion (EKI) to calibrate gravity wave parameters](https://lm2612.github.io/publication/2022-10-27-calibration-uncertainty-quantification). 
Rob has explored the use of history matching for the same task, to calibrate  the half-width of the distribution of phase speeds in the tropics ($c_w$) and the total gravity wave stress at the source level at the equator ($Bt_{eq}$). We consider two observables of the QBO: the period and amplitude at 10 hPa.
Both methods are iterative techniques, where we start with an ensemble of parameters sampled from a prior and at each iteration, we run an ensemble of climate model simulations to estimate the QBO period and amplitude. This is used to generate a new ensemble of parameters for the next iteration. 
In EKI, the ensemble at the next iteration is created by updating the parameter values for each ensemble member to minimize a loss function. However, in history matching, we rule out areas of the parameter space that are deemed implausible and sample new parameters from a sub-space which we call the "Not Yet Ruled Out" space.
The animation below shows how the ensemble members change at each iteration. 
Importantly, history matching has a slightly different goal, where it aims to learn a set of plausible parameters that could be consistent with observation. This is in contrast to EKI which is an optimization method and converges upon a single point estimate of parameters. 
You can see this in the animation below, where history matching samples converge upon an subspace of plausible parameters, while EKI samples converge upon a single point estimate.


---
<br/><img src='/images/visualizations/compare_hm_vs_eki.gif'>
---

Both methods have their merits: EKI converges more rapidly upon the optimal parameters. However, 
we find it can become stuck in local minima. In contrast, history matching may more suitable for obtaining a range of plausible parameters.
We hope to extend this work to consider the behavior of both methods in higher dimensional spaces. 
