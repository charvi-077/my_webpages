---
title: "Real-Time Traffic Light Detection With Adaptive Background Suppression Filter"
last_modified_at: 2025-08-14-traffic-light-ABSF
categories:
  - computer-vision
tags:
  - Image Recongnition
  - Segmentation
  - Computer Vision
excerpt: "If Kakao 2022에서 소개된 MFIM 논문 리뷰 (EVCA 2022)"
use_math: true
classes: wide
published: false
---


> [[Paper](https://doi.org/10.48550/arXiv.2411.11922)]  
> Good tutorial links : [[Blog]()]
> Meta AI Research, FAIR


## Introduction : 


Introduction : 

They are trying to implement the traffic light detection . They proposed method that containes two 
stages (focus on varying illumination ): 
1. cantidate extraction stage : propose adaptive background suppression algorithm to highlight traffic light candidate regions , suppressing background. 
2. Recognition stage : each candidate region is verified and further classified into different traffic light semantic classes . 

Realtime processing atmost 15fps.  

# Adaptive Background Suppression Filter (AdaBSF) – Intuition & Math

This method is designed to **suppress background clutter** while keeping strong responses for **small objects of interest** (e.g., traffic lights).

---

## 🔹 Step 1: Background Energy

- Define a **background patch** as:

$$
x_b
$$

$$
x_b \gamma \Gamma \sum(shit + shit2 ) = shit3
$$

- Filter response to background:

$$
y_b = w^T x_b
$$

- Expected energy (average squared response):

$$
E\{y_b^2\} = E\{(w^T x_b)^2\} = w^T E\{x_b x_b^T\} w
$$

- Define the **background correlation matrix**:

$$
R_b = E\{x_b x_b^T\}
$$

So:

$$
E\{y_b^2\} = w^T R_b w
$$

👉 Interpretation: If this value is small, the filter effectively suppresses background responses.

---

## 🔹 Step 2: Preserve Target (Traffic Lights)

For a **target patch** \(x_t\):

$$
w^T x_t = 1
$$

This enforces a strong normalized response to traffic lights.

So the optimization problem is:

$$
\min_w \; w^T R_b w \quad \text{s.t.} \; w^T x_t = 1
$$

This is a **Rayleigh quotient problem**, common in signal processing (e.g., beamforming, Wiener filters).

---

## 🔹 Step 3: Multiple Target Variations

Traffic lights can look different (intensity, lighting, time of day).  
So multiple constraints are added:

$$
w^T x_{t,i} \geq 1 - \xi_i, \quad \xi_i \geq 0
$$

Where:
- \(x_{t,i}\) = i-th traffic light sample  
- \(\xi_i\) = slack variable (like in SVMs) → allows constraint violations

---

## 🔹 Step 4: Final Optimization (AdaBSF)

The optimization problem becomes:

$$
\min_{w, \xi} J(w, \xi) = w^T R_b w \;+\; \alpha \sum_{i=1}^{N_t} \xi_i \;+\; \beta \|w\|^2
$$

- **First term**: Suppress background responses (\(w^T R_b w\))  
- **Second term**: Penalty if targets not detected (\(\alpha \sum \xi_i\))  
- **Third term**: Regularization to keep weights stable (\(\beta \|w\|^2\))  

👉 This looks very similar to an **SVM optimization**.

---

## 🔹 Step 5: Quadratic Programming Formulation

Rewritten as:

$$
\min_{\tilde{w}} \; \tilde{w}^T H \tilde{w} + f^T \tilde{w} 
\quad \text{s.t.} \; A \tilde{w} \leq b
$$

where:

$$
\tilde{w} = 
\begin{bmatrix}
w \\
\xi
\end{bmatrix}
$$

This is a **standard convex Quadratic Program (QP)**.

---

## 🔹 Step 6: Barrier Method

Constraints are inequalities → handled with a **log barrier**:

$$
B_L(\tilde{w}) = J(\tilde{w}) \;-\; \frac{1}{\mu} \sum \log(a_i^T \tilde{w} - b_i)
$$

- Start with small \(\mu\), solve easier problem  
- Gradually increase \(\mu\) → solution converges to constrained optimum  
- Each step solved with **Newton’s method**

---

## 🔹 Step 7: Detection Phase

Once optimal filter \(w^*\) is found:

$$
y_i = (w^*)^T x_i
$$

- If \(y_i \geq T\) → classify as **traffic light candidate**  
- Apply **Non-Maximum Suppression (NMS)** to remove duplicates

---

## ✅ Summary

- Suppresses background (minimize \(w^T R_b w\))  
- Enforces detection of targets (\(w^T x_t \approx 1\))  
- Handles variability with slack variables \(\xi_i\)  
- Optimized via Quadratic Programming + Barrier method  
- Final filter \(w^*\) applied to image patches → threshold + NMS → detections




<center><img src='{{"image-3.webp" | relative_url}}' width="80%"></center>
<center><em>caption</em></center>

