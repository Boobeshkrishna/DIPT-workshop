# Workshop--1-DIPT-Working-on-an-Image
## Aim:
1.Load two images of the same size.

2.Divide each image into four equal regions (quadrants) based on specific row and column coordinates.

3.Save the eight individual regions, labeling them as R1, R2, R3, R4 for the first image and R5, R6, R7, R8 for the second image.

4.Swap the regions as follows:R1 with R8,R2 with R7,R3 with R6,R4 with R5

5.Resize the final images to dimensions specified by the last four digits of your registration number, ensuring the number is even.


## Program:
Developed By: BOOBESH PM

Register Number: 212222233001
```
import cv2
# Read the image
image1 = cv2.imread('RAJ.JPEG')
image2= cv2.imread('LOKI.JPEG')
image1.shape
# Resize both images to the desired size (160,200)
new_size=(160,200) #(width,height)
image1_resized=cv2.resize(image1,new_size)
image2_resized=cv2.resize(image2,new_size)
image1_resized.shape
image2_resized.shape
height=200
width=160
# Define row and column coordinates for splitting
row_mid=100
col_mid=80
# Split the image into 4 regions using row and column coordinates
R1= image2_resized[0:row_mid,0:col_mid]
R2= image2_resized[0:row_mid,0:width]
R3= image2_resized[row_mid:height,0:col_mid]
R4= image2_resized[row_mid:height,col_mid:width]
# Split the image into 4 regions using row and column coordinates
R5= image1_resized[0:row_mid,0:col_mid]
R6= image1_resized[0:row_mid,0:width]
R7= image1_resized[row_mid:height,0:col_mid]
R8= image1_resized[row_mid:height,col_mid:width]
# Display the regions (optional)
cv2.imshow('Top-Left Region', R1)
cv2.imshow('Top-Right Region', R2)
cv2.imshow('Bottom-Left Region', R3)
cv2.imshow('Bottom-Right Region', R4)
cv2.waitKey(0)
cv2.destroyAllWindows()
# Display the regions (optional)
cv2.imshow('Top-Left Region', R5)
cv2.imshow('Top-Right Region', R6)
cv2.imshow('Bottom-Left Region', R7)
cv2.imshow('Bottom-Right Region', R8)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imwrite('R1.jpg',R1)
cv2.imwrite('R2.jpg',R2)
cv2.imwrite('R3.jpg',R3)
cv2.imwrite('R4.jpg',R4)
cv2.imwrite('R5.jpg',R5)
cv2.imwrite('R6.jpg',R6)
cv2.imwrite('R7.jpg',R7)
cv2.imwrite('R8.jpg',R8)
image1_resized[0:row_mid,0:col_mid] = R1
image2_resized[row_mid:height,col_mid:width] = R8
cv2.imshow('Image Window', image1_resized)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('Image Window', image2_resized)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imwrite('image1_resized.jpg',image1_resized)
cv2.imwrite('image2_resized.jpg',image2_resized)
```
## input images
![RAJ](https://github.com/user-attachments/assets/8eba0590-ef66-4259-8ea0-9304aa737fd4)
![LOKI](https://github.com/user-attachments/assets/c91f4a5a-599e-48e8-8804-57e765db89e6)

## output images
![image](https://github.com/user-attachments/assets/83d2119f-1c76-467f-808a-6e42f26d2dea)
![image](https://github.com/user-attachments/assets/7ec35867-2e08-44fa-856b-2e3be8705423)


