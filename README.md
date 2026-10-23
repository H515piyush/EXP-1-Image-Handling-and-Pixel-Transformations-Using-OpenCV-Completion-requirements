# Name:Piyush Kumar
# Reg No:212223220075
# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** [Piyush kumar] 
- **Register Number:** [212223220075]

  ### Ex. No. 01
 ```
#Load an image from your local directory and display it.
import cv2
import matplotlib.pyplot as plt

# Read the image using OpenCV
img = cv2.imread('pk.jpeg', cv2.IMREAD_COLOR)

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()

# Load the image
image = cv2.imread('pk.jpeg')

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (0, 0, 255), 2) # cv2.line(image, start_point, end_point, color, thickness)

plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('pk.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

circle_img = cv2.circle(img_rgb,(400,300),150,(0,255,0),10) # cv2.circle(image, center, radius, color, thickness)

plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')
plt.show()

Draw a rectangle around  the whole image
# Load the image
image = cv2.imread('pk.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape

# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 255, 0), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('pk.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Add text to the image
text_img = cv2.putText(img_rgb, "Piyush", (150, 100), cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 255, 255), 1000)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)

plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('pk.jpeg')

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")

# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")

# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")

# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")

# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")

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
image = cv2.imread('pk.jpeg')

image.shape

# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)

# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

resized_image_rgb.shape

# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('pk.jpeg')

image.shape

# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349

# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('pk.jpeg')

# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)

# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

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

```






## Output:
<img width="358" height="517" alt="Screenshot 2026-10-23 142505" src="https://github.com/user-attachments/assets/92a52154-967a-419e-b2c0-8e0e2e1b2746" />
<img width="363" height="502" alt="Screenshot 2026-10-23 142513" src="https://github.com/user-attachments/assets/dde66eec-a0f7-4b12-a7eb-2fb8a85b2d71" />
<img width="382" height="508" alt="Screenshot 2026-10-23 142519" src="https://github.com/user-attachments/assets/537df9c3-0a93-4d28-8740-3a6d77456abc" />
<img width="353" height="492" alt="Screenshot 2026-10-23 142526" src="https://github.com/user-attachments/assets/aad4601c-cbee-46fa-858f-eaa6321b9849" />
<img width="351" height="500" alt="Screenshot 2026-10-23 142535" src="https://github.com/user-attachments/assets/9515e691-cf25-4b0a-81bd-45e2cffb9feb" />
<img width="366" height="492" alt="Screenshot 2026-10-23 142544" src="https://github.com/user-attachments/assets/62c9f316-0ff2-4d9b-b881-3b3c80d7d2d6" />
<img width="387" height="515" alt="Screenshot 2026-10-23 142557" src="https://github.com/user-attachments/assets/81d1b623-d336-4390-8824-8e0a3d37f803" />
<img width="377" height="506" alt="Screenshot 2026-10-23 142604" src="https://github.com/user-attachments/assets/82ad01c4-f90d-40d5-9e2e-0e9700d087ad" />
<img width="370" height="497" alt="Screenshot 2026-10-23 142612" src="https://github.com/user-attachments/assets/16dd605e-6aaa-43d7-bead-5f2f2231ac5c" />
<img width="386" height="510" alt="Screenshot 2026-10-23 142618" src="https://github.com/user-attachments/assets/39c6f957-8918-48c9-a6e3-82b34f96aba2" />
<img width="395" height="512" alt="Screenshot 2026-10-23 142625" src="https://github.com/user-attachments/assets/c90c74fe-8d16-45a2-94fa-41e0715dc5c5" />
<img width="645" height="507" alt="Screenshot 2026-10-23 142632" src="https://github.com/user-attachments/assets/63a4b46f-2380-49a8-af8d-5a73d782b396" />
<img width="527" height="520" alt="Screenshot 2026-10-23 142638" src="https://github.com/user-attachments/assets/8a3ca1c4-dff6-4ca3-89c8-7518845ec286" />
<img width="356" height="503" alt="Screenshot 2026-10-23 142644" src="https://github.com/user-attachments/assets/cfc091cc-ab58-4676-bf30-4733b4746706" />
<img width="367" height="506" alt="Screenshot 2026-10-23 142651" src="https://github.com/user-attachments/assets/2dd0c168-2791-4a5d-93ca-c43b992ceccc" />






## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
