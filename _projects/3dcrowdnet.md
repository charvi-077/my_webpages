---
layout: none
title: "Learning to Estimate Robust 3D Human Mesh from In-the-Wild Crowded Scenes"
authors: "**Hongsuk Choi**, Gyeongsik Moon, JoonKyu Park, Kyoung Mu Lee"
venue: "CVPR 2022."
image: "/assets/img/abc.gif"
image_alt: "3DCrowdNet"
paper: "https://arxiv.org/abs/2104.07300"
code: "https://github.com/hongsukchoi/3DCrowdNet_RELEASE"
---

- **Problem:** Existing 3D human mesh methods fail in crowded, in-the-wild scenes due to a domain gap (motion-capture training data lacks crowd examples) and feature averaging that mixes features from multiple people.
- **Approach:** 3DCrowdNet uses 2D pose estimation (to avoid the MoCap domain gap) and a joint-based regressor that samples features at the target's joint locations, preserving spatial activations for the target person.
- **Result:** Produces target-focused features that exclude irrelevant nearby-person signals and yields robust performance on benchmarks (both quantitative and qualitative).
