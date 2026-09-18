---
permalink: /projects/
title: "Projects"
author_profile: true
---

## Autonomous water-bottle pick and handoff

*ROS2 · Python · YOLO · RealSense · Kinova Kortex · Jetson Orin Nano*

A full pipeline taking a wheelchair-mounted Kinova Gen3 from camera frame to grasp: detect the bottle, locate it in 3D coordinates, use Inverse Kinematics, check reachability, pick it up, and hand it to a person.

<iframe width="100%" height="400" src="https://www.youtube.com/embed/XVQrVZTlzw8" frameborder="0" allowfullscreen></iframe>

*Full sequence: detection through grasp and handoff.*

### How it works

- **Detection.** Fine-tuned yolo11s-seg to ~0.93 mIoU at 12–18 FPS on a Jetson Orin Nano, after benchmarking YOLO11 and YOLO26 segmentation variants for on-device use. Built and labeled the ~350-image training dataset with Roboflow and SAM2.
- **Localization.** Depth-to-3D projection and hand-eye calibration to put the bottle in the arm's frame. Added a RealSense camera as a fallback when the arm's onboard vision module failed.
- **Control.** Moved from MoveIt to the Kortex API for real-time performance, with EMA pose filtering, track-locking, IK reachability checks, retry logic, and pause/resume services for safe handoff.

<iframe width="100%" height="400" src="https://www.youtube.com/embed/YyiRctdmvDQ" frameborder="0" allowfullscreen></iframe>

*Wrist camera and external view side by side.*

<iframe width="100%" height="400" src="https://www.youtube.com/embed/3mA2wpvwTL4" frameborder="0" allowfullscreen></iframe>

*Consecutive picks, sped up. Repeatability across attempts and bottle positions.*

## Assistive feeding pipeline

*In progress — December 2026 demo*

Autonomous feeding task on a wheelchair-mounted Kinova Gen3, extending the manipulation stack above.

## Feeding-deployment stack — EmPRISE Lab

*ROS2 · RoboStack · Kinova Gen3*

Deployment work for a microwave door-opening task. Set up and stabilized the ROS2 environment across Jetson and desktop machines, resolved dependency and driver conflicts, and contributed a fix upstream.
