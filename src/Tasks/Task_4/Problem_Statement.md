<hr>
<h1 align="center">Task 4: Problem Statement</h1>
<hr>

## Objective

The city's transportation network has been severely damaged following the disaster. Traffic lights and navigation systems are no longer functional, forcing rescue robots to rely on **ArUCo markers** placed at road intersections for navigation.

Your objective is to program the **e-puck** robot to decode these markers, interpret the navigation instructions, and autonomously travel through the city by selecting the correct route at every intersection.

---

## Learning Outcomes

After completing this task, you will be able to:

- Detect and decode ArUCo markers.
- Interpret visual navigation instructions.
- Detect coloured directional arrows.
- Make autonomous decisions at intersections.
- Navigate through multiple checkpoints.

---

## Mission Requirements

Your controller should perform the following sequence:

1. Follow the navigation path.
2. Detect an ArUCo marker at each intersection.
3. Decode the marker.
4. Identify the assigned colour.
5. Detect the available coloured arrows.
6. Select the arrow matching the decoded colour.
7. Continue navigating until all waypoints are reached.

---

## The Arena

The arena represents an urban road network containing multiple intersections connected by black navigation lines.

Each intersection contains:

- An ArUCo marker
- Multiple coloured directional arrows
- Navigation waypoints

The robot must decode the marker before selecting the correct direction. Choosing an incorrect route may prevent the robot from reaching the remaining checkpoints.

<p align="center">
<img src="./images/arena4.jpeg" width="750">
</p>

---

## Getting Started

To begin Task 4:

1. Download the Task 4 package.
2. Open `task_4.wbt` in Webots.
3. Implement line following.
4. Detect and decode ArUCo markers.
5. Detect coloured arrows.
6. Navigate using the decoded instruction.
7. Reach all waypoints.
8. Test your controller.
9. Generate the submission package.

---

## Scoring

The final score consists of two components.

### Waypoint Score

Each successfully reached waypoint awards **10 points**.

```text
Waypoint Score = Waypoints Reached × 10
```

---

### Time Bonus

Completing the mission quickly earns additional points.

```text
Time Score = (Remaining Time / Maximum Time) × 100
```

---

### Final Score

```text
Total Score = Waypoint Score + Time Score
```

> **Higher scores are achieved by:**
>
> - Reaching every waypoint.
> - Correctly following every navigation instruction.
> - Completing the mission in the shortest possible time.

---

## Expected Output

A successful controller should:

- Follow the navigation path.
- Decode every ArUCo marker.
- Select the correct coloured arrow.
- Navigate through every intersection.
- Reach all required waypoints.
- Complete the mission before time expires.

During execution, the supervisor displays:

- Remaining mission time
- Waypoints reached
- Current navigation status
- Final score

### Please refer to the expected output video shown below.

<center><iframe width="640" height="350" src="https://www.youtube.com/embed/X9Vy4Ox6efk?si=0c1VLcaBqDpbEDlu" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></center> 

---

## Before You Submit

Before generating your submission, verify that:

- ArUCo markers are detected correctly.
- Marker decoding is accurate.
- The correct arrow is selected at every intersection.
- All waypoints are reached.
- `teaminfo.json` contains the correct Team ID.
- The submission package is generated successfully.