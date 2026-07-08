<h2><center> Ground Sensor </center></h2>

<hr>

*Ground sensors* or *Line Sensors* are used to sense the surface that is below the robot. These sensors make use of infrared light to detect the color of the surface underneath the robot.  

<p align="center">
<img src="./images/sensors/ground sensor.png" width=400 height=300>
</p>

### How does it work?
Ground sensors work by emitting infrared light downwards and detecting the amount of light that is reflected back. Different colours tend to reflect different amounts of light. For example

<ol>
<li><strong>Light surfaces:</strong> reflect a lot of infrared light.</li>
<li><strong>Dark surfaces:</strong> reflect very little infrared light.</li>
</ol>

By measuring how much light is reflected from the surface, the sensors can tell if the robot is on a white,black or any other coloured surface.

### Ground Sensors on the e-puck 

The e-puck in webots can be equipped with 3 ground sensors names gs0,gs1 and gs2. These sensors have a slot below the robot body to be able to detect the surface under the robot. These are place in the following order

- **gs0:** Left ground sensor
- **gs1:** Middle ground sensor
- **gs2:** Right ground sensor

### Initializing the Ground sensor in Webots

```python
gs = []
for i in range(3):
    gs.append(robot.getDevice('gs' + str(i)))
    gs[-1].enable(timestep)
```

<ol>
<li><strong>gs = []:</strong> This line initializes an empty list to store the ground sensor objects.</li>
<br>
<li><strong>robot.getDevice('gs' + str(i)):</strong>This method gets the device named 'gs0', 'gs1', and 'gs2' in each iteration by concatenating 'gs' with the current value of i. These are the names of the ground sensors on the e-puck robot.</li>
<br>
<li><strong>gs.append():</strong>This line adds the sensor object to the gs list.</li>
<br>
<li><strong>gs[-1].enable(timestep):</strong>This enables the most recently added sensor (i.e., the last element in the gs list) with the specified time step. Enabling the sensor activates it so that it starts taking readings at each time step.</li>
</ol>

### Reading the Ground Sensor values 

```python 
  while robot.step(timestep) != -1:
    g = [gsensor.getValue() for gsensor in gs]
    print(g)
```

<ol>
<li><strong>g = [gsensor.getValue() for gsensor in gs]:</strong> This line initializes an empty list to store the ground sensor objects.</li>
<br>
<li><strong>[gsensor.getValue() for gsensor in gs]:</strong>This method gets the device named 'gs0', 'gs1', and 'gs2' in each iteration by concatenating 'gs' with the current value of i. These are the names of the ground sensors on the e-puck robot.</li>
<br>
<li><strong>getValue():</strong>returns the current reading from the sensor.</li>
</ol>






