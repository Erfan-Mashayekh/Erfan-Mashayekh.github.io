---
title:  "Shock Vortex Interaction"
mathjax: true
layout: post
categories: media
---

## Introduction

For thirty years, researchers have devoted their efforts to expanding high-precision techniques aimed at capturing shock waves. One of these approaches, the high-order compact method, has demonstrated accuracy in handling such flows. However, a drawback lies in its tendency to oscillate across the computational field. Attempts have been made to improve this method, either through design modifications or increasing its formal order. The evaluation of these methods involves analyzing them in Fourier space and other approaches.

Another suggested approach involves combining low-dissipation schemes with shock-capturing methods around discontinuous regions, necessitating the identification of nonlinear features within the computational domain. These methods add a dissipation term through a post-processing step known as numerical filtering.  A second-order linear filter has proven effective for discontinuous regions (Visbal). Here, the challenge is establishing a shock detector that accurately distinguishes shocks from other gradients, specifically channeling shock-capturing dissipation solely to regions containing shocks.

Bogey et al. [14] used a sensor reliant on the high-frequency aspects of pressure to switch between optimized second-order and higher-order filters. In this study, the sensor developed by Darian is employed, featuring an advanced shock-detecting sensor for filtration in simulations. This sensor is designed to switch between second and higher-order filters based on an analysis of their order and smoothness. Additionally, it introduces a scaling method to handle large and small-scale errors differently by adjusting dissipation in proportion to shock strength while minimizing the impact of the second-order filter on very small scales.
