---
title: "Multi-Modal MRI Reconstruction Assisted with Spatial Alignment Network"
date: 2021-08-21 08:49:46
layout: post
author_profile: false
read_time: true
---

In clinical practice, magnetic resonance imaging (MRI) with multiple contrasts is usually acquired in a single study to assess different properties of the same region of interest in human body. The whole acquisition process can be accelerated by having one or more modalities under-sampled in the *k*-space. 

Our early research ([Xiang *et al.*](https://ieeexplore.ieee.org/document/8552399)) demonstrates that, **considering the redundancy between different contrasts or modalities, a target MRI modality under-sampled in the *k*-space can be better reconstructed with the helps from a fully-sampled sequence (i.e., the reference modality)**. It implies that, in the same study of the same subject, multiple sequences can be utilized together toward the purpose of highly efficient multi-modal reconstruction. 

However, we find that multi-modal reconstruction can be negatively affected by **subtle spatial misalignment** between different sequences, which is actually common in clinical practice. Thus, we aim to **integrate the spatial alignment network with reconstruction** in this work, to improve the quality of the reconstructed target modality. 

A spatial alignment network is integrated into the multi-modal MRI reconstruction pipeline to compensate for the spatial misalignment between the fully-sampled reference image and the under-sampled target.

Specifically, the spatial alignment network estimates the spatial misalignment between the fully-sampled reference and the under-sampled target images, and warps the reference image accordingly. Then, the aligned fully-sampled reference image joins the under-sampled target image in the reconstruction network, to produce the high-quality target image. Our experiments on both clinical MRI and multi-coil *k*-space raw data demonstrate the superiority and robustness of our spatial alignment network.

**For more details of this work, please refer to [Xuan *et al.*](https://ieeexplore.ieee.org/document/9745968) [[arXiv]](http://arxiv.org/abs/2108.05603).**