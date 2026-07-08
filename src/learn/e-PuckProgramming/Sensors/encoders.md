<h1><center> Rotary Encoders </center></h1>


### Background and initialization:

Rotary encoders allow us to measure the position(angle) of a rotating shaft. They are typically used with motors to measure the motor's speed and angle. Do go through this [Wikipedia entry](https://en.wikipedia.org/wiki/Rotary_encoder) for a nice overview!

On the e-puck robot available to us these rotary encoders are available to us in the form of a device called [Position Sensors](https://cyberbotics.com/doc/reference/positionsensor), do not confuse these with the proximity sensors. The values given by these sensors keep on increasing or decreasing as the wheels turn. The values are the total angle rotated by the wheel center in radians, which means if the wheel completes one complete revolution, the value on the sensor will be incremented by 2π. The sensors on the e-puck robot do not have noise and their output value is the total angle covered in radians.

Each wheel on the e-puck robot has a Position Sensor associated with it. They are named "left wheel sensor" and "right wheel sensor" for the left and right wheels respectively.

You can initialize them as follows
```python
left_encoder = robot.getDevice('left wheel sensor')
left_encoder.enable(timestep)
right_encoder = robot.getDevice('right wheel sensor')
right_encoder.enable(timestep)
```
The enable function has a disable counterpart, this enabling/disabling feature is included to conserve CPU processing resources. But in our application, the load on the CPU is negligible hence we will keep them enabled all the time.

As mentioned above, the encoders keep on updating their value as the motors turn.
These values are also commonly referred to as ticks, imagine them like ticks of the seconds hand in a clock, and just as the seconds hand has a resolution of 60, i.e. there are 60 different values it can attain in the course of a rotation, all encoders have a certain resolution.
In our case on the e-puck robot, the resolution is set to 1000, i.e. it is possible for the encoder to sense and return values in increments of 2π÷1000 radians. That is around 0.00628 radians or about 0.4 degrees.
The latest value of the encoder can be accessed by these two functions: 

```python
left_encoder_ticks = left_encoder.getValue()
right_encoder_ticks = right_encoder.getValue()
```
Note that unlike the hands on a clock, these ticks are incremental, i.e. they don't tick over or reset. This also means that the values increase if the motor turns in one direction, and decrease if it turns in the opposite direction, this means the values can also be negative.

<hr>

## Using Encoder Values

### Calculation of Distance for a Single Wheel:

Let’s denote the radius of the wheel as ```R``` . In this example, we’ll assume  **R = 20mm**.

- For every full wheel revolution, it covers a distance of ```2piR```, in the same unit as ```R```, which is mm here.
- This relationship remains true for a straight or a curved path as long as the wheel does no slip 

Thus, the distance traveled by the wheel can be found with:

$$
\text{distance} = \text{angle} \times R
$$

where `angle` is in radians. For a circular path, the angle covered would be ```2pi``` radians or 360 degrees, resulting in a distance of ```2piR```

So, to move a certain distance, we can calculate the required wheel rotation angle.

---

### Calculations Related to the Robot Center:

Now, let’s consider the robot center rather than the wheels.

#### 1: Calculating Distance Traveled by the Robot Center

- If both wheels move at the same speed, the robot moves straight, and the distance traveled by the robot center is equal to the wheel's distance.
- If the wheels move at slightly different speeds, the average of the encoder ticks provides an estimate for the robot center's traveled distance.

The formula for the distance covered by the robot center is:

$$
\text{distance} = \frac{(\text{left\_encoder\_ticks} + \text{right\_encoder\_ticks}) \times R}{2}
$$

Multiplying by the wheel radius converts the ticks to actual distance.

#### 2: Calculating the Angle of the Robot Center

To determine the robot's heading direction, we need to calculate the robot's current angle.

We need to know the robot's axle length, denoted as ```L```. In this case, we’ll assume **L = 58mm**.

Since the two wheels are linked by the axle, the robot turns when one wheel rotates more than the other. This can be calculated by taking the difference between the left and right encoder ticks, multiplying by the wheel radius, and dividing by the axle length.

The angle in radians can be given as:

$$
\text{angle} = \left( \frac{(\text{left\_encoder\_ticks} - \text{right\_encoder\_ticks}) \times R}{L} \right) \text{%} (2\pi)
$$

- The modulo operator (%) keeps the angle within 0 and 2pi radians or 0-360 Degrees.
- To convert this angle into degrees, simply multiply by: ```180/pi```
- You can calculate the angle either in a clockwise (CW) or an counter-clockwise (CCW) direction, depending upon which way you do the subtraction above i.e. whether 50° CW should be 50°? Or 50° CCW should be 50°? This is important because 50° CW is 310° CCW.

<!-- 


### Using encoder values:

#### Calculation of distance for a single wheel:

- Let us continue our notation from the previous Task, and let R be the radius of the wheel. 
- For this task we will consider it be to ```20mm```.
- Thus, for every revolution of the wheel, it will have covered a distance of 2πR (units being the units of R, i.e. mm in our case because we will define R in mm)
- This distance might be in a straight or curved line, this does not matter. As long as the wheel is not slipping, we are guaranteed that it will cover a distance of 2πR units.
- Thus now we have a relationship between how much the motor is turning and how far the robot is going. i.e. ```distance = angle * R``` where the ```angle``` is in radians and the ```distance``` is in the units of ```R```. For example for moving in a circle the total angle covered will be 2π or 360 degrees which means the distance covered will be equal to the circumference. ```distance=2*pi*R```
- Now if we want the wheel to travel a certain distance we know by what angle to turn it!



#### Calculations related to the robot center:


All of this is fine for one wheel, but our robot has two of them! Along with a whole lot of other stuff! We will consider the robot center now instead of the wheels.

**1: Calculating distance traveled by the robot center**

- If both the wheels turn at the same speed the bot moves straight as seen in [Basics of Differential Drive](./Actuators/differential_drive.mdown) in the actuators chapter, which means the distance travelled by the robot center is also the same.

- If the speeds of the wheels vary slightly, the average of encoder ticks will give an estimate on the distance travelled by the robot center.

**To calculate the distance traveled by the robot center**
$$
\text{distance} = \frac{(\text{left\_encoder\_ticks} + \text{right\_encoder\_ticks}) \times \text{R}}{2}
$$

- This average is multiplied with the radius of wheel to convert the ticks to actual distance 
- This works for any combination of straight and curved paths. 

**2: Calculating the angle of the robot center**

- If you want to know which way a robot is headed or is facing, calculating the present angle of the robot is needed.

- This requires us to have knowledge of the axle length of the robot, denoted as L. In this task, we will consider L as ```52mm```.

- Since the two wheels are rigidly linked via the axle, the robot turns when one wheel rotates more than the other. This  can be calculated by taking the difference of the left & right encoder ticks multiplied by the wheel radius and divided by the axle length!

#### *The angle in radians can be given as*
$$
\text{angle} = \left( \frac{(\text{left\_encoder\_ticks} - \text{right\_encoder\_ticks}) \times \text{R}}{\text{L}} \right) \text{%} (2\pi)
$$

- Here the % sign is the modulo operator, it will keep the angle ranges between 0 & 2π.
- To convert this angle into degrees, simply multiply it by 180 / π.
- You can calculate the angle either in a clockwise (CW) or an counter-clockwise (CCW) direction, depending upon which way you do the subtraction above i.e. whether 50° CW should be 50°? Or 50° CCW should be 50°? This is important because 50° CW is 310° CCW. -->

---

**Exercises**

- Practicing is essential in becoming good at anything, could you solve the [Tracing Polygons](./tracing_polygons.mdown) and [Tracing Circles](./tracing_circles.mdown) exercises but now with encoders instead!? All the best!