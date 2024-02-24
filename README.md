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
### Developed By:PRAVEEN.V
### Register Number:212222233004 


## Output:

### i) Read and display the image
```
import cv2
img=cv2.imread('pikachu.jpg',1)
cv2.imshow('praveen image',img)
cv2.waitKey(0)
```
output:![Screenshot 2024-02-24 210835](https://github.com/praveenv23013808/COLOR_CONVERSIONS_OF-IMAGE/assets/145824728/14cf9185-9a62-4536-99f2-0d8a0191a148)

### ii)Write the image
```
import cv2
g_image=cv2.imread('pikachu.jpg',0)
cv2.imwrite('pikachu.jpg',g_image)
```
output:![Screenshot 2024-02-24 211618](https://github.com/praveenv23013808/COLOR_CONVERSIONS_OF-IMAGE/assets/145824728/89f99866-f903-4129-ac49-00bee50f1338)

### iii)Shape of the Image
```
import cv2
image=cv2.imread('pikachu.jpg',1)
print(image.shape)
```
output:![Screenshot 2024-02-24 211939](https://github.com/praveenv23013808/COLOR_CONVERSIONS_OF-IMAGE/assets/145824728/0683d5d7-90f8-4aad-8cda-b446b7950e20)

### iv)Access rows and columns
```
 import random
    import cv2
    image=cv2.imread('pikachu.jpg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
output:![Screenshot 2024-02-24 212329](https://github.com/praveenv23013808/COLOR_CONVERSIONS_OF-IMAGE/assets/145824728/b3658698-6eb6-4989-ae84-feed17f76307)

### v)Cut and paste portion of image
```
  import cv2
   image=cv2.imread('pikachu.jpg',1)
   image=cv2.resize(image,(400,400))
   tag =image[150:200,110:160]
   image[110:160,150:200] = tag
   cv2.imshow('partimage1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
output:![Screenshot 2024-02-24 212731](https://github.com/praveenv23013808/COLOR_CONVERSIONS_OF-IMAGE/assets/145824728/c989960b-f109-41d2-a3ce-e8849854210e)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('pikachu.jpg',1)
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
output:![Screenshot 2024-02-24 213033](https://github.com/praveenv23013808/COLOR_CONVERSIONS_OF-IMAGE/assets/145824728/dc00fa06-585d-4640-a6e0-f0cd2b85dd1c)

### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('pikachu.jpg')
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
output:![Screenshot 2024-02-24 213315](https://github.com/praveenv23013808/COLOR_CONVERSIONS_OF-IMAGE/assets/145824728/d1428185-1139-42e7-837a-51519608f2a5)

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('pikachu.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
output:![Screenshot 2024-02-24 214104](https://github.com/praveenv23013808/COLOR_CONVERSIONS_OF-IMAGE/assets/145824728/7d5c810a-a248-41dc-91ec-f94746272cde)

### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('pikachu.jpg',1)
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
output:![Screenshot 2024-02-24 214429](https://github.com/praveenv23013808/COLOR_CONVERSIONS_OF-IMAGE/assets/145824728/6fbadc97-6b53-440c-92fe-4ec1f2683344)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("pikachu.jpg",1)
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
output:![Screenshot 2024-02-24 214637](https://github.com/praveenv23013808/COLOR_CONVERSIONS_OF-IMAGE/assets/145824728/cd11bb72-59f8-4849-baf2-ad088bbef949)
## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







