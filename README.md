# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

</br>
</br>
</br>

# PROGRAM:
## Developed By: H.Dhayanitha
## Resiter Number:212220230010

# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

# Read the Image and convert to grayscale
````
image=cv2.imread("army.webp",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("army.webp",0)
````

# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```
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

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>


## OUTPUT:

### Original Image and Grayscale Image

![d10](https://user-images.githubusercontent.com/75235032/169642578-ac1d112b-323b-4819-95ee-3e105e667358.jpg)

### Global Thresholding
![d11](https://user-images.githubusercontent.com/75235032/169642628-33db6549-ebf2-40f9-81cc-7ecef7aa0437.jpg)

![d12](https://user-images.githubusercontent.com/75235032/169642619-53616d91-4c71-48f1-a810-13a8a6c2557e.jpg)

![d13](https://user-images.githubusercontent.com/75235032/169642647-18c98991-a4a8-4f70-8c89-f2231a3b8d05.jpg)

![d14](https://user-images.githubusercontent.com/75235032/169642654-3b10a2ad-279f-4ad3-888e-f06c562595aa.jpg)

![d15](https://user-images.githubusercontent.com/75235032/169642658-520810c4-05c5-485e-a208-b3b880da40d1.jpg)

### Adaptive Thresholding

![d16](https://user-images.githubusercontent.com/75235032/169642681-3f8acf6b-622e-4a7c-8167-1ae431403c2f.jpg)

![d17](https://user-images.githubusercontent.com/75235032/169642686-f4a549eb-5198-40ae-82ee-6d056d0a97ec.jpg)

### Optimum Global Thesholding using Otsu's Method

![d18](https://user-images.githubusercontent.com/75235032/169642690-ec8b76c8-d214-48ed-b69f-6aeca883d161.jpg)

## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
