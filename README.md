# Exp-8  Thresholding

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
Anaconda - Python 3.7
OpenCV

## Algorithm
### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

### Program
#### NAME : Meyyappan T
#### REG NO : 212223240086

#### Step 1: Import the necessary libraries
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
#### Step 2: Read the image and convert to grayscale
```
image = cv2.imread('handwritten.jpg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
```

#### Step 3: dispay the original image
```
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
```
<img width="257" height="227" alt="image" src="https://github.com/user-attachments/assets/3a743cbd-281b-49b8-8c0a-2b3f33ebe2a8" />


#### Step 4: Use Global Thresholding to segment the image
```
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
```

#### Step 5: Use Adaptive Thresholding to segment the image

```
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```

#### Step 6: Use Otsu's method to segment the image

```
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


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
#### Global Thresholding
<img width="310" height="263" alt="image" src="https://github.com/user-attachments/assets/46d28ef3-39be-4f82-8acf-823438cb6d9a" />



#### Adaptive Thresholding
<img width="271" height="277" alt="image" src="https://github.com/user-attachments/assets/68b168eb-7935-4623-a668-679117a46313" />



#### Otsu's Method

<img width="278" height="267" alt="image" src="https://github.com/user-attachments/assets/bc387ee1-1abb-4066-a777-06fe846992b5" />


## Result:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
