---
title: "Kalman Filter"
last_modified_at: 2025-08-14-SAM
categories:
  - research
  - computer-vision
tags:
  - Estimation
  - Computer Vision
excerpt: "If Kakao 2022에서 소개된 MFIM 논문 리뷰 (EVCA 2022)"
use_math: true
classes: wide
published: false
---

> Good tutorial links : [[Blog](https://www.kalmanfilter.net/background.html)]
> Meta AI Research, FAIR


## Introduction : 

Hidden State : One thing that we measure/compute using the available data ! 
for example : actual weight of person is hidden state, if scale is with error then it has noisy value called system state , and if take average of those values that's called estimated system state.  

Variance : spread of data from its mean , we calculate by avg of squared from the mean, sigma^square also instead of normalizing by N we normalize by N-1
Standard variance : square root of the variance, sigma


Normal distribution : gaussian curve is pdf for the normal distribution . 

Random variable : describes hidden state of the system , set of possible values from a random experiment. 
it could be discrete or continous. 

Estimation : we can estimate the hidden state . every measured or computed parameter is called estimate 

Accuracy : how close the measurement is to true value 

Precison : how close is the all estimated values for same parameter. 

The alpha - Beta - Gamma Filter : 

Lets take example to calculate weight of the gold : 

x : true value of weight 
z(n) : measure   value of weight at time n 
xbar(n, n) : estimate of x at time n and measurement z(n) is provided as well.
xbar(n+1, n): estimate of x at time n+1 , but it is made at time n only till measurement z(n) is provided, it is called predicted state.
xbar(n-1, n-1) estimate of x at time n-1, so measurement z(n-1) is provided
xbar(n, n-1): is prior prediction - estimate of the sate at time n, prediction is made at time n-1

state update equation : 

estimate of the current state = predicted value of current state + factor ( measurement - predicted value of the current state) 

(predict , update cycle )



