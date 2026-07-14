<hr>
<h1 align="center">Learning Resources - Task 2</h1>
<hr>

These resources will help you complete **Task 2: Flooded Industrial District**.

Go through each topic in order before attempting the problem statement.

---

## Topics for Task 2

| Topic | Description |
|-------|-------------|
| [Introduction to Sensors](../../learn/e-PuckProgramming/Sensors/intro_to_sensors.md) | Overview of e-puck sensors |
| [Ground Sensors](../../learn/e-PuckProgramming/Sensors/ground_sensors.md) | Reading and interpreting ground sensor values |
| [Designing Controllers](../../learn/e-PuckProgramming/Controllers/designing_controllers.md) | Overview of robot controller design |
| [Line Follower (Proportional)](../../learn/e-PuckProgramming/Controllers/proportional_controller_LF.md) | Implementing a proportional line-following controller |
| [Colour Detection](../../learn/OpenCV/ColourDetection.md) | Detecting coloured floor markers |

---

## Key Functions for Task 2

```python
# Get and enable ground sensors
gs_names = ['gs0', 'gs1', 'gs2']
gs = []
for name in gs_names:
    sensor = robot.getDevice(name)
    sensor.enable(timestep)
    gs.append(sensor)

# Read ground sensor values in the main loop
gs_values = [gs[i].getValue() for i in range(3)]

# gs_values[0] = left sensor
# gs_values[1] = centre sensor
# gs_values[2] = right sensor

# Threshold for detecting the black line
LINE_THRESHOLD = 500  # values below this indicate the black line

# Simple proportional line-following
error = gs_values[0] - gs_values[2]
left_speed  = MAX_SPEED - error * Kp
right_speed = MAX_SPEED + error * Kp

leftMotor.setVelocity(left_speed)
rightMotor.setVelocity(right_speed)
```

---

> **NOTE!** <span style="color:red">Ground sensor values depend on surface brightness. Calibrate your threshold by printing sensor values on the actual arena world file.</span>