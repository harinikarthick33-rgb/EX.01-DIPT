# EXP-1 Image Handling and Pixel Transformations Using OpenCV 
# AIM:
Write a Python program using OpenCV that performs the following tasks:

Read and Display an Image. Adjust the brightness of an image. Modify the image contrast. Generate a third image using bitwise operations.

# Software Required:
Anaconda - Python 3.7 Jupyter Notebook (for interactive development and execution)

# Algorithm:
Step 1: Load an image from your local directory and display it.

Step 2: Create a matrix of ones (with data type float64) to adjust brightness.

Step 3: Create brighter and darker images by adding and subtracting the matrix from the original image. Display the original, brighter, and darker images.

Step 4: Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix). Display the original, lower contrast, and higher contrast images.

Step 5: Split the image (boy.jpg) into B, G, R components and display the channels

# Program Developed By:
# Name: Harini V K
# Register Number: 212225220036

# Program:
```
# Import libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread("Harini.new.jpeg",cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
Display the image using matplotlib imshow().
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
# Load the image
image = cv2.imread('Harini.new.jpeg') 
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(1000, 1500, 3)
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread(''Harini.new.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(1000, 1500, 3)
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('Harini.new.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("HARINI")
plt.axis('off')  
plt.show()
 Load the image
image = cv2.imread('Harini.new.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
#Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
(-0.5, 1499.5, 999.5, -0.5)
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
(-0.5, 1499.5, 999.5, -0.5)
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
(-0.5, 1499.5, 999.5, -0.5)
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
(-0.5, 1499.5, 999.5, -0.5)
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
(-0.5, 1499.5, 999.5, -0.5)
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('Harini.new.jpeg') 
image.shape
(1000, 1500, 3)
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
(300, 384, 3)
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('Harini.new.jpeg') 
image.shape
(1000, 1500, 3)
# Crop a 300x300 region starting from (50, 50)
roi = image[250:350, 200:350]  # Rows: 50-349, Columns: 50-349
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('Harini.new.jpeg') 
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
(-0.5, 1499.5, 999.5, -0.5)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
(-0.5, 1499.5, 999.5, -0.5)
```
# Output:
<img width="615" height="450" alt="Screenshot 2026-11-12 161800" src="https://github.com/user-attachments/assets/610d4243-3396-4e12-81a1-5374df4f6555" />
<img width="627" height="437" alt="image" src="https://github.com/user-attachments/assets/ee399f33-78eb-4316-8dcd-c3c196d8ee7a" />
<img width="617" height="441" alt="image" src="https://github.com/user-attachments/assets/e4e8bedc-77b1-4e69-be5d-dd2145613376" />
<img width="620" height="432" alt="image" src="https://github.com/user-attachments/assets/381ac490-2b57-4b7b-a6d0-48e9c48cda6c" />
<img width="608" height="456" alt="image" src="https://github.com/user-attachments/assets/d63fd072-0f39-42ba-a2a2-e900c5c7f14f" />
<img width="613" height="442" alt="image" src="https://github.com/user-attachments/assets/0ec18334-bb4d-4f50-b65a-81d95e26d32c" />
<img width="617" height="441" alt="image" src="https://github.com/user-attachments/assets/1bd4ee14-85bb-4b2f-9ece-60c9c3149538" />
<img width="611" height="442" alt="image" src="https://github.com/user-attachments/assets/bbf75b7d-c9a6-4f59-ab4f-f2d6284b282c" />
<img width="616" height="440" alt="image" src="https://github.com/user-attachments/assets/f7afd37c-3761-43d4-ad8a-b6682d345c21" />
<img width="612" height="440" alt="image" src="https://github.com/user-attachments/assets/6df2521b-8358-468b-9c5c-afcb5bca7ee7" />
<img width="620" height="437" alt="image" src="https://github.com/user-attachments/assets/3874695d-82c2-4da2-a18f-e20b81929bc6" />
<img width="581" height="490" alt="image" src="https://github.com/user-attachments/assets/7029f18f-33c1-4563-9ded-731455328be9" />
<img width="613" height="437" alt="image" src="https://github.com/user-attachments/assets/d1fab2c6-1160-4b54-8123-1608494d38ac" />
<img width="617" height="440" alt="image" src="https://github.com/user-attachments/assets/59a05e72-56d8-4d2e-aef9-584201c6b607" />

# Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.





