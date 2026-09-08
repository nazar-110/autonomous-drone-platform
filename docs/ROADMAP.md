# Development Roadmap

The project is being developed in phases so that each autonomy capability is validated before adding the next one.

## Phase 1 — Manual Flight Platform

- [x] Assemble quadrotor
- [x] Configure ArduPilot
- [x] Configure radio control
- [x] Perform manual flight testing
- [x] Record flight footage

**Result:** functioning manually controlled ArduPilot drone.

## Phase 2 — Diagnose Position-Hold Failure

- [ ] Review GPS and compass placement
- [ ] Inspect power/motor wiring near navigation sensors
- [ ] Review ArduPilot flight logs
- [ ] Measure compass interference where possible
- [ ] Verify GPS quality
- [ ] Check vibration levels
- [ ] Re-test GPS position hold

**Goal:** understand whether the current drift is caused by GPS quality, compass interference, vibration, configuration, or another source.

## Phase 3 — Companion Computer

- [ ] Mount NVIDIA Jetson Orin Nano
- [ ] Establish a safe power solution
- [ ] Install required software
- [ ] Connect Jetson to the flight controller
- [ ] Verify bidirectional MAVLink communication

**Goal:** allow onboard software to read vehicle telemetry and eventually provide navigation information.

## Phase 4 — ROS 2 Integration

- [ ] Set up ROS 2 Jazzy workspace
- [ ] Create vehicle-interface package
- [ ] Publish attitude and vehicle-state data
- [ ] Add launch configuration
- [ ] Add logging and visualization

**Goal:** expose the drone's state to a modular ROS 2 robotics stack.

## Phase 5 — Camera and SLAM

- [ ] Mount camera
- [ ] Publish camera stream
- [ ] Calibrate camera
- [ ] Evaluate visual odometry / SLAM options
- [ ] Produce a stable local pose estimate
- [ ] Test localization while the drone is stationary
- [ ] Test localization during controlled movement

**Goal:** obtain position and orientation estimates without depending on GPS.

## Phase 6 — GPS-Denied Position Hold

- [ ] Transform SLAM pose into the required coordinate frame
- [ ] Send local-position information to ArduPilot
- [ ] Validate estimator behavior
- [ ] Perform tethered or highly controlled tests
- [ ] Tune position-hold behavior
- [ ] Measure drift and repeatability

**Goal:** hold the drone near a commanded position using onboard localization.

## Phase 7 — Autonomous Navigation

Possible future work:

- [ ] waypoint navigation,
- [ ] trajectory generation,
- [ ] path planning,
- [ ] obstacle-aware planning,
- [ ] autonomous takeoff and landing.

This phase is intentionally future work and is not represented as a current capability.
