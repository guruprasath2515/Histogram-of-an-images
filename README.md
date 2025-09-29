# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().


### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: GURU PRASATH R
# Register Number: 212223040053
import matplotlib.pyplot as plt 
import cv2

grayscale_image = cv2.imread("snoopy.jpg", cv2.IMREAD_GRAYSCALE)
color_img = cv2.imread("snoopy.jpg")

gray_hist = cv2.calcHist([grayscale_image], [0], None, [256], [0, 256])
hist_b = cv2.calcHist([color_img], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_img], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_img], [2], None, [256], [0, 256])

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.imshow(grayscale_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(colourscale_image, cv2.COLOR_BGR2RGB))
plt.title('Color Image')
plt.axis('off')

plt.show()

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.plot(gray_hist, color='black')
plt.title("Grayscale Image Histogram (Normalized)")
plt.xlabel("Pixel Intensity")
plt.ylabel("Normalized Pixel Count")

plt.subplot(1, 2, 2)
plt.plot(hist_r, color='red')
plt.plot(hist_b, color='blue')
plt.plot(hist_g, color='green')
plt.title("Color Image Histogram (Normalized)")
plt.xlabel("Pixel Intensity")
plt.ylabel("Normalized Pixel Count")

plt.show()

equalized_grey_img = cv2.equalizeHist(grayscale_image)
plt.title("Equalized Hist of Gray Image")
plt.hist(equalized_grey_img.ravel(),bins=256,color='black',alpha=0.6)
plt.show()
```
## Output:
### Input Grayscale Image and Color Image

![image](https://github.com/user-attachments/assets/71560cc5-8ae1-4f99-844d-9cfd0546ef41)

![image](https://github.com/user-attachments/assets/1e67c2bd-97a8-4c26-a547-a74c304780c8)

### Histogram of Grayscale Image and any channel of Color Image

![image](https://github.com/user-attachments/assets/ff5babd3-0fba-4f3a-9bfb-76de126668f0)

![image](https://github.com/user-attachments/assets/a3c40c0b-ff9b-4254-810f-82b2acee016b)

### Histogram Equalization of Grayscale Image.

![image](https://github.com/user-attachments/assets/bc0cf354-b822-4bcb-b5d8-a4348b25d79b)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
