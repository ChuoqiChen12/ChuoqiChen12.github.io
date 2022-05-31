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

## Related Work
In this section, recent work for medical image segmentation will be gone through. To achieve pixel-wise classification, reseachers proposed the encoder-decoder network structure. UNet is one of the most outstanding works among them. Based on the structure, novel techniques have been introducrure into UMet. 
### ResUNet
Residual UNet(ResUNet) is inspired by ResNet. Previous results showed that with the humber of network layers increased, the feature identities and performance will loss. It is caused by vanishing gradients in deep network. By concatenating features, the skip connection before downsampling or upsamplinng in ResUNet help preseve feature maps. 

According to our results, ResUNet is capable of detecting all 13 organs in the Synapse dataset including small and directions objects such as left and right adrenal gland. However, all other transformer-based models failed to do so. It can also perform better in segmenting other small organs such as portal vein and splenic vein. It is believed that convolutional layer helps model to detect and segmentate these small objects.
### TramsUNet
TranUNet is a model based on Transformers and UNet, leveraging both detailed high-resolution spatial information from CNN features and the global context encoded by Transformers. Transformer serves as a strong encoder, providing attentive feature sequence. According to former results, this architecture achieves superior performance over any other methos on medical image segmentation. Therefore, TransUNet works as the baseline model in this project and implement a novel model.
### Swin-UNet
Based on the outstanding performance in Trans-UNet, optimization of Transformer might be opt to image segmentation. Swin-UNet could be one among them. Different from all silices connected together in Trans-UNet, the limited slices is connected with the neighboring slices in  Swin-UNet. When in the higher layer, the output from the neighbor transformer will be the input of the next layer. By this way, more details from the images could be trained and neighboring information could affects each other. 

Though Swin-UNet has higher DICE score over TRansUNet in overall, which means that it could better classify each pixel in the right class, the results showed that the segmented objects trained by Swin-UNet is fragmental and have rougher edges compared to TransUNet.
### UTNet
Although transformer variants perform well in vision tasks, pixels packed in the same input image patch does not contain enough spatial information, leading to weaker inductive bias compared with traditional CNN. Therefore, vision transformer-based models require large image set to gain enough prior knowledge in image domain. However, a major characteristic of medical image segmentation tasks is that they usually cannot provide such a big dataset, using pretrained weight on other large image datasets then becomes a widely adopted solution.

UTNet, unlike other models, employs another method. Common vision transformer and their variants packing pixel into patches and flattening them into vectors while UTNet preserves the first few encoding layer as convolutional layer, the pixel-level spatial relations thus can be retained.
### UNETR
UNETR proposed a novel transformer-based model for volumetric medical image segmentation. Instead, of extracting features with Transformers at the bottleneck of U-Net, UNETR has its skip-connected decoder combines representation from multiple intermediate Transformers layers. Deconvolutional layers are applied to these intermediate representation to increase the resolution. Sucj architechture helps the network capture global contextual representation at multiple scales and increase the cpaability for learning long-range dependencies
### TransFuse
In order to improve the efficiency of modeling global contexts and preserve low-level features, TransFuse uses a parallel approach to merge Transformers and CNNs. This allows the efficient collection of both global dependencies and low-level spatial features in a significantly shallower manner. The BiFusion module is a novel fusion techinique that efficiently fuses the multi-level features from both branches. According to the researches, TransFuse obtains the state-of-the-art results on both 2D and 3D medical picture sets with significantly fewer parameters and significanly faster inference.
## Proposed Method
## Evaluation

## Result Analysis

## Reference
