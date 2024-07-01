+++
title = 'Probabilistic SHM'
weight = 4
+++

# Introduction
Structural health monitoring (SHM) usually encompasses the different stages that form a monitoring strategy, namely continuous monitoring, damage detection, damage localisation and characterisation. SHM also arguably addresses the prediction of the remaining useful life of a structure, which is part of what is known as Prognostics and Health Management given that it involves maintenance policy about when to carry out inspections or replace a part based on the actual condition of the structure (or condition-based maintenance). The fundamental difference with respect to NDE is that SHM is performed continuously in time - i.e. there is a continuous monitoring of the structural health state.

In the condition-based maintenance paradigm, the quantification of uncertainties is crucial in order to make informed decisions based on probabilities. In this research line, I have developed Bayesian probabilistic methods to address all the stages of SHM. Furthermore, SHM can be carried out using a variety of testing techniques such as vibration methods, visual inspection methods or ultrasonic testing. The latter is particularly interesting for industries with high-value structures with thin-like structures such as the aerospace industries. Most of my work in this area is generic and transferrable to any other testing technique, but has been proved on ultrasonic guided-waves or through-transmission ultrasound - given its weight lightness, penetration power, low attenuation and cheap implementation costs.


# Damage detection
This is probably the most important of all the SHM stages. Reliably and efficiently detecting incipient forms of damage is crucial to ensure safe operation of any engineering asset. Making a prompt decision about an indication of a defect is crucial and hard to perform on complex data such as guided waves. The approach I developed in this area [1] accounts for significant differences in the shape of guided-waves as a result of any external interaction with the structure. It uses fuzzy logic principles to provide information about the peaks of a signal being shifted by applying a probability density function like fuzzy set to each signal peak. This technique in itself may be prone to false negatives, but the potential lies in the use of massive sets of signals coming from different test configurations such as physical beamforming or full matrix capture. Moreover, one can use statistics to track the degradation of a structure and construct a degree of health indicator which can match the damage in itself as demonstrated in a fatigue test and shown in the figure below.

<figure>
<img src="../media/DoH.png" alt="Degree of Health (DoH) comparison against crack length." style="width:500px;"/>
<figcaption>Degree of Health (DoH) comparison against crack length in a fatigue test of an aluminium plate [1].</figcaption>
</figure>

# Damage localisation
Once damage is detected, the next stage in the SHM process is to locate it and isolate it in order to make decisions - e.g. if it falls within a safety-critical area, the part can be replaced without further investigation. Nonetheless, accounting for uncertainties in the process of signal processing is important given the differences in applying these techniques. For example, if a baseline extraction method is being applied, usually the arrival time of the first wave packet in the guided wave is extracted to tract the arrival time. An ellipse-based geometrical model can then be used to extract the damage location. The processing approach to extract the arrival time, e.g. through time-frequency transforms, inevitably introduces epistemic uncertainties stemming from mathematical assumptions when building such techniques. These uncertainties can be systematically accounted for when inferring the damage location. In fact, if the uncertainties of all processing models are added, one can make a hyper-robust estimation of the damage location, accounting for multiple uncertainties. This leads to more accurate and complete identification of damage locations as shown below in comparison with a deterministic optimisation method (genetic algorithms (GA)).

<figure>
<img src="../media/localisation.jpg" alt="Comparison between deterministic and Bayesian approaches" style="width:500px;"/>
<figcaption>Comparison between a deterministic damage localization using GA (grey point) and the results obtained with the Bayesian approach [2].</figcaption>
</figure>

I have developed other Bayesian approaches for localising damage based on physics-based guided wave propagation models and others for resonant metamaterial beams, which you can check in my [Scholar](https://scholar.google.com/citations?user=UzQ8jtwAAAAJ&hl=en).

# Damage characterisation
The next stage in the SHM ladder is to characterise the defect severity. This is usually through characterising the shape and type (e.g. crack of 3mm). To tackle this problem, I have developed multiple multilevel Bayesian approaches whereby the damage is quantified (e.g. Young's modulus reduction) and characterised (e.g. how many layers in a composite layup are damaged). Depending on the nature of the problem, the problem of characterising the type of damage can be computationally expensive if many options can be considered; hence, computational strategies that avoid the calculation of every combination in a full-grid search are considered, such as greedy algorithms whereby only one entity (damage mode, sensor location, etc.) is considered at a time. This was proven computationally efficient when performing damage characterisation in post-impact fatigue composite specimens, whereby the damage pattern can be formed of any combination of layer and interface in the specimen.

<figure>
<img src="../media/Bayesian.jpg" alt=" Bayesian IP framework at the three hierarchical levels" style="width:500px;"/>
<figcaption>Bayesian IP framework at the three hierarchical levels [3].</figcaption>
</figure>

The multilevel Bayesian approach for inverse problems is a very powerful technique for inferring damage characteristics as long as a damage model is available that is not computationally very heavy to compute. This would require the use of a data-driven surrogate model and/or the use of approximate Bayesian methods to reduce the usage of the physics model itself. I have worked in multiple characterisation approaches in the context of probabilistic SHM, which you can check in my [Scholar](https://scholar.google.com/citations?user=UzQ8jtwAAAAJ&hl=en).

# Research work

The work I am leading in this area is nowadays driven by the integration of neural networks in the inverse problem - e.g. surrogate models of the physics models and surrogating the entire inversion process. Currently I am open to the development of any Bayesian methods that advance the state of the art through the use of scientific machine learning, surrogate models and neural networks. In addition, I am also currently working on extending the characterisation stage to the prognostics one, whereby the end-of-life of a structure can be predicted using degradation models. If you want to collaborate in any of these areas, do not hesitate to contact me.

# References
1. Cantero-Chinchilla, S., Aranguren, G., Royo, J.M., Chiachío, M., Etxaniz, J. and Calvo-Echenique, A., 2021. Structural health monitoring using ultrasonic guided-waves and the degree of health index. *Sensors*, 21(3), p.993.
2. Cantero-Chinchilla, S., Chiachío, J., Chiachío, M., Chronopoulos, D. and Jones, A., 2019. A robust Bayesian methodology for damage localization in plate-like structures using ultrasonic guided-waves. *Mechanical Systems and Signal Processing*, 122, pp.192-205.
3. Chiachío, J., Bochud, N., Chiachío, M., Cantero, S. and Rus, G., 2017. A multilevel Bayesian method for ultrasound-based damage identification in composite laminates. *Mechanical Systems and Signal Processing*, 88, pp.462-477.
