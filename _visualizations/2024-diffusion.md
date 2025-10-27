---
title: 'Using Diffusion Models for Climate Data Downscaling'
date: 2024-05-01
permalink: /visualizations/2024_diffusion_downscaling
excerpt: We used generative diffusion models to sharpen coarse climate data over the U.S., showing they can recover fine-scale weather features and provide useful uncertainty estimates for risk analysis.
collection: visualizations
tags:
  - diffusion
  - downscaling 
  - machine learning
  - climate
---

Using Diffusion Models for Climate Data Downscaling 
------

Climate models are global simulations that divide the Earth into grid boxes, usually around 100–200 km across. They are great at capturing large weather systems, but due to their limited resolution, they blur out finer details like local wind patterns, cyclones, or temperature fronts. To bridge that gap, we can use <b>downscaling</b> - a process that takes coarse climate data and sharpens it to finer detail. It’s similar to “enhancing” a blurry image in computer vision.

In this study, we tried a generative machine learning model called diffusion for this task, since they have been gaining popularity in image generation (the same family used by tools like DALL·E or Stable Diffusion). Forward diffusion works by gradually adding noise to an image until it becomes pure Gaussian noise. The reverse of this involves removing noise from an image, step by step, until we recover realistic fine detail. Diffusion models work by learning the reverse diffusion process with a neural network. We tested whether this could help us generate fine-scale weather features. For this task, we need to also <i>condition</i> on an existing image, in other words, given this coarse-resolution climate image, what are the possible high-resolution states that could exist?

To do this, we used ERA5 reanalysis data, a high quality climate dataset that combines observations and models. We first coarse-grained ERA5 to a grid of 2° (around 200 km), and then trained the diffusion model to recover the original 0.25° (25 km) detail (an eightfold increase in resolution) over the continental U.S. We focused on three variables: near-surface temperature, zonal (east-west) winds and meridional (north–south) winds.

We compared our diffusion model against a standard U-Net, a well-known deep learning model often used for downscaling weather and climate data. The results were encouraging: while the U-Net already performed well, the diffusion model captured finer-scale structures more clearly, especially for wind patterns. You can see this in the first figure below, which compares the coarse input, the true high-resolution map, the U-Net prediction, and the diffusion result. The diffusion prediction shows more crisp fronts and gradients, giving a more realistic texture to the wind fields.

---
<br/><img src='/images/visualizations/diffusion_compare.png'>
---

Another major advantage of diffusion models is that they naturally produce ensembles - multiple plausible versions of the same forecast. This is valuable because it lets us estimate uncertainty. The GIF below shows several ensemble members for a single time snapshot, each slightly different but physically consistent. By taking the standard deviation across these members, shown in the last plot, we can highlight areas where the model is most uncertain, typically along strong temperature and wind gradients such as weather fronts. These uncertainty estimates could be especially useful for risk assessment and weather-related hazards.

---
<br/><img src='/images/visualizations/diffusion_ens_pred.gif'>
<br/><img src='/images/visualizations/diffusion_std.png'>
---


Overall, our results show that diffusion models can sharpen coarse climate data while also giving a measure of uncertainty, something traditional neural networks don’t easily provide. The approach is relatively simple and lightweight. You can read the full paper [here](https://arxiv.org/abs/2404.17752) or check out our code [here](https://github.com/robbiewatt1/ClimateDiffuse). We hope this encourages others to explore generative models like diffusion for climate and weather prediction.


Work by Laura Mansfield & Robbie Watt.

