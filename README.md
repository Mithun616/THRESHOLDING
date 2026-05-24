# THRESHOLDING

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

---

## Software Required
1. Anaconda - Python 3.7  
2. OpenCV  

---

## Algorithm

### Step1:
Import the required libraries such as OpenCV and Matplotlib.

### Step2:
Read the input image and convert it into grayscale image.

### Step3:
Apply Global Thresholding using `cv2.threshold()`.

### Step4:
Apply Adaptive Thresholding using `cv2.adaptiveThreshold()`.

### Step5:
Apply Otsu’s Thresholding using `cv2.threshold()` with `cv2.THRESH_OTSU` and display all the results.

---

## Program

```python
# Load the necessary packages
import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image = cv2.imread("road_lanes.png")
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Use Global thresholding to segment the image
ret, global_thresh = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image
adaptive_thresh = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

# Use Otsu's method to segment the image
ret2, otsu_thresh = cv2.threshold(
    gray,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

# Display the results
plt.figure(figsize=(15,10))

plt.subplot(2,2,1)
plt.imshow(gray, cmap='gray')
plt.title("Original Grayscale Image")
plt.axis("off")

plt.subplot(2,2,2)
plt.imshow(global_thresh, cmap='gray')
plt.title("Global Thresholding")
plt.axis("off")

plt.subplot(2,2,3)
plt.imshow(adaptive_thresh, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis("off")

plt.subplot(2,2,4)
plt.imshow(otsu_thresh, cmap='gray')
plt.title("Otsu Thresholding")
plt.axis("off")

plt.show()
```

---

## Output

### Global Thresholding

<img width="824" height="224" alt="image" src="https://github.com/user-attachments/assets/a3bfff31-191e-4782-b278-015b9ba23b3d" />

### Adaptive Thresholding

<img width="804" height="224" alt="image" src="https://github.com/user-attachments/assets/6188b3ad-ed84-4cbe-a3eb-ffbbeb3194b9" />


### Optimum Global Thresholding using Otsu's Method

<img width="805" height="220" alt="image" src="https://github.com/user-attachments/assets/af027662-9fa5-47f1-beb2-47c96ade32a1" />


---

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
