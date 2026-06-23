---
title: "Recurrent Tissue-Aware Network for Deformable Registration of Infant Brain MR Images"
date: 2021-12-24 17:10:35
layout: post
author_profile: false
read_time: true
---

Deformable registration is fundamental to longitudinal and population-based image analyses. However, it is challenging to precisely align longitudinal infant brain MR images of the same subject, as well as cross-sectional infant brain MR images of different subjects, due to fast brain development during infancy.

We propose a recurrently usable deep neural network for the registration of infant brain MR images. The framework is illustrated below.

The proposed solution consists of basic **T**(issue)**A**(aware)-Net and spatial transformer. With *n*-loops for recurrent inference, the final deformation field is composed from all the incremental deformations.

There are three main highlights of our proposed method.

1. We use brain tissue segmentation maps for registration, instead of intensity images, to tackle the issue of rapid contrast changes of brain tissues during the first year of life.
2. A single registration network (TA-Net) is trained in a one-shot manner, and then recurrently applied in inference for multiple times, such that the complex deformation field can be recovered incrementally.
3. We also propose both the adaptive smoothing layer and the tissue-aware anti-folding constraint into the registration network to ensure the physiological plausibility of estimated deformations without degrading the registration accuracy.

We have provided comprehensive experimental results, in comparison to the state-of-the-art registration methods, to validate the proposed method. In summary, our method achieves the highest registration accuracy while still preserving the smoothness of the deformation field.

**For more details of this work, please refer to [Wei *et al*.](https://ieeexplore.ieee.org/document/9656924)**