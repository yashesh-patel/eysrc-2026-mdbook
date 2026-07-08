<!-- <h1><center> Controllers</center></h1>

<hr>

In this module, you will find the following :
1. [Introduction to Controls](./Controllers/intro_to_controllers.md)
2. [Designing Controllers](./Controllers/designing_controllers.md)
3. [Bang Bang Controller](./Controllers/bang_bang_controller.md)
4. [Proportional Controller](./Controllers/proportional_controller.md)
5. [Bang Bang Controller LF](./Controllers/bang_bang_LF.md)
6. [Proportional Controller LF](./Controllers/proportional_controller_LF.md)
5. [Designing Controllers- LF](./Controllers/designing_controllers_LF.md) -->

<h2><center> Introduction to Controllers </center></h2>

<hr>

In the **Actuators Chapters**, we tried to control the robot by just understanding the behavior of the robot for different kind of motor control. That is, we tried to control the robot by purely using the knowledge of **forward and inverse kinematics**.

In **Sensors Chapters**, we used a distance measuring sensor to "react" to the environment. We modified the behaviour of the robot based on the distance measured by the sensor.

In this Section, we shall focus further on the "react" aspect of the Sensors Chapter. That is, we will focus on the algorithm that looks at the sensor data and makes corrections to the robot behavior in order to reach a desired behaviour. We call such algorithms that makes the robot behave in a *desired* way a **controller**.

## Controllers
**What is a Controller?** <br>
A controller is something that alters the *behaviour* or *state* of the system in such a way that the behaviour or outcome must tend to a state that is *desired*. The following diagram shows what a controller is trying to achieve.

<p align="center">
<img src="./images/controller.png">
</p> 

**For ex.** <br>

Self-driving cars and robots in general don’t move with perfect precision. Their trajectory can be affected by its environment (such as non-flat surfaces), and slight mis-alignments in its mechanics (such as mis-aligned wheels wheels). <br>
A human driving a car with imprecisely aligned tires can constantly self-correct to make sure they are driving straight. How can we teach a self-driving car to do the same?

<p align="center">
<img src="./images/Controller_ex1.png">
</p>
<center>Image Source: <a href="https://medium.com/@jaems33/understanding-robot-motion-pid-control-8931899c31df" target="blank">Link</a></center>

Assuming we have a desired path for the car to drive along, we can implement an algorithm known as PID Control to ensure that the car will re-align itself to the target.

**Open Loop VS Closed Loop** <br>
What we did in "Actuators Chapters" is an example of what is known as "Open Loop" Controller. And the program we wrote in the "Sensors Chapters" would be considered a beginner example of "Closed Loop" Controller. 
<br>
Can you identify the difference in the two ways to achieve a desired behaviour in our robot?
The controller we wrote in the "Actuators" Chapters can be represented in block diagram form as shown in Figure 2: Open Loop Controller. The block diagram representation of the controller that we will be designing in this chapter for following the wall is shown in Figure 3: Closed Loop Controller.

If we compare the two images does the name "Open Loop" and "Closed Loop" make more sense?


### Open Loop Controller
Open Loop Controllers are those controllers that do not take into consideration the actual state of the system (Robot) in order to decide the input (Motor Speeds) to be sent to the System (Robot).

This kind of controller requires us to know how the system (robot) will behave for certain Input and give the Input purely based on this knowledge.

One clear down side of this kind of control as you may expect is the fact that if the Robot is disturbed by some unkown factor(slipping wheel, someone pushing the robot, robot runs over a tiny object in its path, etc...) then the robot will trace a completely different shape than what was expected. 

<p align="center">
<img src="./images/open-loop.png">
</p> 
<center>Figure 2: Open Loop Controller</center>


### Closed Loop Controller

The problem discussed in Open Loop Control is tackled by Closed Loop Controller with the help of sensors and some smarter algorithm.
We measure the output of the system with a sensor, and compare the result against the desired state. This generates an error value which is then fed to a controller that adjust the input to the robot based on the error value.

In the specific example of Wall Following,
- **desired state/reference**
    - `set_dist = # The distance to be maintained from the wall`
- **sensor reading**
    - `dist_inv = # [0, 255] element of Integers inversely proportional to distance from Wall`
    - `dist = 255 - dist_inv`
- **error**
    - `error = dist - set_dist`
    - *positive error* would mean the bot is too *far from* the wall
    - *negative error* would mean the bot is too *close to* the wall
- **input**
    - the left and right wheel velocity has to be decided based on the error.
    - The *Controller* will take the *error* value and generate the *input* to be sent to the robot based on the error.

This kind of controller is also sometimes called, *Feedback Control*, *Negative Feedback Control*, *Automatic Control*. Although there is slight differences between all these terms. The *Negative* in the "Negative Feedback Loop" is because we *subtract* the sensor (feedback) value from the reference value. 

<p align="center">
<img src="./images/closed-loop.png">
</p> 
<center>Figure 3: Closed Loop Controller</center>

### Coming Up Next
In the coming chapters, we will study two different ways to design a closed loop controller. i.e. two ways to react to the error in order to maintain a steady distance between the robot and the wall in order to succesfully follow the wall.

But first we shall define a problem statement or a challenge for ourselves!

---

### References
Youtube Lecture Series "Classical Control Theory" by Brain Douglas
