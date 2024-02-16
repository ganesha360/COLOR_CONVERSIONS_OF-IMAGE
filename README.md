# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: GANESH R
### Register Number: 212222240029


## Output:

### i) Read and display the image
```python
import cv2
import matplotlib.pyplot as plt

img=cv2.imread("Cheetah.jpeg",1)
cv2.imshow("display window",img)
cv2.waitKey(0)
cv2.destroyAllWindows()
print(img.shape)
```
## Output:
![display window](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/b82c5763-49d4-4120-aa2f-d04e2b07ec15)

### ii)Write the image
```python
import cv2
img1=cv2.imread("cheetah.jpeg",1)
cv2.imwrite('greyscale.jpeg',img1)
```
## Output:
![shape of the image](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/b47c23ed-d767-497a-9585-930356d9fc1c)

### iii)Shape of the Image
```python
import cv2
img1=cv2.imread("cheetah.jpeg",0)
cv2.imshow("display window",img1)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imwrite('greyscale.jpeg',img1)
print(img1.shape)
```
## Output:
![write the image](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/2c9cf46e-8177-4dd3-90b4-dde3ad585f62)

### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('cheetah.jpeg',1)
#image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                    random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![part image](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/401cf455-b3a6-4355-b151-c72fa9f1b716)

### v)Cut and paste portion of image
```python
import cv2

img2 = cv2.imread("cheetah.jpeg")

x = 0
y = 200
x1 = 160
y1 = 450
x2 = 0
y2 = 0

cropimg = img2[x:x1+x2, y:y1+y2]

cv2.imshow("Original Image", img2)
cv2.imshow("Cropped Image", cropimg)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:

![original image](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/3819e845-ac6a-4776-9a8c-6d97bdf46872)

![crop image](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/884982c4-192c-447f-ba77-909e75eff674)


### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('cheetah.jpeg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![original image](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/1fa54bca-1381-48ad-b838-1758709bc51b)  ![bgr2hsv](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/31bf4c00-70a5-4797-95a2-456e8cb41145)


![bgr2gray](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/1f10e77a-8f4e-4764-96d2-7c5a9b29afb1)  ![rgb2gray](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/faa44186-b912-4e65-8e0c-9eb56925c4a8)



### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('cheetah.jpeg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![original hsv](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/e0c851a6-e63a-4cbf-ac00-ec1d54d6e37b) ![2hsv2bgr](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/36108a58-9351-4551-a905-404d3032ad39)
![hsv2rgb](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/8b620f6e-2837-4f46-87b1-e2ff7c027699)


### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('cheetah.jpeg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![original rgb](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/f87b4ad4-3416-4115-b742-711e2780826d) ![bgr-2-ycr](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/6e9d7bd3-293f-44f0-b31b-6e484cb63314)

![rgb-2-ycr](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/08a28968-d578-4c8e-8c1d-8a52d06d766f)


### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('cheetah.jpeg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![Merged rgb](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/777333aa-ad01-430d-af88-fd48ed1fe123) ![r channel](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/3158f3b5-56fa-42bd-b2ea-a3d159440e93)
![g channel](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/5ca34263-e991-4faa-8ef2-a082e548a865) ![b channel](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/e5895a57-040c-459a-87c7-8cc5366465fd)



### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("cheetah.jpeg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![merged](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/7cde2db5-ad32-4b1c-9c6e-5fb0a258bcb8) ![hue](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/f636915a-3fe2-4bc0-b0ea-818649654df3)
![saturation](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/3b5ec618-5597-44dc-a044-095cacda99b9) ![value](https://github.com/ganesha360/COLOR_CONVERSIONS_OF-IMAGE/assets/120884552/09c2e261-5d05-493c-9d6d-2b442ae972b7)





## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







