---
title:  "Shock Capturing Using Adaptive Spatial Filtering"
mathjax: true
layout: post
categories: media
---

## Introduction

For thirty years, researchers have devoted their efforts to expanding high-precision techniques aimed at capturing shock waves. One of these approaches, the high-order compact method, has demonstrated accuracy in handling such flows. However, a drawback lies in its tendency to oscillate across the computational field. Attempts have been made to improve this method, either through design modifications or increasing its formal order. The evaluation of these methods involves analyzing them in Fourier space and other approaches.

Another suggested approach involves combining low-dissipation schemes with shock-capturing methods around discontinuous regions, necessitating the identification of nonlinear features within the computational domain. These methods add a dissipation term through a post-processing step known as numerical filtering.  [Visbal et al.](https://doi.org/10.2514/6.2005-1265) proved that a second-order linear filter is effective for discontinuous regions. Here, the challenge is establishing a shock detector that accurately distinguishes shocks from other gradients, specifically channeling shock-capturing dissipation solely to regions containing shocks.

[Bogey et al.](https://doi.org/10.1016/j.jcp.2008.10.042) used a sensor reliant on the high-frequency aspects of pressure to switch between optimized second-order and higher-order filters. In this study, the sensor developed by [Darian et al.](https://doi.org/10.1016/j.jcp.2010.09.028)  is employed, featuring an advanced shock-detecting sensor for filtration in simulations. This sensor is designed to switch between second and higher-order filters based on an analysis of their order and smoothness. Additionally, it introduces a scaling method to handle large and small-scale errors differently by adjusting dissipation in proportion to shock strength while minimizing the impact of the second-order filter on very small scales.

## Shock-vertex interaction

This problem is a two-dimensional test case that describes the interaction between a stationary shock and a vortex. This study uses a 4th-order compact finite difference scheme to simulate this interaction. To remove the high-frequency oscillations the adaptive filtering method developed by [Darian et al.](https://doi.org/10.1016/j.jcp.2010.09.028) is employed.


A stationary shock with a Mach number of 1.1 is located at x = 0.5 and perpendicular to the x-axis. Its left state is defined as $$ (\rho, u, v, p)=(1, 1.1\sqrt{\gamma}, 0, 1) $$, while the right state is determined using the normal-shock (Rankine–Hugoniot) relations. Additionally, a small vortex is introduced into the flow preceding the shock, centered at $$ (x_c , y_c ) = (0.25, 0.5) $$. This vortex affects the mean flow's velocity $$ (u, v)$$, temperature $$ (T = p/q)$$, and entropy $$(s = \ln{p / \rho ^ \gamma})$$ as perturbations, represented by the hat values.

$$ \hat{u} = \epsilon \taw e^{\alpha (1-\taw ^ 2)} \sin(\theta) $$



