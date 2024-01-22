# Introduction

Age-related diseases have been increasing over the past years {cite}`Vos2012,Nichols2022`. The search for biomarkers that can predict the healthy and pathological ageing of the brain has been gathering a lot of attention {cite}`Higgins-Chen2021`. Brain age gap estimation (BrainAGE)  is a putative biomarker which tackles brain ageing trajectory by computing the difference between the estimation of brain age and the chronological age {cite}`JH2017`. BrainAGE has been shown to be increased in multiple pathological conditions suggesting an acceleration of the ageing process as a common mechanism {cite}`Baecker2021`. This chapter delves into the motivation for an ageing biomarker, provides an overview of BrainAGE and its existing limitations, and outlines the objectives of this thesis.

It is anticipated that by 2050 the number of individuals over the age of 65 years will surpass the number of both adolescents and young adults {cite}`McNicoll2002`. With the rising number of elderly individuals, the burden of deaths and disability caused by age-related conditions, such as neurodegenerative dementias, is increasing. The number of people diagnosed with dementia worldwide in 2019 was 57.4 million, and this number is expected to rise up to 152.8 million in 2050 {cite}`Nichols2022`.  

The prevalence of age-related conditions is being recognised as a global public health problem. The World Health Organization (WHO) has designated the decade from 2020 to 2030 as the decade of healthy ageing. \textit{Healthy ageing} is defined by WHO as "the process of developing and maintaining functional abilities that enable well-being in older age"  {cite}`Rudnicka2020`. Several factors seem to positively impact brain health. Education {cite}`Milgram2006`, physical exercise {cite}`Ahlskog2011,Wirth2014`, meditation {cite}`Villemure2015`, among others are associated with neuroprotective mechanisms and potentially slower ageing processes. Other lifestyle factors, such as tobacco {cite}`Swan2007` and alcohol consumption {cite}`Vik2004,Spencer1999`, as well as age-related diseases {cite}`Jin2023` seem to accelerate the ageing process. 

Thus, a biomarker sensitive to deviations in brain ageing trajectory might detect, in an early stage, diseases related to pathological ageing. In a pre-clinical stage, the detection of age-related diseases could prove valuable in personalised medicine, opening a window of opportunity for early interventions designed to increase health span or even decelerate ageing. 


## BrainAGE as a putative brain ageing biomarker

BrainAGE aims to gauge brain ageing to identify early deviations from the typical healthy trajectory. Over the past few years, this putative biomarker has gathered significant attention within the scientific community {cite}`Sajedi2019,Franke2019`. In a nutshell,  BrainAGE (1) models healthy brain ageing and (2) compute the difference between the brain age estimation and chronological age. To model healthy brain ageing, a machine learning algorithm is trained using data from individuals who have been confirmed to be healthy. It is assumed that, in healthy individuals, the brain age is equal to the chronological age. Different sources have been explored in BrainAGE {cite}`Franke2019`; this thesis focuses on using structural brain images acquired with magnetic resonance imaging (MRI), a non-invasive neuroimaging technique. Structural images were selected due to their high resolution and current use in clinical practice {cite}`Frisoni2010`. 
 
The rationale behind this putative biomarker is that a delayed ageing process results in a negative BrainAGE. In contrast, accelerated ageing is manifested as a positive value. A negative BrainAGE has been reported in individuals with higher education level {cite}`Steffener2016`, as well as in individuals who practice physical exercise  {cite}`Matziorinis2023` and meditation {cite}`Luders2016` regularly. As discussed above, these activities are related to neuroprotective mechanisms and, consequently, might decelerate brain ageing. Furthermore, tobacco {cite}`Linli2022,Ning2020` and alcohol consumption {cite}`Ning2020` yield a positive BrainAGE. Moreover, BrainAGE is positive in multiple pathological conditions, such as Alzheimer's disease (AD), mild cognitive impairment (MCI), schizophrenia and epilepsy {cite}`Baecker2021`.
Thus, BrainAGE seems to translate the biological mechanisms underlying the brain ageing process and might be able to capture the transition from healthy to pathological ageing.

## Limitations on BrainAGE

