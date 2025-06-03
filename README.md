# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
- **Step1:** Load the necessary packages.

- **Step2:** Read the Image and convert to grayscale.

- **Step3:** Use Global thresholding to segment the image.

- **Step4:** Use Adaptive thresholding to segment the image.

- **Step5:** Use Otsu's method to segment the image and display the results.

## Program
```
NAME : S.VENGADA KRISHNAN
REG : 212223110061
```

```python
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
# Read the Image and convert to grayscale

image = cv2.imread('flight.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('flight.jpg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()


```

<br>
<br>

## Output

### Original Image
<img src = "https://github.com/Adhithyaram29D/Thresholdingg/assets/119393540/39a8caf5-b2c7-44a8-b142-984e3b4c26d4" width= "500">


### Global Thresholding
<img src = "https://github.com/Adhithyaram29D/Thresholdingg/assets/119393540/f126e047-3483-45d5-91b9-f66391496658" width= "500"><br>
<img src = "https://github.com/Adhithyaram29D/Thresholdingg/assets/119393540/5848ac1a-8b59-478b-b5c5-01e8b8eb8bdc" width= "500"><br>
<img src = "https://github.com/Adhithyaram29D/Thresholdingg/assets/119393540/96b86668-e0c2-49db-91d5-d729bcc15c7b" width= "500"><br>
<img src = "https://github.com/Adhithyaram29D/Thresholdingg/assets/119393540/5544dbc9-94d7-4d0d-b7bd-b2902f987bef" width= "500"><br>
<img src = "https://github.com/Adhithyaram29D/Thresholdingg/assets/119393540/93d3054f-de8d-4396-a9cb-576cff2df203" width= "500">


### Adaptive Thresholding
<img src = "https://github.com/Adhithyaram29D/Thresholdingg/assets/119393540/ddc800ab-0522-41d0-ac84-4904e8c38d29" width= "500"><br>
<img src = "https://github.com/Adhithyaram29D/Thresholdingg/assets/119393540/37196d8f-9ebb-454c-806c-00c42da5fe1f" width= "500">


### Optimum Global Thesholding using Otsu's Method
<img src = "https://github.com/Adhithyaram29D/Thresholdingg/assets/119393540/2e725760-03d4-465b-a28e-34616a283309" width= "400">

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
