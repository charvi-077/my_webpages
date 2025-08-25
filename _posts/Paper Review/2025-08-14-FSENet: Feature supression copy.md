---
title: "FSENet: Feature suppression and enhancement network for tiny object detection"
last_modified_at: 2025-08-14-SAM
categories:
  - computer-vision
tags:
  - Object Detection
  - Computer Vision
excerpt: "If Kakao 2022에서 소개된 MFIM 논문 리뷰 (EVCA 2022)"
use_math: true
classes: wide
---

> [[Paper](https://doi.org/10.1016/j.patcog.2025.111425)]  
> Good tutorial links : [[Blog]()]
> Meta AI Research, FAIR


## Introduction : 
Feature fusion is a common technique in object detection, especially for small objects. However, it can lead to information loss and noise interference. This paper proposes a new method called ( feature suppression and enhancement module) FSEM that helps to improve the detection of tiny objects.

Single shot detector are solving many problems, but complex scale variations in real-world scenarios remain a challenge and difficulty in object detection

