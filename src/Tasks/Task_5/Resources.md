<hr>
<h1 align="center">Learning Resources - Task 5</h1>
<hr>

**Task 5: Terminal Evacuation** does not introduce new concepts.

It requires you to integrate everything you have learned across Tasks 1 through 4 into a single autonomous system.

---

## Review These Resources Before Starting

| Topic | Where to Find It |
|-------|-----------------|
| Proximity Sensors | [Working with Proximity Sensors](../../learn/e-PuckProgramming/Sensors/obstacle_avoidance.md) |
| Rotary Encoders | [Working with Rotary Encoders](../../learn/e-PuckProgramming/Sensors/encoders.md) |
| Wall Following | [Proportional Wall Follower](../../learn/e-PuckProgramming/Controllers/proportional_controller.md) |
| ArUco Detection | [ArUco Markers](../../learn/OpenCV/aruco.md) |
| Line Following | [Proportional Line Follower](../../learn/e-PuckProgramming/Controllers/proportional_controller_LF.md) |
| Behaviour Switching | [Finite State Machines](../../learn/e-PuckProgramming/Controllers/fsm.md) |

---

## What You Need to Integrate

**Phase 1 - Maintenance Tunnel:**

```python
# Wall following using proximity sensors
ps0 = robot.getDevice('ps0')
ps7 = robot.getDevice('ps7')
ps0.enable(timestep)
ps7.enable(timestep)

# Read proximity values
left_wall  = ps5.getValue()
right_wall = ps2.getValue()

# Proportional wall follower
error = right_wall - left_wall
left_speed  = BASE_SPEED + Kp * error
right_speed = BASE_SPEED - Kp * error
```

**Phase 2 - Railway Terminal:**

```python
# Switch to line following
# (Reuse your Task 2 / Task 4 line-following code)

# Navigate to rescue locations in the order stored from Phase 1
for target in rescue_sequence:
    navigate_to(target)
    rescue()
```

---

> **NOTE!** <span style="color:red">Focus on clean behaviour switching between Phase 1 and Phase 2. Use an FSM to manage the transition cleanly.</span>