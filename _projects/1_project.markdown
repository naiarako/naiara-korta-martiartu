---
layout: page
title: USCT
description: Ultrasound Computed Tomography (USCT) for breast imaging
img: /assets/img/Sensitivity_kernel_1event.png
importance: 1
category: past
---

Ultrasound computed tomography (USCT) is an emerging technique to image acoustic tissue properties. USCT scanning systems were originally developed for early breast cancer detection. They consist of a water tank in which the patient submerges the breast. The sidewalls of the water tank are equipped with ultrasound transducers that emit and record ultrasonic waves propagating through the tissue. In this way, USCT is able to record both reflected and transmitted waves, which are essential to provide high-resolution quantitative images comparable to MRI. This is a significant improvement compared to traditional sonography techniques, where the gray-scale images are mainly qualitative. Quantitative images allow radiologists to discriminate between different tissue types and diagnose lesions more objectively.

My work on USCT has been focused on transferring knowledge from seismology to medical imaging in order to improve currect acquisition setups and tomographic algorithms. More details can be found in my [Ph.D. thesis](https://www.research-collection.ethz.ch/handle/20.500.11850/416172).

<h4> Optimal experimental design </h4>



<h4> Finite-frequency tomography </h4>

Typical devices include high-frequency transducers, which makes tomography techniques based on numerical wave propagation simulations computationally challenging, especially in 3D. Therefore, despite the finite-frequency nature of ultrasonic waves, ray-theoretical approaches to transmission tomography are still widely used. In this work, we have introduced finite-frequency traveltime tomography to medical ultrasound. In addition to being computationally tractable for 3D imaging at high frequencies, the method has two main advantages:

(1) It correctly accounts for the frequency dependence and volumetric sensitivity of traveltime measurements, which are related to off-ray-path scattering and diffraction (see Figure XX). 

(2) It naturally enables out-of-plane imaging and the construction of 3D images from 2D slice-by-slice acquisition systems (see Figure XX).

This method minimizes cross-correlation traveltime shifts between the observations and calibration data in water, being internally consistent with the standard procedure of traveltime estimations. Moreover, the availability of calibration data in water allows us to provide analytical expressions of cross-correlation traveltime sensitivity, which define our forward operator.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/1.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/3.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/Sensitivity_kernel_1event.png' | relative_url }}" alt="" title="Sensitivity of finite-frequency traveltimes"/>
    </div>
</div>
<div class="caption">
    Figure XX: Example of sensitivity of finite-frequency traveltimes. It corresponds to a band-limited signal with frequencies in the range of 1–3 MHz. The emitter and the receiver are located at positions (-95,0,0) mm and (95,0,0) mm, respectively. The dashed line indicates the corresponding sensitivity predicted from ray theory.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal it's glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/" target="_blank">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
```
