
# Loading and Displaying an Image

---

## Example: Load and Show an Image with OpenCV

```python
import cv2
# Load the image
image = cv2.imread("your_image.jpg")
# Show the image
cv2.imshow("My First Image", image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
<p align="center">
  <img src="./images/MyFirstImage.png" alt="It's an apple" width="350"/>
</p>

---

### What Happens Here:

- `cv2.imread()` loads the image
- `cv2.imshow()` displays the image
- `cv2.waitKey(0)` waits for a key press before closing

> **Note:** Make sure the image file (e.g., `your_image.jpg`) is in the same folder as your Python script, or give the full path.
