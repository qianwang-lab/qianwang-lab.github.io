---
title: "Follow My Eye: Using Gaze to Supervise Computer-Aided Diagnosis"
date: 2022-01-29 16:51:26
layout: single
author_profile: false
read_time: true
---

One of the most popular trends in medical image analysis is to apply deep learning techniques to computer-aided diagnosis (CAD). However, it is evident now that a large number of manually labeled data is often a must to train a properly functioning deep network. This demand for supervision data and labels is a major bottleneck, since collecting a large number of annotations from experienced experts can be time-consuming and expensive.

In this work, we aim to demonstrate that **the eye movement of radiologists when reading medical images can be a new form of supervision** to train the deep-learning-based CAD system. Particularly, we record the tracks of the radiologists’ gaze when they are reading images. The gaze information is processed and then used to supervise the deep network’s attention via an attention consistency module.

The collected gaze points are represented by their spatial coordinates and the timestamps. The gaze points are used to compute the attention level, and are further separated into the saccade points and the fixation points, respectively. The saccade points mark the fast movement of the eyes while the fixation points mark the focusing locations of eyes.

**We are among the first to use radiologist’s gaze to build deep-learning-based CAD systems.** While tracking eye movement is not completely new to the field of radiology, we have successfully conducted this pilot study and achieved superior performance in the CAD task of radiograph assessment for osteoarthritis. 

The deep network consists of two parts, i.e., the classification network, and the attention consistency (AC) module. Both parts are activated during training, yet only the classification network is used for inference.

The setup in our lab allows the radiologists to read images without being distorted or interrupted by the gaze tracker. Therefore, our solution can work as a general-purpose plug-in to current clinical workflows and numerous applications. Meanwhile, with our released toolkit, many other labs can initiate their gaze-based researches easily and efficiently.

**For more details of this work, please refer to [Wang *et al*](https://ieeexplore.ieee.org/document/9694633).**