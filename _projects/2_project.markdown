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

The goal of USCT is to estimate the acoustic tissue parameters $$\mathbf{m}$$ from the observations of the ultrasound signals $$\mathbf{d}$$ that are recorded by an experimental setup $$\mathbf{s}$$.
We can express the physical model relating our observations with unknown tissue properties as
$$\mathbf{F}$$ as

\begin{equation}
\mathbf{d} = \mathbf{F}(\mathbf{m};\mathbf{s}) + \epsilon,
\end{equation}
where $$\mathbf{F}$$ is the forward operator encoding our physical model, and $$\epsilon$$ accounts for measurement noise. In USCT, the nonlinearities of $$\mathbf{F}$$ with respect to $$\mathbf{m}$$ are not too severe, and we typically use linearized forward operators with respect to some prior knowledge about tissue $$\mathbf{m}_\text{prior}$$:

\begin{equation}
\mathbf{F}(\mathbf{m};\mathbf{s}) \approx \mathbf{F}(\mathbf{m}_\text{prior};\mathbf{s}) +  \mathbf{F}'(x),
\end{equation}

\begin{equation}
\mathbf{F}(\mathbf{m};\mathbf{s}) \approx \mathbf{F}(\mathbf{m}_\text{prior};\mathbf{s}) +  \mathbf{F}'(\mathbf{m};\mathbf{s})\rvert_{\mathbf{m} = \mathbf{m}_\text{prior}}(\mathbf{m} - \mathbf{m}_\text{prior}), 
\end{equation} 

For such linearized problems, we can compute the posterior covariance operator $$\Gamma_\text{post}$$. This operator contains the uncertainties in tissue properties that we expect post-reconstruction and is expressed as

\begin{equation}
\Gamma_\text{post}(\mathbf{s}) = 
\left( {\mathbf{F}'(\mathbf{s})}^{T} \Gamma_\text{noise}^{-1}\mathbf{F}'(\mathbf{s}) + \Gamma_\text{prior}^{-1}\right)^{-1}.
\end{equation}

Here, $$\Gamma_\text{noise}$$ and $$\Gamma_\text{prior}$$ are the covariance operator of measurements noise and our prior knowledge about tissue properties, respectively, which we assume to be Gaussian. $$\Gamma_\text{post}$$ shows useful properties to measure the quality of an experimental configuration. First, it depends on the parameters that define the experimental setup $$\mathbf{s}$$. This allows us to compare different candidates and select the ones that give the lowest uncertainties in the parameter estimation. Second, it neither depends on the observations nor the unknown model parameters, which means that it could be used to optimize the experiment before any realization. Last, it shows the same structure for any forward operator, under the condition that these are linear or can be linearized with respect to the model parameters. This allows us to present general formulations of the OED problem, independent of the tomographic method that is intended to be applied post-acquisition. 

Assume that $$\Theta$$ is a scalar function that quantifies the level of expected uncertainties in the parameters by extracting some properties from $$\Gamma_\text{post}$$. Then, we can formulate the OED problem as a minimization problem

\begin{equation}\label{eq:OED}
\min_{\mathbf{s} \in \mathcal{S}}  \Theta \left(\Gamma_\text{post}\right),
\end{equation}

where $$\mathcal{S}$$ represents the space for all possible experimental configurations. In our work, we define $$\Theta$$ as the determinant of the posterior covariance matrix

\begin{equation}\label{eq:D-optLog}
\Theta = \log \det \left(\Gamma_\text{post} \ \right).
\end{equation}

The determinant corresponds to the product of the eigenvalues of $$\Gamma_\text{post}$$, and thus, we minimize the volume of the uncertainty ellipsoid in the estimated tissue parameters. From information theory, this quantity can be related to the expected information gain.

