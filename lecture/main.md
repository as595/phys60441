---
layout: page
mathjax: true
permalink: /lecture/main
---


<h3 id="wide-field-imaging"> Wide-field Imaging </h3>

There are multiple effects that become important when making very wide-field interferometric images: non-coplanarity, primary beam rotation, direction-dependent phase calibration...

In this lecture we will focus on the first of these: non-coplanarity, otherwise known as the w-effect.

The structure of the lecture will be,

- an overview of the w-effect,
- various solutions to the w-effect, and
- worked examples.

#### Visibility Equation

The spatial coherence function measured by a radio interferometer is related to the spectral intensity as,

$$
V(u,v,w) = \int{\frac{I(l,m)}{\sqrt{1-l^2-m^2}} {\rm e}^{j 2\pi [ul + vm + w(\sqrt{1-l^2-m^2}-1)]}~{\rm d}l{\rm d}m},
$$

where

 - $ (l,m) $ are the direction cosines relative to the phase centre;
 - $ I(l,m) $ is the spectral intensity at position $(l,m)$;
 - $ (u, v, w) $ is the vector between the two interferometer elements expressed in units of wavelength.

This is more often referred to as the *visibility equaton*.

The $w$-term in this equation is the final part of the exponent: $w(\sqrt{1-l^2-m^2}-1)$. In the case where $w(\sqrt{1-l^2-m^2}-1) \ll 1$ then we can ignore it completely and the visibility equation becomes:

$$
V(u,v) = \int{\frac{I(l,m)}{\sqrt{1-l^2-m^2}} {\rm e}^{j 2\pi [ul + vm]}~{\rm d}l{\rm d}m},
$$

which is just a 2d Fourier transform. 

However if $w(\sqrt{1-l^2-m^2}-1) \ge 1$ then we can't use a 2d Fourier transform without suffering from aberration effects. 

#### The w-effect

So what happens if we do use a 2d transform?

Let's look at the visibility equation again, but separating the w-term in the exponent:

$$
V(u,v,w) = \int{\frac{I(l,m)}{\sqrt{1-l^2-m^2}} {\rm e}^{j 2\pi [ul + vm]} {\rm e}^{j 2\pi w(\sqrt{1-l^2-m^2}-1)}~{\rm d}l{\rm d}m}.
$$

We can see that $w$ is only used in the exponent, which means that ${\rm e}^{j 2\pi w(\sqrt{1-l^2-m^2}-1)}$ is purely a phase term, i.e. ${\rm e}^{j \phi}$.

However, the phase is *position-dependent*:

$$\phi(l,m,w).$$

Effectively every visibility with a different $w$-value sees a different sky - and, since the $w$-value changes as a function of time, the measured sky is time-variable. 

Consequently, if we ignore the $w$-term and do a 2d Fourier transform then we will see image distortions. 

#### Why are the sources distorted like that?

The distortions that we see have a quite characteristic shape, like a double "U". This is a consequence of $w$ not truly being independent of $(u,v)$. In fact we can write $W$ as:

$$
w = u \sin \chi \tan Z - v \cos \chi \tan Z,
$$

where

 - $\chi$ is the *parallactic angle*, and
 - $Z$ is the *zenith angle*.

These angles are defined by the relationship between the local coordinate frame and the celestial coordinate frame and can be defined as:

$$ \tan \chi = \frac{\sin H}{\cos \delta \tan \phi - \tan \delta \cos H},$$
$$ \cos Z = \sin \phi \sin \delta + \cos \phi \cos \delta \cos H,$$

where

 - $H$ is the local *Hour Angle* of the celestial source,
 - $\delta$ is the declination of the celestial source, and
 - $\phi$ is the latitude of the telescope on the Earth.

Using the expression $w = u \sin \chi \tan Z − v \cos \chi \tan Z$, we can re-write the visibility equation as

$$
V(u,v) = \int{\frac{I(l,m)}{\sqrt{1-l^2-m^2}} {\rm e}^{j 2\pi [ul' + vm']}~{\rm d}l{\rm d}m},
$$

where

$$
l′=l+\sin \chi \tan Z ( \sqrt{1−l^2−m^2} −1)
$$

$$
m′=m−\cos \chi \tan Z ( \sqrt{1−l^2−m^2} −1)
$$
