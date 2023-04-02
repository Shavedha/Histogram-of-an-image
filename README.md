# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required
Anaconda - Python 3.7

## Algorithm
### Step1:
Import cv2, matplotlib.py libraries and display the saved images using cv2.imshow().

### Step2:
Use cv2.calcHist(images, channels, mask, histSize, ranges[, hist[, accumulate]]) to find the histogram of the image.

### Step3:
Plot the image and its stem plots using the plt.show() and plt.stem() functions.

### Step4:
Equalize the grayscale image using the in-built function cv2.equalizeHist().

### Step5:
Print the original and equalized image using cv2.imshow() and end the program.

## Program
```
# Developed By: Y SHAVEDHA
# Register Number: 212221230095
```
```
import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.
color_image=cv2.imread("rcolorimg2.jpg")
gray_image=cv2.imread("gimg.jpg")
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Color_image",color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Display the histogram of gray scale image and any one channel histogram from color image
hist_g = cv2.calcHist([gray_image],[0],None,[256],[0,256])
plt.figure()
plt.imshow(gray_image)
plt.show()
plt.title("Histogram")
plt.xlabel("Grayscale Value")
plt.ylabel("Pixel Count")
plt.stem(hist_g)
plt.show()

hist_c = cv2.calcHist([color_image],[2],None,[256],[0,256])
plt.figure()
plt.imshow(color_image)
plt.show()
plt.title("Histogram of Color Image - Red Channel")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(hist_c)
plt.show()


# Write the code to perform histogram equalization of the image. 
gray_image = cv2.imread("gimg.jpg",0)
cv2.imshow("Gray Image",gray_image)
equ = cv2.equalizeHist(gray_image)
cv2.imshow("Equalized Image",equ)
cv2.waitKey(0)
cv2.destroyAllWindows

```
## Output
### Input Grayscale Image and Color Image
<img width="803" alt="op1" src="https://user-images.githubusercontent.com/93427376/229366038-1373f55b-1ba4-4dfd-afc6-2e500df53ee7.png">

### Histogram of Grayscale Image and any channel of Color Image
### GRAY SCALE IMAGE
<img width="368" alt="op2" src="https://user-images.githubusercontent.com/93427376/229366050-c5cd0022-df43-4a36-be6c-d721a805ba89.png">

### RED CHANNEL OF COLOR IMAGE
<img width="380" alt="op3" src="https://user-images.githubusercontent.com/93427376/229366058-34b1bdd9-0c84-40ee-8daf-919ee1c1b0ee.png">


### Histogram Equalization of Grayscale Image
<img width="803" alt="op4" src="https://user-images.githubusercontent.com/93427376/229366069-6c5ad11e-b810-4d20-b14d-7f221f6c329c.png">


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
