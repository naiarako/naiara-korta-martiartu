---
layout: page
title: Anisotropy
description: Speed-of-sound anisotropy in muscle
img: /assets/img/anisotropy.png
importance: 1
category: current
---

The velocity of ultrasound longitudinal waves (speed of sound) is emerging as a valuable biomarker for a wide range of diseases, including musculoskeletal disorders. Muscles are fiber-rich tissues that exhibit anisotropic behavior, meaning that velocities vary with the wave-propagation direction. Quantifying anisotropy is therefore essential to improve velocity estimates while providing a new metric that relates to both muscle composition and architecture. In this work, we present a novel method to estimate the anisotropy of longitudinal ultrasound waves in transversely isotropic tissue. Until now, only shear waves have been used to characterize tissue anisotropy in clinical applications. However, shear and longitudinal waves interrogate fundamentally different mechanical tissue properties. Their propagation velocities differ by three orders of magnitude, resulting in decoupled relationships between the two velocities and elastic moduli. Hence, this work not only complements other studies on the topic but is pivotal to characterize mechanical tissue properties comprehensively.

We assume elliptical anisotropy and consider an experimental setup that includes a flat reflector located in front of the linear probe. The probe-reflector distance is controlled by a sensor. This setup allows us to measure first-arrival reflection traveltimes and has already been used in various clinical studies. Unknown muscle parameters are the orientation angle of the anisotropy symmetry axis and the velocities along and across this axis.

<div class="row justify-content-center">
    <div class="col-sm-9 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/setup_anisotropy.png' | relative_url }}" alt="" title="Experimental setup"/>
    </div>
</div>
<div class="caption">
    Schematic representation of the anisotropic medium and experimental setup considered in this study. (a) Wavefronts in elliptical anisotropic media are ellipsoidal. Parameters \(v_1\) and \(v_2\) represent velocities along and across muscle fibers, and \(\varphi\) describes the orientation of fibers with respect to the coordinate system. In an arbitrary propagation direction \(\theta\) connecting \(\mathbf{x}_\text{A}\) and \(\mathbf{x}_\text{B}\), waves propagate with velocity \(v_\theta = v(\theta)\). (b) Our experimental setup includes a flat reflector in front of the probe, with tissue in between. The probe-reflector distance \(L\) is controlled by a sensor. We measure first-arrival reflection traveltimes of ultrasound signals emitted from \(\mathbf{x}_\text{S}\) and received at \(\mathbf{x}_\text{R}\), with \(\mathbf{x}_\text{P} \in \mathcal{D}\) indicating the reflection point.
</div>

In a medium with elliptical anisotropy, the velocity in any arbitrary location $$v(\theta)$$ satisfies

\begin{equation}
\label{eq:Ellipse}
\frac{v^2(\theta)}{v^2_1} \sin^2{(\theta-\varphi)} + \frac{v^2(\theta)}{v^2_2}
\cos^2{(\theta-\varphi)} = 1,
\end{equation}

where the variables are described in the figure above. Using trigonometric identities, we find that the traveltime $$t_\text{AB}$$ between positions $$\mathbf{x}_\text{A}$$ and $$\mathbf{x}_\text{B}$$ is given by

\begin{equation}
t^2_\text{AB} = \frac{1}{v^2_1}\left[\cos{\varphi} - \sin{\varphi} \right]^2.
\end{equation}

\begin{equation}
t^2_\text{AB} = \frac{1}{v^2_1}\left[(x_{1,\text{B}}-x_{1,\text{A}})\cos{\varphi} - (x_{2,\text{B}}-x_{2,\text{A}})\sin{\varphi} \right]^2+ \frac{1}{v^2_2}\left[(x_{1,\text{B}}-x_{1,\text{A}})\sin{\varphi} + (x_{2,\text{B}}-x_{2,\text{A}})\cos{\varphi}\right]^2.
\end{equation}

For an experimental setup that includes a reflector located at distance $$L$$ from the probe, we can measure the first-arrival reflection traveltimes and use them to retrieve muscle anisotropy. Using Fermat's principle, we can find that, in this anisotropic medium, the reflection point will be shifted from the mid-point between the source $$\mathbf{x}_\text{S}$$ and receiver $$\mathbf{x}_\text{R}$$. This shift is a constant value, independent of the source and receiver location. The reflection point $$\mathbf{x}_\text{P}$$ is 

\begin{equation}
\label{eq:reflect_point}
\mathbf{x}_{\text{P}}^{\text{min}} = \left(\frac{x_{1,\text{S}} +
x_{1,\text{R}}}{2} + \frac{L\sin2\varphi(v_2^2 - v_1^2)}{2(v_1^2 \sin^2\varphi + v_2^2 \cos^2\varphi)}, L \right),
\end{equation}

where $$x_1$$ indicates the first component of $$\mathbf{x}$$. We can make interesting observation from this equation: 

(1) The reflection point is located at the source-receiver midpoint only when the medium is isotropic ($$v_1=v_2$$) or the anisotropy symmetry axis is aligned with our coordinate system ($$\varphi = 0$$).

(2) The path with the minimum traveltime satisfies $$t_\text{SP} \left(\mathbf{x}_\text{P}\right)= t_\text{RP}\left(\mathbf{x}_\text{P}\right)$$. Therefore, the fastest ray path is the path with equal traveltime along each segment.

(3) The mirror image of the receiver, namely a virtual equivalent receiver $$\tilde{R}$$ below the reflector, is located at $$\mathbf{x}_{\tilde{\text{R}}} = 2\mathbf{x}_\text{P}$$.

Upon inserting the expression for $$\mathbf{x}_\text{P}$$ in the calculation of the the first-arrival reflection traveltime between $$\mathbf{x}_\text{S}$$ and $$\mathbf{x}_\text{R}$$, we obtain

\begin{equation}
\label{eq:ttt_total}
t_\text{SR}^2 =
\frac{d^2}{v^2(\theta = \pi/2)} + \frac{4L^2
v^2(\theta = \pi/2)}{v_1^2 v_2^2},
\end{equation}
with $$v^2(\theta = \pi/2)$$ being the velocity in direction $$\pi/2$$ and $$d = x_{1,\text{R}} - x_{1,\text{S}}$$ being the source-receiver offset. 
