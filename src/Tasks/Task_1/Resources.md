<hr>
<h1 align="center">Learning Resources - Task 1</h1>
<hr>

These resources will help you complete **Task 1: Military Supply Drop**.

Go through each topic in order before attempting the problem statement.

---

## Topics for Task 1

| Topic | Description |
|-------|-------------|
| [Introduction to OpenCV](../../learn/OpenCV/Opencv.md) | What OpenCV is and how it processes images |
| [Colour Spaces](../../learn/OpenCV/ColourSpacing.md) | Understanding BGR, HSV, and why we use HSV for colour detection |
| [Colour Detection](../../learn/OpenCV/ColourDetection.md) | Detecting coloured objects using HSV ranges and masks |
| [OpenCV in Webots](../../learn/OpenCV/OpencvWebots.md) | Accessing the robot's camera and using OpenCV in a Webots controller |
| [Grayscaling](../../learn/OpenCV/Grayscaling.md) | Converting images to grayscale |
| [Thresholding](../../learn/OpenCV/Thresholding.md) | Binary thresholding and its uses |

---

## Key OpenCV Functions for Task 1

```python
# Get camera image from Webots
camera = robot.getDevice('camera')
camera.enable(timestep)
image = camera.getImage()

# Convert Webots image to OpenCV format
import numpy as np
import cv2

img = np.frombuffer(image, np.uint8).reshape(
    (camera.getHeight(), camera.getWidth(), 4)
)
img_bgr = cv2.cvtColor(img, cv2.COLOR_BGRA2BGR)

# Convert to HSV for colour detection
hsv = cv2.cvtColor(img_bgr, cv2.COLOR_BGR2HSV)

# Create a colour mask
lower = np.array([H_low, S_low, V_low])
upper = np.array([H_high, S_high, V_high])
mask = cv2.inRange(hsv, lower, upper)

# Find contours (blobs of colour)
contours, _ = cv2.findContours(mask, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)

# Get largest contour
if contours:
    largest = max(contours, key=cv2.contourArea)
    area = cv2.contourArea(largest)
    x, y, w, h = cv2.boundingRect(largest)
    cx = x + w // 2  # centre x of detected colour
```

---

> **NOTE!** <span style="color:red">Make sure you understand HSV colour space before starting the task. Choosing the right HSV range is critical for reliable colour detection.</span>