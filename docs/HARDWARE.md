# Hardware

## Current Platform

The current quadrotor is a manually flown ArduPilot platform that will serve as the hardware base for future autonomous-flight development.

| Component | Current Status |
|---|---|
| Flight controller | F405-class controller running ArduPilot |
| ESC | 4-in-1 ESC |
| Motors | 4 × 1200 KV brushless motors |
| Battery | LiPo |
| GPS / compass | Installed |
| Radio control | Installed and working |
| NVIDIA Jetson Orin Nano | Planned |
| Camera | Planned; not connected |
| Custom 3D-printed frame | Planned |

## Current Flight Capability

The drone can currently be flown manually with a radio controller through ArduPilot.

GPS-based position hold has been tested but is not considered reliable. The aircraft has shown significant drift during these tests.

## Suspected GPS/Compass Interference

One hypothesis is that high-current motor or power wiring may be producing interference near the GPS/compass hardware.

This has **not yet been confirmed**. Future troubleshooting should include:

- relocating the GPS/compass farther from power wiring,
- checking compass health and interference in ArduPilot logs,
- verifying orientation and calibration,
- inspecting vibration levels,
- validating GPS satellite count and accuracy,
- repeating position-hold tests in a controlled environment.

## Planned Mechanical Work

A custom frame is planned for CAD and 3D printing. Mechanical goals include:

- cleaner electronics placement,
- better separation between high-current wiring and navigation sensors,
- dedicated mounting for the Jetson,
- camera mounting,
- improved serviceability,
- space for future autonomous-navigation sensors.
