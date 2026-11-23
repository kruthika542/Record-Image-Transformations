## Geometric Transformations Using OpenCV

## Aim
To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation
- Image Scaling (Resizing)
- Image Shearing
- Image Reflection (Flipping)
- Image Rotation

## Software Used
- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the input image in color mode.

Step 3: Image Translation
Create a translation matrix to shift the image
Move the image 50 pixels to the right and 80 pixels down
Apply transformation using cv2.warpAffine()
Display original and translated images

Step 4: Image Scaling
Resize the image to 0.5× (downscale)
Resize the image to 2× (upscale)
Use cv2.resize()
Display original, downscaled, and upscaled images

Step 5: Image Shearing
Create transformation matrices for:
Horizontal shearing
Vertical shearing
Apply transformations using cv2.warpAffine()
Display original and sheared images

Step 6: Image Reflection
Perform flipping using cv2.flip():
Horizontal reflection
Vertical reflection
Both axes
Display all reflected images

Step 7: Image Rotation
Create rotation matrices for:
45° rotation
90° rotation
Use cv2.getRotationMatrix2D() and cv2.warpAffine()
Display original and rotated images

## Program
Developed By:
Name:Kruthika R
Register No:212225240075

## 1.Import Libraries
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

## 2.Read Input Image
```
img = cv2.imread('image.jpg')

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

height, width = img.shape[:2]

plt.imshow(img)
plt.title("Original Image")
plt.axis('off')
plt.show()
```

## 3.Image Translation
```
M = np.float32([[1, 0, 50],
                [0, 1, 80]])

translated = cv2.warpAffine(img, M, (width, height))

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(translated)
plt.title("Translated Image")
plt.axis('off')

plt.show()
```
## 4.Image Scaling
```
downscaled = cv2.resize(img, None, fx=0.5, fy=0.5)

upscaled = cv2.resize(img, None, fx=2, fy=2)

plt.figure(figsize=(12, 5))

plt.subplot(1, 3, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(downscaled)
plt.title("Downscaled (0.5x)")
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(upscaled)
plt.title("Upscaled (2x)")
plt.axis('off')

plt.show()
```
## 5.Image Shearing
```
# Horizontal Shearing
M1 = np.float32([[1, 0.5, 0],
                 [0, 1, 0]])

horizontal_shear = cv2.warpAffine(
    img, M1, (width + int(0.5 * height), height)
)

# Vertical Shearing
M2 = np.float32([[1, 0, 0],
                 [0.5, 1, 0]])

vertical_shear = cv2.warpAffine(
    img, M2, (width, height + int(0.5 * width))
)

plt.figure(figsize=(12, 5))

plt.subplot(1, 3, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(horizontal_shear)
plt.title("Horizontal Shearing")
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(vertical_shear)
plt.title("Vertical Shearing")
plt.axis('off')

plt.show()
```
## 6.Image Reflection
```
horizontal_flip = cv2.flip(img, 1)

vertical_flip = cv2.flip(img, 0)

both_flip = cv2.flip(img, -1)

plt.figure(figsize=(12, 7))

plt.subplot(2, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(2, 2, 2)
plt.imshow(horizontal_flip)
plt.title("Horizontal Reflection")
plt.axis('off')

plt.subplot(2, 2, 3)
plt.imshow(vertical_flip)
plt.title("Vertical Reflection")
plt.axis('off')

plt.subplot(2, 2, 4)
plt.imshow(both_flip)
plt.title("Both Axis Reflection")
plt.axis('off')

plt.show()
```
## 7.Image Rotation
```
# Rotate by 45 degrees
M45 = cv2.getRotationMatrix2D(
    (width // 2, height // 2), 45, 1
)

rotated_45 = cv2.warpAffine(img, M45, (width, height))

# Rotate by 90 degrees
M90 = cv2.getRotationMatrix2D(
    (width // 2, height // 2), 90, 1
)

rotated_90 = cv2.warpAffine(img, M90, (width, height))

plt.figure(figsize=(12, 5))

plt.subplot(1, 3, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(rotated_45)
plt.title("Rotation 45 Degrees")
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(rotated_90)
plt.title("Rotation 90 Degrees")
plt.axis('off')

plt.show()
```
## Output

## Original image
<img width="313" height="410" alt="image" src="https://github.com/user-attachments/assets/4efee3f9-9d3a-4965-a7b6-b59f745143a8" />

## Image Translation
<img width="785" height="428" alt="image" src="https://github.com/user-attachments/assets/c0c7cfb5-4260-47d0-801e-4a674dc082d4" />

## Image Scaling
<img width="961" height="382" alt="image" src="https://github.com/user-attachments/assets/160ee24b-6d2a-4eb4-9e56-a190afba6f41" />

## Image Shearing
<img width="940" height="427" alt="image" src="https://github.com/user-attachments/assets/f387266b-4964-4c87-abc7-13096538a7a9" />

## Image Reflection
<img width="710" height="585" alt="image" src="https://github.com/user-attachments/assets/b4b18ab3-fff9-465b-b213-b876b9f9f8b6" />

## Image Rotation
<img width="947" height="386" alt="image" src="https://github.com/user-attachments/assets/e67033e3-e28c-47ab-bfc5-d062ed469c8e" />

## Result
Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
