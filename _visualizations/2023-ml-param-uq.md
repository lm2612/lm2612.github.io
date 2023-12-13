---
title: Uncertainty Quantification of a Machine Learning Parameterization'
date: 2023-12-12
permalink: /visualizations/2023_ml_param_uq
excerpt: Machine learning parameterizations are becoming a popular technique for improving climate models. This work aims to learn the uncertainties associated with them.
collection: visualizations
tags:
  - uncertainty quantification
  - machine learning
  - emulators
  - gravity waves
  - parameterizations
---

Uncertainty Quantification of Machine Learning Parameterization for Gravity Waves
------

This work was motivated by the rapid growth in machine learning parameterizations but with few 
studies carrying out uncertainty quantification (UQ). UQ is a key part of conventional parameterization development, that helps us assess the level of "trust" in a parameterization. 
I think it is important that we also consider UQ with machine learning parameterizations, especially
considering the black box nature of machine learning algorithms.

This work builds upon the machine learning emulator of a gravity wave parameterization developed by [Espinosa et al. (2022)](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2022GL098174).
Using the same model architecture, I trained an ensemble of neural networks, each initialized with a different seed. This allows us to estimate uncertainty in neural network predictions. The animation
below shows zonal and meridional gravity wave drag profiles, with the ground truth emulator in black,
the mean neural network prediction in red and the neural network uncertainty (1 standard deviation) in orange shading. 

---
<br/><img src='/images/visualizations/animation_GWDs_profile_mean_std_ensemble.gif'>
---
