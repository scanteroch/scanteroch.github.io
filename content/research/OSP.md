+++
title = 'Optimal sensor placement'
weight = 5
+++

# Introduction
This research line focuses on the optimisation of sensor location for a given objective, which might be defect detection, damage localisation, or characterisation. In particular, I am interested in incorporating uncertainty quantification along the way to obtain the most robust locations that can manage some level of noise. This problem not only need to provide the most informative locations but also the optimal number of sensors, which introduces an economic problem such that when adding more sensors, more hardware, software and data management costs are added. Although the methods that I have developed are quite generic and applicable to many other domains, I have worked on guided-wave based structural health monitoring (SHM). Therefore, the sensors that are optimised are of the form of PZT discs.

# Approaches
## Value of information
The first alternative approach that I have developed is based on the value of information [1,2]. The value of information gives a mathematically rigorous tool to compare different sensor configurations (including location and number of sensors) and determine the value of implementing the candidate configurations. The cost/benefit is defined here as a hybrid between the amount of information (through the distance of two probability density functions) that is acquired by a configuration along with the cost of adding the sensors.

The problem can account for uncertainties stemming from identifiable parameters (e.g. coordinates of the damage) and nuisance parameters that do not need to be identified (e.g. wave speed velocity). By exploring the effect of different parameters and optimisation algorithms in the output, one can be confident in the results that the method provides, which are explainable and mathematically consistent.

<figure>
<img src="../media/osp_voi.jpg" alt="Comparison of three sensor layouts (optimal and suboptimal) along with their reconstruction results" style="width:500px;"/>
<figcaption>Comparison of three sensor layouts (optimal and suboptimal) along with their reconstruction results [1].</figcaption>
</figure>

## Information entropy
The second approach that I developed was based on the information entropy [3]. This method relies on several hypotheses and simplifications that make the problem able to be solved analytically by standard minimisation algorithms in Matlab or Python. The key assumption is the relaxation of binary variables considered for the location (either a sensor is or is not "activated"), which makes the optimisation problem and the objective function convex.

This contribution enables a strong reduction in computational time as everything (location and number) can be solved at once. This method is flexible and can be adapted and implemented in different platforms relatively easily. A base code is provided both in MATLAB and Python [4] to optimise PZT for damage localisation in metallic and composite plates. This is to evaluate the performance and adapt it and extend it to other applications.

<figure>
<img src="../media/osp_cnv.jpg" alt="Optimal configuration of sensors and actuators in a composite plate" style="width:500px;"/>
<figcaption>Optimal configuration of sensors and actuators in a composite plate [3].</figcaption>
</figure>

# Research work
Research work in this area will look at different problems (ultrasonic NDE, eddy currents, etc.). In addition, for the information entropy, the estimation of the entropy without many of the assumptions involve expensive calculations of probabilistic evidences. However, a more accurate estimate of the entropy could be obtained in this manner. Efficient avenues to obtain these quantities will also be explored.

# References
1. Cantero‐Chinchilla, S., Papadimitriou, C., Chiachío, J., Chiachío, M., Koumoutsakos, P., Fabro, A.T. and Chronopoulos, D., 2022. Robust optimal sensor configuration using the value of information. *Structural Control and Health Monitoring*, 29(12), p.e3143.
2. Cantero-Chinchilla, S., Chiachío, J., Chiachío, M., Chronopoulos, D. and Jones, A., 2020. Optimal sensor configuration for ultrasonic guided-wave inspection based on value of information. *Mechanical Systems and Signal Processing*, 135, p.106377.
3. Cantero-Chinchilla, S., Beck, J.L., Chiachío, M., Chiachío, J., Chronopoulos, D. and Jones, A., 2020. Optimal sensor and actuator placement for structural health monitoring via an efficient convex cost-benefit optimization. *Mechanical Systems and Signal Processing*, 144, p.106901.
4. Cantero-Chinchilla, S., Beck, J.L., Chiachío, J., Chiachío, M. and Chronopoulos, D., 2021. OptiSens—Convex optimization of sensor and actuator placement for ultrasonic guided-wave based structural health monitoring. SoftwareX, 13, p.100643.
