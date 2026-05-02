# 🤖 IE410: Introduction to Robotics — Project Part A

**Object Manipulation using a Robotic Arm**
*Winter 2026*

---

## 📋 Overview

This project explores kinematic control, visual sensing, and multi-robot coordination using the **Braccio robotic arm** with a two-finger gripper. It is divided into three progressively complex tasks, culminating in a coordinated two-arm object handover.

### Learning Objectives

- Understand kinematic control of a robotic manipulator with a two-finger gripper
- Implement a basic pick-and-place manipulation task using pre-planned robot motions
- Integrate visual sensing (smartphone or webcam) for object detection and robot guidance
- Develop coordination strategies for transferring an object between two robotic manipulators
- Gain practical experience with robot motion planning, grasping, perception-assisted manipulation, and task sequencing

---

## Task 1 — Pre-Programmed Pick and Place

### Description

The orange-colored Braccio robotic arm performs a simple pick-and-place operation in a fully pre-programmed manner — no sensor feedback is required.

### How It Works

1. An object (e.g., eraser or sharpener) is placed at a fixed **Point A** on a sheet of paper.
2. The robot arm grasps the object using its two-finger gripper.
3. The arm carries the object and places it at **Point B**.
4. The entire motion sequence — including gripper configuration, joint angles, and trajectory — is designed offline and executed repeatably.

### Key Concepts

- Forward/Inverse Kinematics
- Joint-space trajectory planning
- Gripper open/close control

> No visual feedback is used in this task. All positions and orientations are pre-defined.

---

## Task 2 — Camera-Assisted Pick and Place

### Description

This task extends Task 1 by introducing **perception-driven manipulation**. The robot must detect the object's position and orientation using a camera before grasping it.

### How It Works

1. The object may be placed at **varying locations or orientations** on the paper sheet.
2. A **smartphone camera or webcam** captures the scene and detects the object.
3. The estimated position relative to the robot workspace is used to compute the required joint motion.
4. The robot grasps the object and moves it to **Point B**.

### Sensing Approach

- Simple image processing techniques (e.g., color/contour detection), **or**
- **ARUCO markers** for reliable pose estimation

### Key Concepts

- Camera calibration and coordinate frame transformation
- Object detection and localization
- Sensor-driven motion planning

> Robot motion depends on live sensor inputs rather than fixed pre-programmed coordinates.

---

## Task 3 — Object Handover Between Two Robot Arms

### Description

Two Braccio robotic arms cooperate to transfer a soft object (e.g., a crumpled paper ball) from one gripper to the other without dropping it. This task introduces **multi-robot coordination** and **bimanual manipulation**.

### How It Works

1. **Arm 1** starts holding the soft object.
2. Arm 1 moves the object to a predefined **handover location** within the shared workspace.
3. **Arm 2** approaches, aligns its gripper, and grasps the object securely.
4. Only after Arm 2 confirms a stable grasp does Arm 1 open its gripper and release.

### Coordination Strategy

- Pre-defined handover point in shared workspace
- Synchronized gripper timing: Arm 2 closes → Arm 1 opens
- Proper spatial alignment of both end-effectors

### Key Concepts

- Multi-robot task sequencing
- Bimanual manipulation
- Gripper synchronization and timing

> A stable handover requires careful alignment and sequenced gripper control to prevent the object from being dropped.

---

## 🎥 Demo Video

> A 3-minute demonstration video of all three tasks is available [here](#).
> *(No stock music or AI voiceover used.)*

---

## 📄 Report

See [`report.pdf`](./report.pdf) for methodology, results, and discussion.

---

## 🛠️ Hardware & Software

| Component | Details |
|---|---|
| Robot Arm | Arduino Braccio (x2 for Task 3) |
| Gripper | Two-finger gripper |
| Camera | Smartphone / Webcam |
| Microcontroller | Arduino |
| Vision Library | OpenCV / ARUCO |
| Language | Python / Arduino (C++) |

---

## 👥 Team


*IE410 — Introduction to Robotics, Winter 2026*
