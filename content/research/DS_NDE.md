+++
title = 'Data Science for NDE'
weight = 1
+++

# Introduction
Automation of non-destructive evaluation (NDE) processes has typically relied on rudimentary tools that support a trained operator manually interpreting data. The abundance of data and implementation of Internet of Things and Industry 4.0 provide a new exciting opportunity to extract more accurate information in a more efficient manner - hence, enabling automation. A general framework for the automation in ultrasonic NDE enabled by deep learning is provided below.

<figure>
<img src="../media/LevelsDiagram1.jpg" alt="Automation levels in ultrasonic NDE" style="width:500px;"/>
<figcaption>Automation levels for ultrasonic NDE [1].</figcaption>
</figure>

This research line explores data science and artificial intelligence/machine learning techniques for the automation of NDE processes, including data pre-processing, defect detection, and defect or material characterisation.

# Data pre-processing
NDE data are typically noisy and contain elements that may obscure defective information. In the case of ultrasonic NDE, this can be realised in the form of *artefacts* - benign feature that appear in images (ultrasonic imaging) potentially obscuring defects.
I have addressed this problem from a data-driven perspective, i.e. using datasets to build a model that can suppress the artefacts, ideally in the time-domain, before going to the image domain (as in the latter, preserving information from a pixel area is much more difficult).

To tackle this issue, I have proposed two methods [2,3] based on the concepts of autoencoders and PCA, which use either numerical or experimental data in order to learn the artefact representation in the time domain and suppress them. In [2], the suppression was addressed by blanking out some parts of the ultrasonic signals, while in [3] a subtraction was proposed. The benefit of [2] is an enhanced removal of artefacts but at the cost of removing defect-related energy and distorting the spread function. In [3], these limitations where addressed, showing a more realistic spread function of the defects while having a very limited impact in the level of artefact suppression.

<figure>
<img src="../media/Art_Supp.jpg" alt="Artefact suppression" style="width:500px;"/>
<figcaption>Artefact suppression example (Figure taken from [3]). First column is the raw image without suppression, second column is the PCA-AE from [3] compared against the GB-AE autoencoder in [2] and the original defect.</figcaption>
</figure>

The overall limitations rely on the simplistic inspection configuration considering flat specimens and artefacts stemming from back- and front-walls. These are aspects that are considered to have an implication in the design of the data-driven models, and that are under research consideration.

# Defect detection
This NDE stage involves the binary classification of a set of data in either defective or pristine material. In ultrasonic imaging, this is typically done by setting a threshold value (based on defect-free data) and identifying any amplitude above the threshold. The approaches from data pre-processing can be seen as an attempt to improve the performance of classical detectors.

Deep learning offers the possibility to detect defects from images by visually inspecting an image and tracing boxes whereby a defect is believed to be seen (e.g. through CNNs). Binary classifiers can also be created to provide information about the defect information in a piece of NDE data. However, the main issue with these approaches is the reliance on defect data, which are usually scarce in nature in NDE. Alternatives could include unsupervised approaches for anomaly detection, which effectively bypass the need for defective data and issues about class imbalance.

# Defect/Material characterisation
Characterising defects or material properties involves the prediction of numerical variables - e.g. defect size or remaining wall thickness. In ultrasonic imaging, this has been typically addressed through clipping methods (e.g. -6dB method) with the hope that it would help determine an accurate estimate of the defect size. However, these methods are conservative and not very accurate.

Neural networks provide an excellent alternative that produces numerical predictions from complex, structured or unstructured data. For example, predicting crack length and orientation from half-skip ultrasonic images [4] or estimating minimum wall thickness in heavily corroded materials [5]. Comparing against traditional methods to do this, the data-driven approaches easily improves their accuracy.

<figure>
<img src="../media/CNN_corrosion.jpg" alt="CNN architecture for wall thickness prediction" style="width:500px;"/>
<figcaption>CNN architecture for wall thickness prediction [5].</figcaption>
</figure>

However, issues w.r.t. the training data, uncertainty quantification and domain adaptation (when numerical data is required to train but the model is applied in experimental data) are still being explored to further improve these models. More remarkably, explainable AI can provide very useful information to determine the right network architecture to improve these models.

# Research work
The work in this area is nowadays focused on **explanability** and how that can help inform about (1) the behaviour of deep learning models for specific applications and (2) the optimal model structure through a human-interpretable and reasoned approach without having to do trial and errors. Further improvements in the artefact suppression and new ways of addressing the detection (and its performance evaluation through e.g. ROC curves) are also under consideration.

# References
1. Cantero-Chinchilla, S., Wilcox, P.D. and Croxford, A.J., 2022. Deep learning in automated ultrasonic NDE–developments, axioms and opportunities. *NDT & E International*, 131, p.102703.
2. Cantero-Chinchilla, S., Wilcox, P.D. and Croxford, A.J., 2022. A deep learning based methodology for artefact identification and suppression with application to ultrasonic images. *NDT & E International*, 126, p.102575.
3. Cantero-Chinchilla, S., Croxford, A.J. and Wilcox, P.D., 2023. A data-driven approach to suppress artefacts using PCA and autoencoders. *NDT & E International*, 139, p.102904.
4. Pyle, R.J., Bevan, R.L., Hughes, R.R., Rachev, R.K., Ali, A.A.S. and Wilcox, P.D., 2020. Deep learning for ultrasonic crack characterization in NDE. *IEEE Transactions on Ultrasonics, Ferroelectrics, and Frequency Control*, 68(5), pp.1854-1865.
5. Cantero-Chinchilla, S., Simpson, C.A., Ballisat, A., Croxford, A.J. and Wilcox, P.D., 2023. Convolutional neural networks for ultrasound corrosion profile time series regression. *NDT & E International*, 133, p.102756.
