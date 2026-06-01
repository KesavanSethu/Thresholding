# EX-8-THRESHOLDING

## Aim:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required:
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:

 1 Load the necessary packages
 
 2 Read the Image and convert to grayscale.
 
 3 Use Global thresholding to segment the image.
 
 4 Use Adaptive thresholding to segment the image.
 
 5 Use Otsu's method to segment the image and display the results.
 
## Developed By: KESAVAN S
## Reg No.: 212224230121


## Program:
```python
import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread('Golden Temple.jpg')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Original image
plt.subplot(2,2,1)
plt.imshow(cv2.cvtColor(image,cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

# Use Global thresholding to segment the image
_,global_thresholded = cv2.threshold(gray_img, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image
adaptive_thresholded = cv2.adaptiveThreshold(gray_img, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 
_,otsu_thresholded = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```
## Output:

### ORIGINAL IMAGE
<img width="739" height="283" alt="image" src="https://github.com/user-attachments/assets/6bd15f48-a8b1-49f7-9019-c6c2ad77df88" />

### GLOBAL THRESHOLDING
<img width="681" height="299" alt="image" src="https://github.com/user-attachments/assets/46a241f1-feab-487e-9f3d-59dba2069b65" />

### ADAPTIVE THRESHOLDING
<img width="727" height="301" alt="image" src="https://github.com/user-attachments/assets/61d57d3d-ff4c-459b-89b7-b51fda168c9d" />

### Optimum Global Thesholding using Otsu's Method
<img width="701" height="301" alt="image" src="https://github.com/user-attachments/assets/8d4a3f59-e303-48bc-84f2-d8ac85669dac" />



## Result:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
