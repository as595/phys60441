---
layout: page
mathjax: true
permalink: /lecture/part1/
---

#### Wide-field Imaging

There are multiple effects that become important when making very wide-field interferometric images: non-coplanarity, primary beam rotation, direction-dependent phase calibration...
In this lecture we will focus on the first of these: non-coplanarity, otherwise known as the w-effect.

The structure of the lecture will be,

- an overview of the w-effect,
- various solutions to the w-effect, and
- worked examples.

The spatial coherence function measured by a radio interferometer is related to the spectral intensity as,

$$
V(u,v,w) = \int{\frac{I(l,m)}{\sqrt{1-l^2-m^2}} {\rm e}^{j 2\pi [ul + vm + w(\sqrt{1-l^2-m^2}-1)]}\,{\rm d}l{\rm d}m},
$$

where

 - $(l,m)$ are the direction cosines relative to the phase centre;
 - $I(l,m)$ is the spectral intensity at position $(l,m)$;
 - $(u, v, w)$ is the vector between the two interferometer elements expressed in units of wavelength;