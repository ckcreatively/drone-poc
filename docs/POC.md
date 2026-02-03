# Proof of Concept (PoC) - Drone Stack

## Objective
Demonstrate a stable end-to-end loop:
PX4 SITL runs, simulator launches, QGroundControl connects, basic flight works, offboard control works, and a video pipeline stub proves the path for camera integration.

## Success Criteria (Pass/Fail)
- [ ] PX4 builds on Ubuntu 22.04 using documented steps
- [ ] SITL launches successfully 3/3 times
- [ ] QGroundControl connects (heartbeat + attitude visible)
- [ ] Manual flight test: Arm -> Takeoff -> Hover -> Land
- [ ] Offboard test (MAVSDK): scripted takeoff + land succeeds
- [ ] Video stub: a test stream can be viewed (even a test pattern)
- [ ] Reproducible: a new machine can follow docs/SETUP.md and repeat the above

## Non-goals (for PoC)
- Autonomy, mapping, obstacle avoidance
- Real camera hardware
- ROS2 (optional later layer)
- Custom UI beyond QGroundControl

## Deliverables
- docs/SETUP.md
- docs/POC.md
- scripts/run_sitl.sh
- scripts/offboard_takeoff_land.py
- docs/VIDEO.md (later)

## Risks / Mitigations
- VM graphics limitations: run QGroundControl on macOS host
- Package manager locks: disable unattended-upgrades during dev sessions if needed
- Simulator migration (Gazebo Classic -> GZ): keep launch scripts isolated so simulator is swappable
