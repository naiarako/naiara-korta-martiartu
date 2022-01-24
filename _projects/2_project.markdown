---
layout: page
title: USCT - design
description: Optimal Experimental Design methods for USCT
img: /assets/img/design_USCT.png
importance: 1
category: past
---

There are mainly two classes of USCT devices depending on the data coverage they provide: 

(1) Two-dimensional (2D) devices arrange the transducers in a plane (e.g., in a ring-shape transducer holder) and produce a set of 2D breast images at different elevations. This arrangement is useful to reduce the dimension of the physical problem and speed-up the image reconstruction process. It also enables the use of sophisticated tomographic methods (explicitly solving the wave equation) that otherwise would be computationally prohibitive to implement. However, fast reconstructions neglect the three-dimensional nature of the wave propagation (e.g., out-of-plane scattering) and thereby introduce artifacts in the final images. 

(2) Three-dimensional (3D) devices arrange transducers in a semispherical setup and are able to provide volumentric tissue images at the expense of a higher acquisition and computational cost. Currently, this cost does not allow the implementation of advanced tomographic methods and limits significantly the spatial resolution of final images. 



<div class="row justify-content-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/2D&3DUSCT.png' | relative_url }}" alt="" title="USCT devices"/>
    </div>
</div>
<div class="caption">
Example of 2D (left) and 3D (right) ultrasound computer tomography devices. Image sources: <a href = "https://journals.lww.com/investigativeradiology/Fulltext/2017/06000/Ultrasound_Tomography_Evaluation_of_Breast.4.aspx" target="_blank">2D</a> and <a href="http://ipeusctdb1.ipe.kit.edu/~usct/challenge/?page_id=92" target="_blank">3D</a>
</div>


My work on USCT has been focused on transferring knowledge from seismology to medical imaging in order to improve currect acquisition setups and tomographic algorithms. More details can be found in my [Ph.D. thesis](https://www.research-collection.ethz.ch/handle/20.500.11850/416172).

<h4> Optimal experimental design </h4>

