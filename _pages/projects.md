---
layout: single
permalink: /projects/
title: "Projects"
author_profile: false
hide_sidebar: true
no_title_link: true
---

<link rel="stylesheet" href="{{ '/assets/css/projects.css' | relative_url }}">

<!-- 3D Reconstruction -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/3dreconstruct.gif" alt="3D Reconstruction">
    <div class="paper-textual">
      <h3>3D Scene Reconstruction & Gaussian Splatting</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Built SfM/MVS pipeline using pycolmap for 3D scene reconstruction from multi-view imagery with robust feature matching and sparse-to-dense reconstruction.</li>
        <li>Implemented and compared advanced feature detection and matching techniques including SuperPoint, SuperGlue, SIFT, and ROMA for robust correspondence and accurate camera poses.</li>
        <li>Applied Gaussian Splatting for high-quality novel view synthesis and efficient 3D scene representation.</li>
      </ul>
      <div style="height: 0.375em"></div>
      <p style="font-size: 0.85em; color: #666; margin: 0; font-style: italic;"><strong>Other team members:</strong> Adyant Srinivasan</p>
      <div style="height: 0.2em"></div>
      <div class="paper-links">
        <a href="https://drive.google.com/file/d/1fsuQqApizjY08JVZaQKz_Mp8fKm8RSET/view?usp=sharing">Report</a>
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
        <li>Built end-to-end transformer-based architecture for panoptic segmentation on nuScenes dataset, extending MaskPLS with cross-modal attention mechanisms.</li>
        <li>Integrated image and point cloud features using modified transformer decoder for unified multimodal understanding.</li>
        <li>Investigated and implemented four positional encoding strategies to spatially align and fuse multimodal features for improved segmentation accuracy.</li>
      </ul>
      <div style="height: 0.375em"></div>
      <p style="font-size: 0.85em; color: #666; margin: 0; font-style: italic;"><strong>Other Team Members:</strong> Nivisha Gandhi</p>
      <div style="height: 0.2em"></div>
      <div class="paper-links">
        <a href="https://github.com/charvi-077/Multimodal-Panoptic-Segmentation">Code</a>
      </div>
      <div style="height: 0.375em"></div>
    </div>
  </div>

  <!-- Civil Infrastructure Project -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/civil-proj.gif" alt="Civil Infrastructure Project">
    <div class="paper-textual">
      <h3>Civil Infrastructure Inspection (Research Project, IIIT-H)</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Developed a UAV-based vision pipeline to automate building inspection and estimate seismic structural parameters using deep learning (LEDNet for segmentation, DETIC for object detection).</li>
        <li>Automated estimation of building distances, plan-shape, rooftop layout, and crack detection from aerial imagery for rapid structural assessment.</li>
      </ul>
      <div style="height: 0.375em"></div>
      <p style="font-size: 0.85em; color: #666; margin: 0; font-style: italic;"><strong>Other Team Members:</strong> Jayakanth Kumar</p>
      <div style="height: 0.2em"></div>
      <div class="paper-links">
        <a href="https://github.com/charvi-077/civil-structure-inspection">Code</a> <span class="sep">/</span> <a href="https://civil-inspection-project-docs.readthedocs.io/en/latest/dataCollection.html">Docs</a>
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
        <li>Implemented and compared three major SLAM algorithms (Gmapping, Hector-SLAM, and Cartographer) across multiple environments using ROS ecosystem.</li>
        <li>Evaluated performance through systematic experiments in Gazebo; analyzed mapping accuracy, loop closure detection, and pose estimation error (RMS).</li>
        <li>Found Cartographer's better performance in complex environments and long corridors compared to traditional Gmapping and Hector-SLAM approaches.</li>
      </ul>
      <div style="height: 0.375em"></div>
      <div class="paper-links">
        <a href="https://drive.google.com/file/d/1y4Prp6W4tJA9ca0kAKvYfLpIHO9Cndse/view">Report</a>
      </div>
      <div style="height: 0.375em"></div>
    </div>
  </div>


  <!-- Convex Relaxations for Registration -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/convex-opti.gif" alt="Convex Relaxations for Registration">
    <div class="paper-textual">
      <h3>Convex Relaxations for Rigid and Non-Rigid Registration</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Formulated registration as a convex optimization problem leveraging Semidefinite Programming (SDP) and ADMM to achieve globally optimal and computationally efficient solutions.</li>
        <li>Developed algorithms for both rigid and non-rigid point cloud registration with theoretical guarantees on convergence and solution quality.</li>
      </ul>
      <div style="height: 0.375em"></div>
      <p style="font-size: 0.85em; color: #666; margin: 0; font-style: italic;"><strong>Other team members:</strong> Dharmesh</p>
      <div style="height: 0.2em"></div>
      <div class="paper-links">
        <a href="https://drive.google.com/file/d/17e6W-hWt0ewa0niRP7H_IZG3MZdfgQpL/view">Slides</a>
        <span class="sep">/</span>
        <a href="https://drive.google.com/file/d/1W0GhUW2ojVJJM2i8v-D0gQAZOObi1jNF/view">Report</a>
      </div>
      <div style="height: 0.375em"></div>
    </div>
  </div>

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

    <!-- BisQue -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/bisque.gif" alt="BisQue">
    <div class="paper-textual">
      <h3>BisQue - Web-based 5D Image Analysis Platform (VRL, UCSB)</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Contributed to BisQue, a web-based platform providing researchers with organizational and quantitative analysis tools for up to 5D image data with flexible metadata facility.</li>
        <li>Deployed and maintained infrastructure using Kubernetes (K3s) and Docker containerization, enabling execution of multiple deep learning based modules on distributed systems.</li>
        <li>Developed segmentation/Object detection modules using existing deep learning algorithms(Yolo, DETR, SAM, SAM2, CellPose3D) for multimodal data analysis (3D Cell Segmentation, Underwater Image Segmentation).</li>
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

  <!-- Ant Bot -->
  <div class="paper">
    <img class="paper-visual" src="/assets/projects/eyantra2.gif" alt="Ant Bot e-Yantra">
    <div class="paper-textual">
      <h3>Ant Bot - Firebird V Robot (e-Yantra IIT Bombay)</h3>
      <div style="height: 0.1em"></div>
      <ul class="paper-points">
        <li>Built Ant Bot from scratch using Firebird V robot kit and Raspberry Pi with SFM-based line following algorithm for autonomous navigation.</li>
        <li>Implemented segmentation-based object detection and decision-making algorithm using ArUco marker recognition for task-specific actions.</li>
      </ul>
      <div style="height: 0.375em"></div>
      <p style="font-size: 0.85em; color: #666; margin: 0; font-style: italic;"><strong>Other team members:</strong> Pranav Kumar, Ankur Bhatia, Dhawal</p>
      <div style="height: 0.2em"></div>
      <div class="paper-links">
        <a href="https://github.com/charvi-077/THE_ANT_BOT_e-Yantra-2018">Code</a>
        <span class="sep">/</span>
        <a href="https://drive.google.com/file/d/1EQ4P828vuVj7kjMM0S_i-fTmSZbR5KP1/view">Poster</a>
      </div>
      <div style="height: 0.375em"></div>
    </div>
  </div>

<!--
Notes:
- Images are referenced at `/assets/img/...`. Place your images at `assets/img/handoccnet_teaser.gif` and
  `assets/img/3DCrowdNet_CVPR2022.png` (or update the paths above) so they appear correctly.
-->
