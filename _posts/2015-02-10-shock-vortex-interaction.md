---
title:  "Shock Capturing Using Adaptive Spatial Filtering"
mathjax: true
layout: post
categories: media
---

![Pressure Contours](/images/shockvortex_contours.png)


## Introduction

For thirty years, researchers have devoted their efforts to expanding high-precision techniques aimed at capturing shock waves. One of these approaches, the high-order compact method, has demonstrated accuracy in handling such flows. However, a drawback lies in its tendency to oscillate across the computational field. Attempts have been made to improve this method, either through design modifications or increasing its formal order. The evaluation of these methods involves analyzing them in Fourier space and other approaches.

Another suggested approach involves combining low-dissipation schemes with shock-capturing methods around discontinuous regions, necessitating the identification of nonlinear features within the computational domain. These methods add a dissipation term through a post-processing step known as numerical filtering.  [Visbal et al.](https://doi.org/10.2514/6.2005-1265) proved that a second-order linear filter is effective for discontinuous regions. Here, the challenge is establishing a shock detector that accurately distinguishes shocks from other gradients, specifically channeling shock-capturing dissipation solely to regions containing shocks.

[Bogey et al.](https://doi.org/10.1016/j.jcp.2008.10.042) used a sensor reliant on the high-frequency aspects of pressure to switch between optimized second-order and higher-order filters. In this study, the sensor developed by [Darian et al.](https://doi.org/10.1016/j.jcp.2010.09.028)  is employed, featuring an advanced shock-detecting sensor for filtration in simulations. This sensor is designed to switch between second and higher-order filters based on an analysis of their order and smoothness. Additionally, it introduces a scaling method to handle large and small-scale errors differently by adjusting dissipation in proportion to shock strength while minimizing the impact of the second-order filter on very small scales.

## Shock-vertex interaction

This problem is a two-dimensional test case that describes the interaction between a stationary shock and a vortex. This study uses a 4th-order compact finite difference scheme to simulate this interaction. To remove the high-frequency oscillations the adaptive filtering method developed by [Darian et al.](https://doi.org/10.1016/j.jcp.2010.09.028) is employed.


A stationary shock with a Mach number of $$ 1.1 $$ is located at $$ x = 0.5 $$ and perpendicular to the $$ x $$-axis. Its left state is defined as $$ (\rho, u, v, p)=(1, 1.1\sqrt{\gamma}, 0, 1) $$, while the right state is determined using the normal-shock (Rankine–Hugoniot) relations. Additionally, a small vortex is introduced into the flow preceding the shock, centered at $$ (x_c , y_c ) = (0.25, 0.5) $$. This vortex affects the mean flow's velocity $$ (u, v)$$, temperature $$ (T = p/q)$$, and entropy $$(s = \ln{p / \rho ^ \gamma})$$ as perturbations, represented by the hat values.

$$ \hat{u} = \epsilon \tau e^{\alpha (1-\tau ^ 2)} \sin(\theta) $$,

$$ \hat{v} = -\epsilon \tau e^{\alpha (1-\tau ^ 2)} \cos(\theta) $$,

$$ \hat{T} = -\frac{(\gamma-1) \epsilon^2 e^{2 \alpha (1 - \tau^2)}}{4 \alpha \gamma} $$, and $$ \hat{s}=0 $$.

where $$ \tau = r/r_c$$ and $$ r = \sqrt{ (x - x_c)^2 + (y - y_c)^2 } $$ and the angle $$ \theta $$ is measured with reference to the vortex core $$ (x_c , y_c )$$. Here, $$ \epsilon $$ indicates the strength of the vortex, $$ \alpha $$ controls the decay rate of the vortex, and $$ r_c $$ is the critical radius for which the vortex has  the maximum strength. Similar to [Darian et al.](https://doi.org/10.1016/j.jcp.2010.09.028) we take the computational domain to be $$ [0, 2] \times [0, 1]$$ and also $$ \epsilon = 0.3 $$, $$ r_c = 0.05 $$, and  $$ \alpha = 0.204 $$.

The figure displays the pressure distribution along $$ y = 0.5 $$ section at $$ t = 0.6 $$ before and after the shock. These results are derived from a grid of dimensions $$ [ 251 \times 101 ] $$ and leverage a constant time-step of $$ \Delta t = 0.001 $$. The results have a good agreement with [Darian et al.](https://doi.org/10.1016/j.jcp.2010.09.028) pressure values.

![Pressure Dist](/images/shockvortex_pressuredist.png)
