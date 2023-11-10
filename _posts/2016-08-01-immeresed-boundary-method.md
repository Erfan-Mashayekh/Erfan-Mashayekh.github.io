---
title:  "A Numerical Solution for Two-Dimensional Compressible Flow with a High-order Compact Finite Difference Scheme using Immersed Boundary method"
mathjax: true
layout: post
categories: media
---

![Pressure Contours](/images/shockvortex_contours.png)


## Introduction

Engineering, medical, and environmental applications of flow problems often demand to resolve complicated solid-fluid interactions. A finite difference method is a convenient tool for exploring these problems. One of the most popular choices for spatial discretization is the Cartesian grid as they have clearly expressed stencils and typically simple to generate at a low computation cost. This paper describes a Cartesian model based on ghost cell immersed boundary method accompanying a high order numerical approach to simulate viscous compressible flows with arbitrary boundaries. The idea is to combine fourth-order compact finite difference schemes with a direct forcing approach of the immersed boundary method. Moreover, a nonlinear filter with an associated sensor was used to assure the damping of the high-frequency waves in smooth regions and also disappearing of Gibbs oscillations around the discontinuities while using high-order compact finite difference schemes. Two flow fields were simulated. The first test case was a supersonic flow over a circular cylinder, with the results providing good estimations of the shock wave and also the flow around the cylinder. The second test case was the simulated subsonic flow around a circular cylinder. This case was selected to estimate the wake region mechanics and vortex shedding. In the test cases, the Mach number varies from 0.3 to 2, and the Reynolds number is 300. It was observed that the estimation of the force coefficients did not result in any troubles. As a result, in supersonic flow, a high-accuracy global convergence achieved when an immersed boundary was applied.

## Results

This problem is a two-dimensional test case that describes the interaction between a stationary shock and a vortex. This study uses a 4th-order compact finite difference scheme to simulate this interaction. To remove the high-frequency oscillations the adaptive filtering method developed by [Darian et al.](https://doi.org/10.1016/j.jcp.2010.09.028) is employed.

![Pressure Contours](/images/shockvortex_contours.png)

### Required Skill-Set to generate these results:

- C++
- CFD
- Immersed Boundary method
- Adaptive filtering
- Compact finite difference methods
- Compressible flow
- Supersonic flow
- Validation