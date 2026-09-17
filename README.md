# Image-Handling-and-Pixel-Transformations-Using-OpenCV

## Program Developed By:
## Name: VIJAY K

## Register Number: 212224240182

# AIM:
Write a Python program using OpenCV that performs the following tasks:

Read and Display an Image.
Adjust the brightness of an image.
Modify the image contrast.
Generate a third image using bitwise operations.
# Software Required:
Anaconda - Python 3.7
Jupyter Notebook (for interactive development and execution)
# Algorithm:
Step 1:
Load an image from your local directory and display it.

Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.
Display the original, brighter, and darker images.

Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).
Display the original, lower contrast, and higher contrast images.

Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels


## Ex. No. 01
```
import cv2
import matplotlib.pyplot as plt
```
# Read the image using OpenCV
```
img = cv2.imread('model img.jpg', cv2.IMREAD_COLOR)
```
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
# Display the image using Matplotlib
```
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/ec3db73c-14b4-4449-9107-8ce09d8baacd" />




# Load the image
```
image = cv2.imread('model img.jpg')
``` 
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(554, 554, 3)
```
# Draw a line from top-left to bottom-right
```
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('on')  
plt.show()
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/b65fb961-3199-4430-b781-ec2e7ec2a314" />



# Load the image
```
image = cv2.imread('model img.jpg') 
```
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(554, 554, 3)
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/07d2ac35-ac45-45cc-afbc-fa5321064bcc" />



# Load the image
```
image = cv2.imread('model img.jpg') 
```
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
(554, 554, 3)
```
# Draw a rectangle around the Whole image
```
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/315164f8-24ce-4d08-806f-5aa9fdfed7fe" />




# Load the image
```
image = cv2.imread('model img.jpg') 
```
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
# Add text to the image
```
text_img = cv2.putText(img_rgb, "Sanjaykumar", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/d1d02959-d8f5-4e0f-8b23-debf96fc0034" />



# Load the image
```
image = cv2.imread('model img.jpg') 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
# Original RGB Image
```
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
(np.float64(-0.5), np.float64(553.5), np.float64(553.5), np.float64(-0.5))
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/971285da-3be1-4ac3-8c01-cf83dfd7dcd2" />



# Convert RGB to HSV
```
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
```
# HSV Image
```
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
(np.float64(-0.5), np.float64(553.5), np.float64(553.5), np.float64(-0.5))
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/8b75f808-d088-4735-9193-670f5690d356" />



# Convert RGB to GRAY
```
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
```
# Grayscale Image
```
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
(np.float64(-0.5), np.float64(553.5), np.float64(553.5), np.float64(-0.5))
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/aee89214-9ea6-43c0-b362-79248e0b6aa8" />



# Convert RGB to YCrCb
```
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
```
# YCrCb Image
```
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
(np.float64(-0.5), np.float64(553.5), np.float64(553.5), np.float64(-0.5))
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/6fda9746-e7f7-43e4-b9a2-7b6da8c78eaa" />



# Convert HSV back to RGB
```
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
(np.float64(-0.5), np.float64(553.5), np.float64(553.5), np.float64(-0.5))
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/f4552743-37e9-4fa7-b16a-06a18fd5d94a" />



# Modify a block of pixels (300x300) to white, starting from (200, 200)
```
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
```
# Convert BGR to RGB for displaying with Matplotlib
```
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
# Display the modified image
```
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/60ce47bb-818a-4678-804a-37e38e3bf08a" />



# Load the image
```
image = cv2.imread('images.jpg') 
image.shape
(554, 554, 3)
```
# Resize the image to half its size
```
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
```
# Convert BGR to RGB for displaying with Matplotlib
```
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
(300, 384, 3)
```
# Display the resized image
```
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
<img width="493" height="410" alt="download" src="https://github.com/user-attachments/assets/404cccfd-e00a-407c-9c1f-c902a76f0f96" />



# Load the image
```
image = cv2.imread('model img.jpg') 
image.shape
(554, 554, 3)
```
# Crop a 300x300 region starting from (50, 50)
```
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
```
# Convert BGR to RGB for displaying with Matplotlib
```
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
```
# Display the cropped region (ROI)
```
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/345c31ed-0018-4406-bae8-a61d86ed4a54" />



# Load the image
```
image = cv2.imread('model img.jpg')
```
# Flip the image horizontally (left-right)
```
flipped_horizontally = cv2.flip(image, 1)
```
# Convert BGR to RGB for displaying with Matplotlib
```
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
```
# Horizontal flip
```
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
(np.float64(-0.5), np.float64(553.5), np.float64(553.5), np.float64(-0.5))
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/a9358bd4-44f6-443d-bdd8-b6027b7df386" />



# Flip the image vertically (up-down)
```
flipped_vertically = cv2.flip(image, 0)
```
# Convert BGR to RGB for displaying with Matplotlib
```
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
```
# Vertical flip
```
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
(np.float64(-0.5), np.float64(553.5), np.float64(553.5), np.float64(-0.5))
```
<img width="516" height="371" alt="download" src="https://github.com/user-attachments/assets/4128e08b-bd4d-44ca-87ed-1f6e3bd68059" />



# Output:
i) Read and Display an Image.
ii) Adjust Image Brightness.
iii) Modify Image Contrast.
iv) Generate Third Image Using Bitwise Operations.
# Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
