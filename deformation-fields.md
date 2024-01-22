# Deformation fields: a new source of information to predict brain age

**Objective:** The modelling of healthy ageing critically requires the identification of methods that detect subtle changes in this process. In the last few years multiple machine learning models have been proposed that learn age patterns from magnetic resonance imaging (MRI). Current standard information sources rely on local volumetric information of brain tissues, namely grey mater (GM), white matter (WM) and cerebrospinal fluid (CSF). Information about patterns of brain deformation remains underexplored. In this paper an assessment is performed to understand better the predictive value of the deformation fields.

**Approach:** A shallow approach was used to compare the predictive value of deformation fields with the brain tissues (GM, WM and CSF). Images were compressed into a lower dimension space using Principal Components Analysis and then, a RVR (relevant vector regression) learned the age patterns from the components. A model was trained per modality (deformation fields, GM, WM and CSF) and the performance between the models was compared. To evaluate whether the deformation fields increased the predictive power of GM, a model fusion approach was explored in which the final estimator was a RVR. Each model was validated using a cross-validation approach and was also evaluated on an external dataset.

**Main results:**  We found that models trained with deformation patterns have higher predictive value than the ones trained with WM or CSF. Furthermore, deformation fields had a significantly better performance on the test set and also yield the lower difference between the validation and test set. Moreover, the predictions based on the combination of deformation patterns with GM volume yields better results than GM volumetric information alone.

**Significance:** These findings suggest that deformation fields have a higher predictive power than WM and CSF and are robustly invariant across a set of confounding variables. Therefore, deformation fields should be considered in brain age models. 
Keywords: Deformation Fields, BrainAge, Ageing; Machine Learning

## Paper
https://iopscience.iop.org/article/10.1088/1741-2552/ac7003

## Code availability
https://cibit-uc.github.io/brainage-deformation-fields