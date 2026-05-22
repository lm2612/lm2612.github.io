---
title: 'Uncertainties in weather and climate modelling'
date: 2025-10-01
permalink: /visualizations/2025_UQ_models
excerpt: What uncertainties are there in weather and climate models? 
collection: visualizations
tags:
  - uncertainties
  - atmospheric modelling
  - chaos
  - weather 
  - climate
---

Where Do Weather and Climate Uncertainties Come From?


------

Uncertainty quantification is a crucial part of weather and climate prediction. Even with the best models, forecasts can never be perfect because the Earth system is **chaotic**, meaning tiny changes can grow quickly. This leads to the limit of predictability. But as well as this, the underlying physics is not fully understood, so we cannot perfectly represent every process inside a model.

In physics, we generally categorise uncertainty into two main types: 
- **Aleatoric uncertainty** comes from randomness in nature itself - the things we can’t predict because they’re inherently variable, like the exact path of a thunderstorm or the timing of a gust of wind.  
- **Epistemic uncertainty** comes from our limited knowledge - how we build models, choose parameters, or represent unresolved processes. It reflects things we could reduce if we had better data or understanding that could lead to better modelling choices.

In the machine learning world, these same ideas apply: aleatoric uncertainty comes from noisy data, while epistemic uncertainty comes from the model’s parameters and structure. In weather and climate science, these ideas map onto the traditional uncertainty framework used for decades.

For example, in **weather forecasting**, uncertainty mostly comes from small errors in the initial state of the atmosphere (aleatoric) and from simplifications in how we represent unresolved processes (epistemic). For **climate projections**, we care less about the exact initial state and more about how model structure and parameters affect the long-term averages we simulate.

Here’s how the different types of uncertainty fit together across weather and climate timescales:

| Timescale         | Type of Uncertainty in GCMs | Aleatoric | Epistemic | Typical Approach |
|-------------------|-----------------------------|------------|------------|------------------|
| **Weather**       | Initial Condition            | ✅         |            | Perturbed initial condition ensemble |
| **Weather**       | Subgrid Variability (informs parameterisations) | ✅ |  | Stochastic parameterisation |
| **Seasonal–Decadal** | Internal Variability      | ✅         |            | Perturbed initial condition ensemble |
| **All Timescales**| Structural Uncertainty       |            | ✅         | Multi-model ensemble |
| **Climate**       | Parametric Uncertainty       |            | ✅         | Perturbed parameter ensemble |
| **Climate**       | Scenario Uncertainty         |            | ✅         | Multi-scenario ensemble |

Each row shows a source of uncertainty, whether it’s mainly aleatoric (randomness) or epistemic (lack of knowledge), and how we typically represent it in models. For example, **stochastic parameterisations** inject random variability into small-scale processes, while **perturbed parameter ensembles** explore how changes in model parameters affect long-term climate outcomes.

Understanding both kinds of uncertainty is crucial. Aleatoric uncertainty helps capture the range of possible short-term weather outcomes, while epistemic uncertainty helps us understand how confident we are in our models themselves. In our next post, we’ll show how we can represent both of these using **Bayesian Neural Networks**, which naturally combine the two frameworks and help us better quantify uncertainty across weather and climate prediction.


------

