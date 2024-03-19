+++
title = 'Adaptive Laser-Induced Phased Array inspections'
weight = 3
+++

# Introduction
Ultrasonic array inspections are usually impractical in highly hazardous environments where a trained operator cannot access physically to ensure good coupling and data are being acquired. Similarly, classical arrays need to find alternative coupling approaches when the geometry of the inspected specimen is irregular. Laser-induced phased-arrays (LIPAs) overcome these issues as it is a non-contact NDT technique that enable ultrasonic imaging in a similar fashion as classical phased-arrays [1].

<figure>
<img src="../media/exp_lipa.jpg" alt="Experimental setup of LIPA inspections" style="width:300px;"/>
<figcaption>Experimental setup of LIPA inspections [2].</figcaption>
</figure>

The main limitation currently is the acquisition time, which is highly dependent on hardware and is done sequentially for one detection and generation point at a time. In a full matrix capture, this configuration impacts significantly the efficiency of the method. Therefore, finding optimal configurations that minimise the measurement points is essential, and that is the main objective of this research line.

# Research work
The work addressed in this research area has focused on optimising the configuration of LIPAs for 1D inspections. This is based on the detection performance (trough ROC curves and SNR as proxy) of multiple candidate configurations (i.e. physical and computational aperture in addition to pitch). The developed methods in [2] consider the continuous case when inspecting large parts, specifically whereby the number of measurement points start to increase dramatically with the inspected distance (see figure below). The optimised array configurations can also be tailored depending on the type of target defect and size that needs to be inspected.

<figure>
<img src="../media/insp_lipa.jpg" alt="Inspection configuration for 1D LIPA inspections" style="width:500px;"/>
<figcaption>Inspection configuration for 1D LIPA inspections [2].</figcaption>
</figure>

Nowadays, the problem is being explored from 1D to 2D in order to enable inspections of large areas. This requires a step up in the theory and implementation so that 2D arrays can be optimised when considering continuous inspections.

This work is part of the ALIPA project primarily funded by the UK EPSRC.

# References
1. Stratoudaki, T., Clark, M. and Wilcox, P.D., 2016. Laser induced ultrasonic phased array using full matrix capture data acquisition and total focusing method. *Optics express*, 24(19), pp.21921-21938.
2. Cantero-Chinchilla, S., Croxford, A.J. and Wilcox, P.D., 2024. Optimising laser-induced phased-arrays for defect detection in continuous inspections. *NDT & E International*, p.103091.
