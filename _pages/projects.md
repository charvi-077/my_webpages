---
layout: single
permalink: /projects/
title: "Projects"
author_profile: false
hide_sidebar: true
no_title_link: true
---

<link rel="stylesheet" href="{{ '/assets/css/projects.css' | relative_url }}">

<div id="more-papers">
  

 


  <!-- ROS2 FastPlanner -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/ros2-fast-planner.gif" alt="ROS2 FastPlanner">
    <div class="paper-textual">
      <h3>Kinodynamic Path Searching & B-spline Optimization, ROS2</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Integrated kinodynamic path searching and B-spline trajectory optimization into ROS2's asynchronous framework for real-time, smooth trajectory generation in autonomous drone navigation.</li>
        <li>Ported the FastPlanner motion planning package from ROS1 to ROS2, enabling efficient trajectory generation and replanning.</li>
      </ul>
      <div style="height: 0.375em"></div>
      <p style="font-size: 0.85em; color: #666; margin: 0; font-style: italic;"><strong> Other Team Members:</strong> Basvaraj PN, Rohit Pawar</p>
      <div style="height: 0.2em"></div>
      <div class="paper-links">
        <a href="https://github.com/RohitPawar2406/Fast-Planner-ROS2/tree/main?tab=readme-ov-file">Code</a>
      </div>
      <div style="height: 0.375em"></div>
    </div>
  </div>

  <!-- Multimodal Panoptic Segmentation -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/seg-nuscene.gif" alt="Multimodal Panoptic Segmentation">
    <div class="paper-textual">
      <h3>Multimodal Panoptic Segmentation</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Developed panoptic segmentation approach combining instance and semantic segmentation for autonomous scene understanding.</li>
        <li>Integrated multimodal sensor fusion to enhance segmentation accuracy in complex driving scenarios.</li>
      </ul>
      <div style="height: 0.375em"></div>
    </div>
  </div>

  <!-- Civil Infrastructure Project -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/civil-proj.gif" alt="Civil Infrastructure Project">
    <div class="paper-textual">
      <h3>Civil Infrastructure Detection & Analysis</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Developed automated detection and classification system for civil infrastructure elements from aerial imagery.</li>
        <li>Applied deep learning for robust analysis of infrastructure features in large-scale geospatial datasets.</li>
      </ul>
      <div style="height: 0.375em"></div>
    </div>
  </div>

  <!-- BisQue -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/bisque.gif" alt="BisQue">
    <div class="paper-textual">
      <h3>BisQue - ML Module Execution & Deployment</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Deployed and maintained BisQue test bench infrastructure using Kubernetes (K3s) and Docker containerization.</li>
        <li>Debugged and resolved deployment issues, enabling seamless execution of multiple ML modules on distributed infrastructure.</li>
        <li>Enhanced functionality to support concurrent execution of multiple machine learning modules with improved orchestration.</li>
      </ul>
      <div style="height: 0.375em"></div>
      <p style="font-size: 0.85em; color: #666; margin: 0; font-style: italic;"><strong>Team Members:</strong> Connor, Chandrakanth, Amil Khan</p>
      <div style="height: 0.2em"></div>
      <div class="paper-links">
        <a href="https://bisque2.ece.ucsb.edu/client_service/">Project</a>
        <span class="sep">/</span>
        <a href="https://github.com/UCSB-VRL/bisqueUCSB">Code</a>
      </div>
      <div style="height: 0.375em"></div>
    </div>
  </div>

  <!-- 2D SLAM -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/2dmapping.gif" alt="2D SLAM" style="flex: 0 0 50%; max-width: 450px;">
    <div class="paper-textual">
      <h3>2D SLAM - Simultaneous Localization and Mapping</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Tested and implemented multiple SLAM algorithms including SlamToolbox, Gmapping, and Cartographer using ROS ecosystem.</li>
        <li>Evaluated algorithm performance using RVIZ visualization and GAZEBO simulation for robotic navigation and mapping.</li>
        <li>Compared accuracy, computational efficiency, and map quality across different SLAM approaches for autonomous navigation.</li>
      </ul>
      <div style="height: 0.375em"></div>
    </div>
  </div>

  <!-- 3D Reconstruction -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/3dreconstruct.gif" alt="3D Reconstruction">
    <div class="paper-textual">
      <h3>3D Reconstruction & Feature Matching</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Explored and implemented Structure-from-Motion (SfM) pipeline using COLMAP for 3D scene reconstruction from multi-view imagery.</li>
        <li>Investigated advanced feature detection and matching techniques including SuperPoint, SuperGlue, SIFT, and ROMA for robust correspondence.</li>
        <li>Performed Gaussian Splatting for high-quality novel view synthesis and efficient 3D scene representation.</li>
        <li>Compared and evaluated different feature matching strategies for accuracy and computational efficiency in reconstruction tasks.</li>
      </ul>
      <div style="height: 0.375em"></div>
    </div>
  </div>

</div>

<!--
Notes:
- Images are referenced at `/assets/img/...`. Place your images at `assets/img/handoccnet_teaser.gif` and
  `assets/img/3DCrowdNet_CVPR2022.png` (or update the paths above) so they appear correctly.
-->
