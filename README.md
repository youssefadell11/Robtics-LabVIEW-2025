# 🤖 3-DOF Planar Robot Simulator (LabVIEW 2025)

<img width="2752" height="1536" alt="Image" src="https://github.com/user-attachments/assets/178bc2c2-7aec-4cf7-9e7a-ff6451cf7284" />

## 📝 Overview
This repository contains a comprehensive **Digital Twin simulation of a 3-DOF (RRR) Planar Robotic Manipulator** developed in **LabVIEW 2025**. 

The project is designed to bridge the gap between theoretical mechanics and practical control systems. It allows users to simulate kinematic chains, visualize workspace limits, generate automated trajectories, and control the robot in real-time using a physical joystick.

**📺 [Watch the Full Demonstration on YouTube](https://www.youtube.com/playlist?list=PLtZreFIbvwdiTNFI50TTKZVrqkKH9rAwB)**

---

## 🚀 Key Features

### 1. Forward Kinematics (FK)
* **Real-time Visualization:** Converts joint angles $(\theta_1, \theta_2, \theta_3)$ to Cartesian coordinates $(x, y)$.
* **Dynamic Rendering:** Uses custom parametric SubVIs to draw the robot links and joints on a 2D Picture Control.
* **Stick Figure Verification:** Includes a raw XY Graph mode for verifying geometric equations.

### 2. Inverse Kinematics (IK)
* **Target-Based Control:** Allows users to input a Target $(X, Y, \phi)$ and solves for the required joint angles.
* **Solution Switching:** Features a dynamic **"Elbow Up / Elbow Down"** toggle to handle kinematic redundancy.
* **Safety Clamps:** Robust mathematical logic protects against singularity errors (NaN) when targets are out of reach.

### 3. Trajectory Generation
* **Linear Path Planning:** Generates smooth, time-based trajectories between Start and End poses.
* **Full Synchronization:** Interpolates $X, Y, \text{Orientation}, \text{TCP}$, and \text{Claw} state simultaneously.
* **Dual-Loop Architecture:** Separates mathematical solving (Loop 1) from visual animation (Loop 2) for high performance.
* **Path Overlay:** Visualizes the planned trajectory as a static red line on the graph before movement begins.

### 4. Joystick Teleoperation
* **Hardware-in-the-Loop:** Interfaces with an **Arduino Joystick Shield** via serial/analog input.
* **Real-Time Mapping:** Scales raw analog input (-32768 to 32767) to physical joint limits (-90° to 90°).
* **Low Latency:** Optimized While Loop architecture for immediate visual feedback.

---

## 📂 Project Structure

```text
├── Main VIs/
│   ├── RRR_Forward_Kinematics_2025.vi       # Manual Angle Control
│   ├── RRR_Inverse_Kinematics_2025.vi       # Cartesian Target Control
│   ├── RRR_Trajectory_Generation_2025.vi    # Automated Path Planning
│   └── RRR_Joystick_Control_2025.vi         # Real-time Hardware Control
├── Documentation/
│   └── Report.pdf                           # Detailed Technical Report
└── README.md
