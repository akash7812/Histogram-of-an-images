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
# Developed By: AKASH KUMAR M.
# Register Number: 212223230010

#import the libraries 
import cv2
from matplotlib import pyplot as plt

# Load the color image
image = cv2.imread(r"C:\Users\admin\Downloads\painting.jpeg")

# Check if the image was loaded successfully
if image is None:
    print("Error: Image not found or path is incorrect.")
else:
    # Convert the image to grayscale
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

    # Display the grayscale image
    plt.figure(figsize=(6, 6))
    plt.imshow(gray_image, cmap='gray')
    plt.title('Original Grayscale Image')
    plt.axis('off')
    plt.show()

# Calculate histogram for the original grayscale image
hist_original = cv2.calcHist([gray_image], [0], None, [256], [0, 256])

# Plot the histogram
plt.figure(figsize=(6, 4))
plt.plot(hist_original, color='black')
plt.title('Original Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.xlim([0, 256])
plt.grid(True)
plt.show()

# Apply histogram equalization
equalized_image = cv2.equalizeHist(gray_image)

# Display the equalized grayscale image
plt.figure(figsize=(6, 6))
plt.imshow(equalized_image, cmap='gray')  # corrected colormap spelling
plt.title('Equalized Image')
plt.axis('off')
plt.show()

# Calculate histogram for the equalized image
hist_equalized = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])

# Plot the histogram
plt.figure(figsize=(6, 4))
plt.plot(hist_equalized, color='black')
plt.title('Equalized Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.xlim([0, 256])
plt.grid(True)
plt.show()

```
## Output:
### Original gray scale image 
![Screenshot 2025-04-27 212047](https://github.com/user-attachments/assets/78e85d52-396b-43c4-b6ed-588a5c0218ba)



### Original Histogram 
![Screenshot 2025-04-27 212058](https://github.com/user-attachments/assets/1f4fac02-6145-4114-aeb6-97e83e13e58f)



### Equalization Image.
![Screenshot 2025-04-27 212106](https://github.com/user-attachments/assets/f3e0da14-7100-47fa-a52f-53f0cb51ee86)



### Equalized Histogram
![Screenshot 2025-04-27 212113](https://github.com/user-attachments/assets/145edd31-03be-48c8-911a-865fa5f980d1)



## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
