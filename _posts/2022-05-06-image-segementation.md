---
title: Abdominal Medical Images Segmentation with CNN-Transformer Hybrid Model
author: Chuoqi Chen
date: 2022-05-06 18:06:00 -0400
categories: [Projects, Machine Learning]
tags: [machine learning]
math: true
mermaid: true
# image:
#   path: /commons/devices-mockup.png
#   width: 800
#   height: 500
#   alt: Responsive rendering of Chirpy theme on multiple devices.
---
<style>body {text-align: justify}</style>

Two novel neural network is purposed to solve problems in abodominal multi-organs segmentation:fragmental objects and failure in detecting small, direction-depend obejcts. 

---
**EECS545 Coursework Project**         

**Duration**: *02/2022-05/2022*

**Teammates**: Haowen Chen, Yuang Lu, Yuqi Yan, Ying Yuan

---
## Introduction
During Diagnosis, treatment and surgery with computer aid, medical image segmantation plays a curcial part in identifying pixels of anatomical objects in medical images. However, it is a time-consuming and heavy work to conduct segmentation on images one by one by doctors. The primary challenges for segmation mainly comes from three aspects: (1) Complex boundary interactions, (2) Large appearance variation, (3) Low tissue contrast. These challenges. With the advance of deep learning, it is necessary to conduct new techniques to help medical image segmentation.  

In this project, we focus on the abdominal multi-organs segmentation problem. We purpose two novel neural network structures to solve two main problems: fragmental objects edges and failue to detect small, direction-dependent objects. The performance of medical image segmentation is expected to be enhanced by fusing Self Attention mechanism and convolutional neural network. 

## Related Work(Baseline)
In this section, recent work for medical image segmentation will be gone through. To achieve pixel-wise classification, reseachers proposed the encoder-decoder network structure. UNet is one of the most outstanding works among them. Based on the structure, novel techniques have been introducrure into UMet. 
### ResUNet
Residual UNet(ResUNet) is inspired by ResNet. Previous results showed that with the humber of network layers increased, the feature identities and performance will loss. It is caused by vanishing gradients in deep network. By concatenating 
### TramsUNet

### Swin-UNet

### UTNet

### UNETR

## Proposed Method

## Evaluation

## Result Analysis

## Reference
