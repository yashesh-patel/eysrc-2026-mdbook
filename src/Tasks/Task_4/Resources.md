<hr>
<h1 align="center">Learning Resources - Task 4</h1>
<hr>

These resources will help you complete **Task 4: Urban Gridlock**.

Go through each topic in order before attempting the problem statement.

---

## Topics for Task 4

| Topic | Description |
|-------|-------------|
| [ArUco Marker Detection](../../learn/OpenCV/aruco.md) | Detecting and decoding ArUco markers using OpenCV |
| [Arrow Detection](../../learn/OpenCV/arrow_detection.md) | Detecting coloured directional arrows from the camera |
| [Colour Detection](../../learn/OpenCV/ColourDetection.md) | Identifying the colour of arrows at intersections |
| [Line Follower (Proportional)](../../learn/e-PuckProgramming/Controllers/proportional_controller_LF.md) | Line following between intersections |
| [Ground Sensors](../../learn/e-PuckProgramming/Sensors/ground_sensors.md) | Detecting intersections via ground sensors |

---

## Key Functions for Task 4

```python
import cv2
import cv2.aruco as aruco
import numpy as np

# Setup ArUco dictionary and parameters
aruco_dict = aruco.getPredefinedDictionary(aruco.DICT_4X4_50)
parameters = aruco.DetectorParameters()
detector = aruco.ArucoDetector(aruco_dict, parameters)

# Detect markers in camera image
corners, ids, rejected = detector.detectMarkers(image)

# Get marker ID
if ids is not None:
    marker_id = ids[0][0]
    print(f"Detected marker ID: {marker_id}")

# Map ID to navigation colour
# (this mapping depends on your task-specific instructions)
id_to_colour = {
    1: "Red",
    2: "Yellow",
    3: "Blue",
    4: "Green"
}

if ids is not None:
    target_colour = id_to_colour.get(marker_id, None)

# Arrow detection using contour convex hull
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
_, thresh = cv2.threshold(gray, 100, 255, cv2.THRESH_BINARY_INV)
contours, _ = cv2.findContours(thresh, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)

for cnt in contours:
    hull = cv2.convexHull(cnt, returnPoints=False)
    defects = cv2.convexityDefects(cnt, hull)
    # Use defects to identify arrow direction
```

---

> **NOTE!** <span style="color:red">ArUco marker detection is sensitive to lighting and camera resolution. Test your detection under the exact arena lighting conditions before submission.</span>