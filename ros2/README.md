# ROS 2 Autonomy Stack

**Status: Not implemented yet.**

This directory is reserved for the ROS 2 Jazzy software that will run on the planned NVIDIA Jetson Orin Nano companion computer.

The first planned packages will focus on:

1. communication with ArduPilot,
2. vehicle-state telemetry,
3. camera input,
4. local pose estimation,
5. SLAM integration,
6. GPS-denied position hold.

No autonomous-flight source code is currently included because development has not begun yet.

A likely future workspace layout is:

```text
ros2/
└── src/
    ├── drone_interface/
    ├── drone_localization/
    └── drone_control/
```

The final package names and architecture will be chosen once Jetson-to-flight-controller communication is working.
