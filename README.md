# EXP-6-EDGE-DETECTION

**Developed By:** Dharshini J  
**Register Number:** 212224240036
**Title:** Ex.No: 6 – Edge Detection 



## Aim
To implement different edge detection techniques using OpenCV and Python to identify and highlight the edges and boundaries of objects in an image.

## Software Used
- Python
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Jupyter Notebook

## Algorithm
1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Read the input image using `cv2.imread()`.
3. Convert the original image from BGR to RGB format for display.
4. Convert the original image into grayscale using `cv2.cvtColor()`.
5. Apply the Sobel operator in the X-direction and Y-direction.
6. Combine both Sobel outputs using `cv2.magnitude()` to obtain the Sobel edge detection result.
7. Apply the Laplacian operator to detect edges in the grayscale image.
8. Apply the Canny edge detection method using lower and upper threshold values of 50 and 150.
9. Display the original image and the edge detection results using Matplotlib.

## Program

### 1. Import Libraries and Display Original Image

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('car.jpeg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```

### 2. Sobel Edge Detection

```python
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)

sobel_combined = cv2.magnitude(sobel_x, sobel_y)

plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```

### 3. Laplacian Edge Detection

```python
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```

### 4. Canny Edge Detection

```python
canny_edges = cv2.Canny(gray_image, 50, 150)

plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```

## Output

The following outputs are obtained:

### i) Display the Original Image

<img width="555" height="306" alt="image" src="https://github.com/user-attachments/assets/d65efbf6-03e2-4dfe-8d46-201559e9ca63" />


### ii) Display the Sobel Edge Detection Image

<img width="520" height="315" alt="image" src="https://github.com/user-attachments/assets/b9b6e185-4ed0-499c-b781-0ccd18c3e44e" />

### iii) Display the Laplacian Edge Detection Image

<img width="550" height="322" alt="image" src="https://github.com/user-attachments/assets/b7d515fc-3356-45f0-b91d-aef9311631a6" />


### iv) Display the Canny Edge Detection Image

<img width="515" height="321" alt="image" src="https://github.com/user-attachments/assets/7f13042f-6820-4dcf-8aab-3d1b8c5e8787" />

## Result

Thus, different edge detection techniques, namely Sobel Edge Detection, Laplacian Edge Detection, and Canny Edge Detection, were successfully implemented using OpenCV and Python. The edges and boundaries of objects in the input image were detected and displayed.
