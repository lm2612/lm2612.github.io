---
title: 'Calibration and Uncertainty Quantification of Gravity Wave Parameterization'
date: 2022-08-01
permalink: /visualizations/2022_ces_gw_params
tags:
  - calibration
  - uncertainty quantification
  - emulators
---

Calibration and Uncertainty Quantification of Gravity Wave Parameterization
======

In my 2022 paper, we calibrate a gravity wave parameterization to obtain climate model statistics 
consistent with observations. The gravity wave parameters are the half-width of the distribution of 
phase speeds in the tropics (c_w) and the total gravity wave stress at the source level at the equator (Bt_eq).
We calibrate to two observables of the Quasi-Biennial Oscillation (QBO): the period and amplitude at 10 hPa.
For calibration, we use Ensemble Kalman Inversion (EKI), a gradient-free optimization method. We start with 
an ensemble of climate model simulations, with parameter values sampled from a prior distribution, and iteratively update 
the parameters until the QBO observables are consistent with observations. The animation below shows the 
evolution of the gravity wave parameters (top two panels) and the QBO observables (lower two panels).

---
title: "Calibration using Ensemble Kalman Inversion"
excerpt: "Evolution of ensembles for parameters (top) and observables (bottom)<br/><img src='/images/visualizations/pm_EKI.gif'>"
collection: visualizations
---

Then, we carried out uncertainty quantification, using Markov chain Monte Carlo (MCMC). We cannot regularly sample 
from the full climate model due to the high computational cost. However, using the ensembles of simulations generated
in the calibration stage, we can build a Gaussian process emulator, which we can use for quick sampling. The figures 
below shows the behavior of the GP emulator with gravity wave parameters on the x- and y- axis for the QBO period (left) and 
amplitude (right). The points indicate MCMC samples, which are selected to be consistent with observations (including
uncertainty).

---
title: "Gaussian process emulator" 
excerpt: "Gaussian process emulator for QBO period (left)and amplitude (right) for different parameter choices. Samples are generated using MCMC. <br/><img src='/images/visualizations/gwparams_sampling.gif'>"
collection: visualizations
---

The animation below shows how these samples create a 2d posterior distribution of gravity wave parameters.
 
---
title: "Samples of posterior distribution"  
excerpt: "MCMC samples of posterior distribution, generated using the Gaussian process emulator above. <br/><img src='/images/visualizations/gwparams_posterior.gif'>"
collection: visualizations
---
