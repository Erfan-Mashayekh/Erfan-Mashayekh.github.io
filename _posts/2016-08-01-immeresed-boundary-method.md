---
title:  "A Numerical Solution for Two-Dimensional Compressible Flow with a High-order Compact Finite Difference Scheme using Immersed Boundary method"
mathjax: true
layout: post
categories: media
---

![Desnity Contours](/images/ibm_contours_top.png)


## Introduction

Engineering, medical, and environmental applications of flow problems often demand resolving complicated solid-fluid interactions. A finite difference method is a convenient tool for exploring these problems. One of the most popular choices for spatial discretization is the cartesian grid as they have clearly expressed stencils and are typically simple to generate at a low computation cost. This research project describes a cartesian model based on the ghost cell immersed boundary method accompanying a high-order numerical approach to simulate viscous compressible flows with arbitrary boundaries. The idea is to combine fourth-order compact finite difference schemes with a direct forcing approach of the immersed boundary method. Moreover, a nonlinear filter with an associated sensor was used to ensure the damping of the high-frequency waves in smooth regions and also the disappearance of Gibbs oscillations around the discontinuities while using high-order compact finite difference schemes.

## Immersed Boundary Method

[Immersed Boundary Methods](https://en.wikipedia.org/wiki/Immersed_boundary_method) (IBMs) are numerical techniques used in fluid dynamics simulations to handle interactions between solid boundaries or obstacles and a fluid flow. These methods allow for the simulation of complex geometries without requiring a specific mesh conforming to the shape of the obstacle. Instead, they utilize an Eulerian grid that does not conform to the boundaries of the solid objects.

This thesis employed the approach developed by [Takahashi et al.](https://doi.org/10.1155/2014/252478) to implement boundary conditions on cartesian grids. The application of an immersed boundary method notably showcased a high level of accuracy in achieving global convergence, particularly in the context of supersonic flows. This thesis’ findings present a promising advancement in resolving complex flow problems, particularly in scenarios demanding precise estimations and analysis.

In this approach, the boundary is defined using the level set method, which establishes a level set function across nodes as the signed distance from the object boundary. This method efficiently computes the normal vector based on a gradient operation from the object surface. 

Using the level set function, nodes are categorized into three groups: fluid, ghost, and object depicted in the figure. The ghost nodes act as a protective boundary between the fluid and object regions, being assigned in two layers based on the current definition.

$$ d_{Fp} > 0, \quad  -2 \sqrt{2} \Delta x \leq d_{Gp} \leq 0, \quad d_{Op} < -2 \sqrt{2} \Delta x $$

<img src="/images/ibm_ibm.jpg" alt="Picture" width="500" style="display: block; margin: 0 auto" />

## Results

The study conducts simulations on two distinct flow fields. The first scenario involves supersonic flow over a circular cylinder, yielding promising estimations of shock waves and the flow patterns around the cylinder. The second test case focuses on simulating subsonic flow around a similar cylinder to evaluate mechanics in the wake region and the phenomenon of vortex shedding. Across these test cases, the Mach number 2 and 0.3 respectively, while maintaining a Reynolds number of 300. Notably, the estimation of force coefficients shows a correct order of magnitude for the subsonic case.

The application of an immersed boundary method notably showcased a high level of accuracy in achieving global convergence, particularly in the context of supersonic flows. This thesis’ findings present a promising advancement in resolving complex flow problems, particularly in scenarios demanding precise estimations and analysis.

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