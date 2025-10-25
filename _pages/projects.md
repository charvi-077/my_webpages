---
layout: single
permalink: /projects/
title: "Projects"
author_profile: false
---

<link rel="stylesheet" href="{{ '/assets/css/projects.css' | relative_url }}">

<div id="more-papers">
  <!-- HandOccNet -->
   <div class="paper">
    <img class="paper-visual" src="/assets/img/abc.gif" alt="3DCrowdNet">
    <div class="paper-textual">
      <h3>Learning to Estimate Robust 3D Human Mesh from In-the-Wild Crowded Scenes</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li><strong>Problem:</strong> Recovering a single person's 3D human mesh in crowded, in-the-wild scenes is hard because MoCap training data lacks crowd examples (domain gap) and feature averaging within bounding boxes mixes signals from multiple people.</li>
        <li><strong>Approach:</strong> 3DCrowdNet — leverage 2D pose estimation to avoid MoCap domain gaps and use a <em>joint-based regressor</em> that samples features at the target's joint locations to preserve target spatial activations.</li>
        <li><strong>Result:</strong> Generates target-focused features that exclude irrelevant nearby-person signals, improving robustness on benchmarks (quantitative and qualitative gains).</li>
      </ul>
      <div style="height: 0.375em"></div>
      <div class="paper-links">
        <a href="https://arxiv.org/abs/2104.07300">Paper</a>
        <span class="sep">/</span>
        <a href="https://github.com/hongsukchoi/3DCrowdNet_RELEASE">Code</a>
        <span class="sep">/</span>
        <a href="https://github.com/hongsukchoi/3DCrowdNet_RELEASE">Code</a>
      </div>
      <div style="height: 0.375em"></div>
    </div>
  </div>

  <!-- 3DCrowdNet -->
  <div class="paper">
    <img class="paper-visual" src="/assets/img/abc.gif" alt="3DCrowdNet">
    <div class="paper-textual">
      <h3>Learning to Estimate Robust 3D Human Mesh from In-the-Wild Crowded Scenes</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li><strong>Problem:</strong> Recovering a single person's 3D human mesh in crowded, in-the-wild scenes is hard because MoCap training data lacks crowd examples (domain gap) and feature averaging within bounding boxes mixes signals from multiple people.</li>
        <li><strong>Approach:</strong> 3DCrowdNet — leverage 2D pose estimation to avoid MoCap domain gaps and use a <em>joint-based regressor</em> that samples features at the target's joint locations to preserve target spatial activations.</li>
        <li><strong>Result:</strong> Generates target-focused features that exclude irrelevant nearby-person signals, improving robustness on benchmarks (quantitative and qualitative gains).</li>
      </ul>
      <div style="height: 0.375em"></div>
      <div class="paper-links">
        <a href="https://arxiv.org/abs/2104.07300">Paper</a>
        <span class="sep">/</span>
        <a href="https://github.com/hongsukchoi/3DCrowdNet_RELEASE">Code</a>
        <span class="sep">/</span>
        <a href="https://github.com/hongsukchoi/3DCrowdNet_RELEASE">Code</a>
      </div>
      <div style="height: 0.375em"></div>
    </div>
  </div>

</div>

<!--
Notes:
- Images are referenced at `/assets/img/...`. Place your images at `assets/img/handoccnet_teaser.gif` and
  `assets/img/3DCrowdNet_CVPR2022.png` (or update the paths above) so they appear correctly.
-->
