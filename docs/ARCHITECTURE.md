# System Architecture

## Current Architecture

The current system is intentionally simple:

```mermaid
flowchart LR
    RC[Radio Transmitter / Receiver] --> FC[ArduPilot Flight Controller]
    GPS[GPS / Compass] --> FC
    FC --> ESC[4-in-1 ESC]
    ESC --> MOTORS[4 Brushless Motors]
    BAT[LiPo Battery] --> ESC
```

The flight controller currently handles stabilization and manual flight.

## Planned Autonomy Architecture

```mermaid
flowchart LR
    CAMERA[Camera] --> JETSON[Jetson Orin Nano]
    JETSON --> ROS[ROS 2 Jazzy]
    ROS --> SLAM[SLAM / Visual Odometry]
    SLAM --> POSE[Local Pose Estimate]
    POSE --> CONTROL[Position-Hold Logic]
    CONTROL --> MAV[MAVLink]
    MAV --> FC[ArduPilot]
    FC --> ESC[4-in-1 ESC]
    ESC --> MOTORS[Motors]
```

## Design Goal

The major architectural change is the introduction of an external local-position estimate.

Instead of relying only on GPS for horizontal position, the planned companion-computer stack will estimate the drone's motion from camera data. That estimate can then be used to support GPS-denied position hold.

## Planned Software Responsibilities

### ArduPilot

- low-level attitude stabilization,
- motor output,
- failsafes,
- radio-control input,
- flight modes,
- vehicle state.

### NVIDIA Jetson Orin Nano

- camera processing,
- ROS 2 runtime,
- SLAM / visual odometry,
- local-pose estimation,
- future path planning.

### ROS 2 Jazzy

- sensor and pose message flow,
- modular autonomy nodes,
- debugging and visualization,
- future planning and perception integration.

### MAVLink

MAVLink is planned as the communication layer between the companion computer and ArduPilot. It is **not yet implemented in this project**.
