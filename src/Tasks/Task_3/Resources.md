<hr>
<h1 align="center">Learning Resources - Task 3</h1>
<hr>

These resources will help you complete **Task 3: Landslide Triage**.

Go through each topic in order before attempting the problem statement.

---

## Topics for Task 3

| Topic | Description |
|-------|-------------|
| [Edge Detection](../../learn/OpenCV/EdgeDetection.md) | Detecting object boundaries using Canny, Sobel, and Laplacian |
| [Shape Detection](../../learn/OpenCV/shape_detection.md) | Identifying geometric shapes from contours |
| [Colour Detection](../../learn/OpenCV/ColourDetection.md) | Detecting and classifying coloured survivor beacons |
| [Finite State Machines](../../learn/e-PuckProgramming/Controllers/fsm.md) | Designing FSM-based robot behaviour |
| [Intro to Controllers](../../learn/e-PuckProgramming/Controllers/intro_to_controllers.md) | Understanding how robot controllers are structured |

---

## Key Functions for Task 3

```python
# Edge detection
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
blurred = cv2.GaussianBlur(gray, (5, 5), 0)
edges = cv2.Canny(blurred, 50, 150)

# Find contours from edges
contours, _ = cv2.findContours(edges, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)

# Approximate shape from contour
for cnt in contours:
    area = cv2.contourArea(cnt)
    if area < 500:
        continue  # ignore small noise contours

    perimeter = cv2.arcLength(cnt, True)
    approx = cv2.approxPolyDP(cnt, 0.04 * perimeter, True)
    vertices = len(approx)

    if vertices == 3:
        shape = "Triangle"
    elif vertices == 4:
        shape = "Rectangle"
    elif vertices == 5:
        shape = "Pentagon"
    else:
        shape = "Circle"

# FSM example
state = "SEARCH"

while robot.step(timestep) != -1:
    if state == "SEARCH":
        # rotate and scan for survivors
        if survivor_detected():
            state = "NAVIGATE"

    elif state == "NAVIGATE":
        # move towards survivor
        if at_survivor():
            state = "RESCUE"

    elif state == "RESCUE":
        # pick up survivor
        state = "DELIVER"

    elif state == "DELIVER":
        # take survivor to correct medical camp
        state = "SEARCH"
```

---

> **NOTE!** <span style="color:red">In Task 3, survivor priorities change over time. Your FSM must handle priority updates dynamically, not just at the time of first detection.</span>