---
layout: page
title: USCT - design
description: Optimal Experimental Design methods for USCT
img: /assets/img/design_USCT.png
importance: 1
category: past
---

There are mainly two classes of USCT devices depending on the data coverage they provide (see examples in figure below):

(1) Two-dimensional (2D) devices arrange the transducers in a plane (e.g., in a ring-shaped transducer holder) and produce a set of 2D breast images at different elevations. This arrangement is helpful to reduce the dimension of the physical problem and speed up the image reconstruction process. It enables us to use sophisticated tomographic methods (numerically solving the wave equation) that otherwise would be computationally prohibitive to implement. However, fast reconstructions neglect the three-dimensional nature of the wave propagation (e.g., out-of-plane scattering) and introduce artifacts in the final images, reducing their accuracy.

(2) Three-dimensional (3D) devices arrange transducers in a semispherical setup and can provide volumetric tissue images at the expense of a higher acquisition and computational cost. Currently, this cost does not allow the implementation of advanced tomographic methods and significantly limits the spatial resolution of final images.


<div class="row justify-content-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/2D&3DUSCT.png' | relative_url }}" alt="" title="USCT devices"/>
    </div>
</div>
<div class="caption">
Example of 2D (left) and 3D (right) ultrasound computer tomography devices. Image sources: <a href = "https://journals.lww.com/investigativeradiology/Fulltext/2017/06000/Ultrasound_Tomography_Evaluation_of_Breast.4.aspx" target="_blank">2D</a> and <a href="http://ipeusctdb1.ipe.kit.edu/~usct/challenge/?page_id=92" target="_blank">3D</a>
</div>


As we see, USCT designs and tomographic methods are interrelated. My work has focused on developing Optimal Experimental Design (OED) approaches to find the optimal configuration of transducers for commonly applied image reconstruction methods. We define the optimal setup as the configuration of transducers that reduces most uncertainties of reconstructed images post-acquisition. More details can be found in my [Ph.D. thesis](https://www.research-collection.ethz.ch/handle/20.500.11850/416172).

<h4> Optimal experimental design </h4>

The goal of USCT is to estimate the acoustic tissue parameters $$\mathbf{m}$$ from the observations of the ultrasound signals $$\mathbf{d}_\text{obs}$$ that are recorded by an experimental setup $$\mathbf{s}$$.

