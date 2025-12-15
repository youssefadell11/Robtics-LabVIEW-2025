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

  ![Image](https://github.com/user-attachments/assets/e06eaa69-d0d3-4727-91f0-c140cd7c72bc)
  <img width="1272" height="644" alt="Image" src="https://github.com/user-attachments/assets/30de396d-d13f-4b14-869e-d0a45779f905" />

### 2. Inverse Kinematics (IK)
* **Target-Based Control:** Allows users to input a Target $(X, Y, \phi)$ and solves for the required joint angles.
* **Solution Switching:** Features a dynamic **"Elbow Up / Elbow Down"** toggle to handle kinematic redundancy.
* **Safety Clamps:** Robust mathematical logic protects against singularity errors (NaN) when targets are out of reach.
* 
![Image](https://github.com/user-attachments/assets/e2b0a173-32aa-44cb-8ea4-7a924f8d5778)
<img width="1241" height="629" alt="Image" src="https://github.com/user-attachments/assets/d0ccec5f-40ef-4609-9d82-79b864749940" />
  

### 3. Trajectory Generation
* **Linear Path Planning:** Generates smooth, time-based trajectories between Start and End poses.
* **Full Synchronization:** Interpolates $X, Y, \text{Orientation}, \text{TCP}$, and \text{Claw} state simultaneously.
* **Dual-Loop Architecture:** Separates mathematical solving (Loop 1) from visual animation (Loop 2) for high performance.
* **Path Overlay:** Visualizes the planned trajectory as a static red line on the graph before movement begins.
  
![Image](https://github.com/user-attachments/assets/f12c2068-6260-4b49-a52b-e7bc1e2541e0)
![Image](https://github.com/user-attachments/assets/7fc62620-5977-4003-a526-f7e76dc1e84c)

### 4. Joystick Teleoperation
* **Hardware-in-the-Loop:** Interfaces with an **Arduino Joystick Shield** via serial/analog input.
* **Real-Time Mapping:** Scales raw analog input (-32768 to 32767) to physical joint limits (-90° to 90°).
* **Low Latency:** Optimized While Loop architecture for immediate visual feedback.

<img width="564" height="443" alt="Image" src="https://github.com/user-attachments/assets/37e8a646-db71-4f12-875a-468b7e7b9117" />
<img width="1305" height="663" alt="Image" src="https://github.com/user-attachments/assets/242eed04-b949-4458-85d5-3f7fe7e2d4f0" />


---

## 📂 Project Structure

```text
├── Documentation/
│   └── Report.pdf                           # Detailed Technical Report
└── README.md
