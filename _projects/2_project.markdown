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
Example of 2D (left) and 3D (right) ultrasound computer tomography devices. Image sources: <p><a href = https://journals.lww.com/investigativeradiology/Fulltext/2017/06000/Ultrasound_Tomography_Evaluation_of_Breast.4.aspx>2D</a></p> and <p><a href=http://ipeusctdb1.ipe.kit.edu/~usct/challenge/?page_id=92>3D</a></p> 
</div>


USCT is able to record both reflected and transmitted waves, which are essential to provide high-resolution quantitative images comparable to MRI. This is a significant improvement compared to traditional sonography techniques, where the gray-scale images are mainly qualitative. Quantitative images allow radiologists to discriminate between different tissue types and diagnose lesions more objectively.

My work on USCT has been focused on transferring knowledge from seismology to medical imaging in order to improve currect acquisition setups and tomographic algorithms. More details can be found in my [Ph.D. thesis](https://www.research-collection.ethz.ch/handle/20.500.11850/416172).

<!--<h4> Optimal experimental design </h4>-->


<h4> Finite-frequency tomography </h4>

Typical devices include high-frequency transducers, which makes tomography techniques based on numerical wave propagation simulations computationally challenging, especially in 3D. Therefore, despite the finite-frequency nature of ultrasonic waves, ray-theoretical approaches to transmission tomography are still widely used. In this work, we have introduced finite-frequency traveltime tomography to medical ultrasound. In addition to being computationally tractable for 3D imaging at high frequencies, the method has two main advantages:

(1) It correctly accounts for the frequency dependence and volumetric sensitivity of traveltime measurements, which are related to off-ray-path scattering and diffraction. 

<div class="row justify-content-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/Sensitivity_kernel_1event.png' | relative_url }}" alt="" title="Sensitivity of finite-frequency traveltimes"/>
    </div>
</div>
<div class="caption">
    Example of sensitivity of finite-frequency traveltimes. It corresponds to a band-limited signal with frequencies in the range of 1–3 MHz. The emitter and the receiver are located at positions (-95,0,0) mm and (95,0,0) mm, respectively. The dashed line indicates the corresponding sensitivity predicted from ray theory.
</div>

(2) It naturally enables out-of-plane imaging and the construction of 3D images from 2D slice-by-slice acquisition systems.


<div class="row justify-content-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/FFtomo_3Drec.png' | relative_url }}" alt="" title="3D reconstruction"/>
    </div>
</div>
<div class="caption">
    3D velocity reconstruction using the dataset provided by the Spanish National Research Council (CSIC) and the Complutense University of Madrid (UCM) as part of the <a href="http://ipeusctdb1.ipe.kit.edu/~usct/challenge/?page_id=183">SPIE USCT Data Challenge 2017</a>. We simulate a slice-by-slice acquisition, and we assume that the same data have been recorded at different elevationss. We show in each case the lateral view, the isolated view of the inclusions and the cross section at z = 0 mm. The red line indicates the position of the cross section.
</div>

Finite-frequency tomography minimizes cross-correlation traveltime shifts between the observations and calibration data in water, being internally consistent with the standard procedure of traveltime estimations. Moreover, the availability of calibration data in water allows us to provide analytical expressions of cross-correlation traveltime sensitivity, which define our forward operator.
To improve computational efficiency, we develop a memory-efficient implementation by encoding the Jacobian (forward) operator with a 1D parameterization. This parameterization is independent of the emitter-receiver geometry and allows us to efficiently extend the method to large-scale domains using massively parallelized operations on GPU architectures. 


<div class="row justify-content-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/FFtomo_parameterization.png' | relative_url }}" alt="" title="Parameterization"/>
    </div>
</div>
<div class="caption">
Cross section of the 3D sensitivity kernel (a) with and (b) without including geometrical spreading. (c) Sensitivity kernel in (b) represented as a function of distances indicated in (b) with dashed lines between the positions of the emitter \(\mathbf{x}_s\), receiver \(\mathbf{x}_r\), and an arbitrary spatial location \(\mathbf{x}\).
</div>


