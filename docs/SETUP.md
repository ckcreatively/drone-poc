# Setup - Drone PoC (Ubuntu 22.04 VM + macOS Host)

## Overview
- Ubuntu VM: PX4 + simulator
- macOS Host: QGroundControl UI

## Gate 0: VM sanity checks
Run in Ubuntu:
- `gazebo --version`
- `pkg-config --modversion gazebo`
- `glxinfo | grep "OpenGL renderer"`

Expected: Gazebo 11.x and VMware SVGA3D renderer.

## Gate 1: PX4 install + deps
Clone PX4:
- `git clone https://github.com/PX4/PX4-Autopilot.git --recursive`
- `cd PX4-Autopilot`

Run deps script:
- `bash ./Tools/setup/ubuntu.sh`

## Gate 2: Run SITL + sim
(Commands will be finalized once PX4 build path is verified.)
Goal: simulator opens and vehicle spawns.

## Gate 2b: QGroundControl connection
Install and run QGroundControl on macOS.
Goal: QGC shows vehicle telemetry from SITL (via UDP).

## Gate 3: Offboard control
Run MAVSDK takeoff/land script connected to SITL.

## Notes
We add layers only after the previous gate is stable and repeatable.
