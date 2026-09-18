---
permalink: /projects/
title: "Projects"
author_profile: true
---

## Autonomous water-bottle pick and handoff

*ROS2 · Python · YOLO · RealSense · Kinova Kortex · Jetson Orin Nano*

A full pipeline taking a wheelchair-mounted Kinova Gen3 from camera frame to grasp: detect the bottle, locate it in 3D, transform into the arm's frame, check reachability, pick it up, and hand it to a person.

<video src="/files/demo.mp4" controls width="100%"></video>

- Fine-tuned yolo11s-seg to ~0.93 mIoU at 12–18 FPS on a Jetson Orin Nano, after benchmarking YOLO11 and YOLO26 segmentation variants for on-device use
- Built and labeled the ~350-image training dataset with Roboflow and SAM2
- Performed hand-eye calibration and depth-to-3D projection; added a RealSense camera as a fallback when the arm's onboard vision module failed
- Moved arm control from MoveIt to the Kortex API for real-time performance, with EMA pose filtering, track-locking, retry logic, and pause/resume services for safe handoff

## Assistive feeding pipeline

*In progress — December 2026 demo*

Autonomous feeding task on a wheelchair-mounted Kinova Gen3, extending the manipulation stack above.

## Feeding-deployment stack — EmPRISE Lab

*ROS2 · RoboStack · Kinova Gen3*

Deployment work for a microwave door-opening task. Set up and stabilized the ROS2 environment across Jetson and desktop machines, resolved dependency and driver conflicts, and contributed a fix upstream.
