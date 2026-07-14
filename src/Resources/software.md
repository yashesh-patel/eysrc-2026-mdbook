# Software and Reference Materials

This page lists the software required for the project, along with useful reference links and learning materials.

---

## Required Software

| Software | Purpose | Download |
|----------|---------|---------|
| Webots R2025a | Robot simulation environment | [cyberbotics.com](https://cyberbotics.com/#download) |
| Python 3.14 | Programming language | [python.org](https://www.python.org/downloads/) |
| Visual Studio Code | Code editor (recommended) | [code.visualstudio.com](https://code.visualstudio.com/) |
| Git | Version control | [git-scm.com](https://git-scm.com/) |

---

## Python Library Installation

Install the required Python libraries using pip:

```bash
pip install numpy opencv-python opencv-contrib-python pycryptodome
```

The `opencv-contrib-python` package is required for ArUco marker detection.

---

## Official Documentation

| Topic | Link |
|-------|------|
| Webots Documentation | [docs.cyberbotics.com](https://docs.cyberbotics.com/) |
| OpenCV Documentation | [docs.opencv.org](https://docs.opencv.org/) |
| Python Documentation | [docs.python.org](https://docs.python.org/3/) |
| NumPy Documentation | [numpy.org/doc](https://numpy.org/doc/) |

---

## Reference Material

### Robotics Concepts

| Topic | Description |
|-------|-------------|
| Differential Drive Robot | How two-wheeled robots turn and move |
| PID Control | Proportional-Integral-Derivative controller theory |
| Finite State Machines | Modelling behaviour with states and transitions |
| Odometry | Estimating robot position from wheel encoders |
| Proportional Controller | Simplified feedback control for line/wall following |

---

### Computer Vision

| Topic | Description |
|-------|-------------|
| HSV Colour Space | Hue-Saturation-Value vs BGR for colour detection |
| Thresholding | Binary image creation from grayscale |
| Contour Detection | Finding object boundaries in images |
| Shape Detection | Identifying circles, triangles, rectangles, polygons |
| ArUco Markers | Fiducial markers for robot localisation and navigation |
| Canny Edge Detection | Detecting object edges in images |
| Morphological Operations | Erosion, dilation, opening, closing for noise removal |

---

### Webots Specific

| Topic | Description |
|-------|-------------|
| Camera Sensor API | Accessing camera images in Python controllers |
| Distance Sensor API | Reading proximity sensor values |
| Ground Sensor API | Reading reflectance from ground sensors |
| Motor API | Controlling wheel speed and position |
| Supervisor API | Accessing world state and object positions |
| Rotary Encoder API | Reading wheel rotation from position sensors |

---

## Going Further (Advanced Topics)

For those who want to explore beyond the course material:

| Topic | Where to Start |
|-------|---------------|
| PID Controller | [Wikipedia: PID Controller](https://en.wikipedia.org/wiki/PID_controller) |
| Simultaneous Localisation and Mapping (SLAM) | [OpenSLAM](https://openslam-org.github.io/) |
| Robot Operating System (ROS) | [ros.org](https://www.ros.org/) |
| Deep Learning for Robotics | [OpenCV DNN Module](https://docs.opencv.org/4.x/d2/d58/tutorial_table_of_content_dnn.html) |
| Path Planning Algorithms | [Red Blob Games](https://www.redblobgames.com/) |