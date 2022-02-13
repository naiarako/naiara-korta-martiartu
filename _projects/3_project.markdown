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
\label{eq:ttt}
\begin{split}
t^2_\text{AB} =
\frac{1}{v^2_1}\left[(x_{1,\text{B}}-x_{1,\text{A}})\cos{\varphi} -
(x_{2,\text{B}}-x_{2,\text{A}})\sin{\varphi} \right]^2+
\\\frac{1}{v^2_2}\left[(x_{1,\text{B}}-x_{1,\text{A}})\sin{\varphi} +
(x_{2,\text{B}}-x_{2,\text{A}})\cos{\varphi}\right]^2.
\end{split}
\end{equation}
 