The performance of brain age models on test sets acquired in the same conditions as training data is, in general, similar to the performance on the validation test set. However, the model's performance on data collected in different acquisition settings is lower; in some cases, the error is two- or three-fold higher {cite}`LIEM2017179,Jonsson2019,Leonardsen2022,Zhai2019`. Therefore, brain age models are not reliable. To be used on other sites, these models must be retrained and validated with local data from healthy individuals. Therefore, the usage of BrainAGE in clinical practice is compromised by this generalisation issue. Consequently, it is of uttermost importance to address this limitation.

BrainAGE has a high sensitivity for different pathologies, nevertheless, its specificity is low {cite}`Baecker2021`. Currently, it solely identifies deviations without necessarily specifying the underlying disease. Therefore, approaches should be developed to detect the deviations and suggest the  specific pathology causing the abnormal ageing. A recent research trend aims to overcome this problem by predicting local brain age rather than a global age, yet the performance of these models still needs to improve.




## Goals and main contributions

This thesis aims to add insights to the BrainAGE as a ageing biomarker by improving its generalisability and specificity. 

On the generalisability axis, two studies were performed; one focused on preprocessing, while the other focused on model training. 
Concerning the preprocessing, a comparative analysis of two commonly employed MRI preprocessing frameworks {cite}`Sajedi2019`, computational anatomy toolbox (CAT12) and Freesurfer was performed, focusing on two critical aspects: reliability and reproducibility. The preprocessing phase plays a crucial role in reducing noise and removing non-brain tissue, which is essential to ensure the removal of data artefacts that could mislead the learning process {cite}`Sajedi2019`. The framework comparison was conducted using cortical thickness, a common feature in neuroimaging studies. This investigation selects the more reliable preprocessing framework, which is subsequently applied in the following studies. Another explored aspect on the generalisability axis was the usage of transfer learning as a training strategy for deep learning models. Deep learning models are data-driven, with remarkable performance on different tasks, namely object recognition and language processing {cite}`Lecun2015`. Nevertheless, these models demand high amounts of data. This requirement is often a constraint in the neuroimaging field, where the data is relatively scarce compared to natural images, in which millions of labelled images are available. Therefore, we explore the potential of transfer learning from an autoencoder to train brain age models and assess the impact of this training strategy on performance and generalisability.

The BrainAGE specificity was addressed by proposing a new feature, the deformation fields, and exploring the explainability of brain age models. The deformation fields were considered to predict brain age and were compared to segmented images commonly used in this field. The exploration of novel features can enhance the model`s specificity and help to understand the underlying biological processes. In this case, it sheds light on how morphology changes with age. Finally, the last study integrated all the previous analysis and assessed whether the explainability of brain age predictions could increase the BrainAGE specificity. The explainability highlights the regions most critical for age prediction and reveals the brain areas that exerted different influences when comparing the predictions in individuals with a particular disease with healthy controls. Identifying the regional pattern of accelerated ageing may unveil the underlying pathologies and add specificity to the model. 


## Scientific Outcomes

Throughout the course of this thesis, different achievements have been reached. Specifically, four articles were authored, with two already published and two currently undergoing the revision process. Most of the data used in the scope of this thesis are from open-source repositories. Moreover, some contributions were made to the nipype library {cite}`Gorgolewski2011`, which included the addition of CAT12 and Robust Brain Extraction (ROBEX) {cite}`Iglesias2011` to the supported preprocessing frameworks. 


* Peer-reviews journal articles

- Dias, Maria de Fátima Machado, Paulo Carvalho, Miguel Castelo-Branco, and João Valente Duarte. "Cortical thickness in brain imaging studies using freesurfer and cat12: A matter of reproducibility." Neuroimage: Reports 2, no. 4 (2022): 100137.
- Dias, Maria de Fátima Machado, Paulo Carvalho, João Valente Duarte, and Miguel Castelo-Branco. "Deformation fields: a new source of information to predict brain age." Journal of Neural Engineering 19, no. 3 (2022): 036025.
- Dias, Maria de Fátima Machado, Tiago FT Cerqueira, João Valente Duarte, Miguel Castelo-Branco, and Paulo Carvalho. "3DCAE-MRI: Overcoming Data Availability Limitations in Small Sample MRI Studies." Scientific Reports (2023). [under revision]
- Dias, Maria de Fátima Machado, João Valente Duarte, Paulo de Carvalho and Miguel Castelo-Branco. "Unravelling pathological ageing with brain age in Alzheimer’s Disease, Diabetes, and Schizophrenia." Brain Communications (2023). [under revision]


## References
```{bibliography}
```