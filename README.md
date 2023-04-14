# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import cv2, matplotlib.py libraries and display the saved images using cv2.imshow().

### Step2:
Use cv2.calcHist(images, channels, mask, histSize, ranges[, hist[, accumulate]]) to find the histogram of the image.

### Step3:
Plot the image and its stem plots using the plt.show() and plt.stem() functions.

### Step4:
Equalize the grayscale image using the in-built function cv2.equalizeHist().

### Step5:
Print the original and equalized image using cv2.imshow() and end the program

## Program:
```
# Developed By: Naveenvetrivel
# Register Number: 212221230068
import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.

gray_image = cv2.imread("gray.png")
color_image =cv2.imread("color.png",-1)
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Colour Image",color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Display the histogram of gray scale image and any one channel histogram from color image

gray_image = cv2.imread("gray.png")
color_image = cv2.imread("color.png")
gray_hist = cv2.calcHist([gray_image],[0],None,[256],[0,256])
color_hist = cv2.calcHist([color_image],[0],None,[256],[0,256])
plt.figure()
plt.imshow(gray_image)
plt.show()
plt.title("Histogram")
plt.xlabel("Grayscale Value")
plt.ylabel("Pixel Count")
plt.stem(gray_hist)
plt.show()
plt.imshow(color_image)
plt.show()
plt.title("Histogram of Color Image - Green Channel")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(color_hist)
plt.show()

# Write the code to perform histogram equalization of the image. 

gray_image = cv2.imread("gray.png",0)
cv2.imshow("Gray Image",gray_image)
equ = cv2.equalizeHist(gray_image)
cv2.imshow("Equalized Image",equ)
cv2.waitKey(0)
cv2.destroyAllWindows
```
## Output:
### Input Grayscale Image and Color Image

![image](https://user-images.githubusercontent.com/94165322/232117227-f3ef7081-808e-4764-bf34-8a729d06dceb.png)

### Histogram of Grayscale Image and any channel of Color Image

![image](https://user-images.githubusercontent.com/94165322/232117278-a6477741-775d-4155-9757-b1e89fecb575.png)
![image](https://user-images.githubusercontent.com/94165322/232117339-bf8f2128-7890-4f9a-8564-3bf0e1cbd00c.png)

### Histogram Equalization of Grayscale Image

![image](https://user-images.githubusercontent.com/94165322/232117371-3903cd5c-2265-4c2e-b1cd-8cee27c37085.png)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
