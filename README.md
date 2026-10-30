
## Workshop -1 Adding Sunglasses to Your Passport Photo Using OpenCV
### Name: Divya Dharshini S
### Reg.No: 2122242420039
# Sturdy-Octo-Disco-Adding-Sunglasses-for-a-Cool-New-Look

Sturdy Octo Disco is a fun project that adds sunglasses to photos using image processing.

Welcome to Sturdy Octo Disco, a fun and creative project designed to overlay sunglasses on individual passport photos! This repository demonstrates how to use image processing techniques to create a playful transformation, making ordinary photos look extraordinary. Whether you're a beginner exploring computer vision or just looking for a quirky project to try, this is for you!

## Features:
- Detects the face in an image.
- Places a stylish sunglass overlay perfectly on the face.
- Works seamlessly with individual passport-size photos.
- Customizable for different sunglasses styles or photo types.

## Technologies Used:
- Python
- OpenCV for image processing
- Numpy for array manipulations

## How to Use:
1. Clone this repository.
2. Add your passport-sized photo to the `images` folder.
3. Run the script to see your "cool" transformation!

## Applications:
- Learning basic image processing techniques.
- Adding flair to your photos for fun.
- Practicing computer vision workflows.

Feel free to fork, contribute, or customize this project for your creative needs!

## Program
```
# Import libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Load the Face Image
faceImage = cv2.imread('08.JPG')
plt.imshow(faceImage[:,:,::-1]);plt.title("Face")
faceImage.shape
#resized_faceImage.shape
faceImage.shape
# Load the Sunglass image with Alpha channel
# (http://pluspng.com/sunglass-png-1104.html)
glassPNG = cv2.imread('sunglass.png',-1)
plt.imshow(glassPNG[:,:,::-1]);plt.title("glassPNG")
# Resize the image to fit over the eye region
glassPNG = cv2.resize(glassPNG,(450,170))
print("image Dimension ={}".format(glassPNG.shape))
# Separate the Color and alpha channels
glassBGR = glassPNG[:,:,0:3]
glassMask1 = glassPNG[:,:,3]
# Display the images for clarity
plt.figure(figsize=[15,15])
plt.subplot(121);plt.imshow(glassBGR[:,:,::-1]);plt.title('Sunglass Color channels');
plt.subplot(122);plt.imshow(glassMask1,cmap='gray');plt.title('Sunglass Alpha channel');
# Make a copy
#faceWithGlassesNaive = resized_faceImage.copy()
faceWithGlassesNaive = faceImage.copy()

# Replace the eye region with the sunglass image
faceWithGlassesNaive[340:510,327:777]=glassBGR

plt.imshow(faceWithGlassesNaive[...,::-1])
# Replace the eye ROI with the output from the previous section
faceWithGlassesArithmetic[340:510,327:777]=eyeRoiFinal

# Display the final result
plt.figure(figsize=[20,20]);
plt.subplot(121);plt.imshow(faceImage[:,:,::-1]); plt.title("Original Image");
plt.subplot(122);plt.imshow(faceWithGlassesArithmetic[:,:,::-1]);plt.title("With Sunglasses");
```
## Output

<img width="568" height="591" alt="image" src="https://github.com/user-attachments/assets/0f067811-4317-4e28-9c6c-940fe8147975" />

<img width="732" height="405" alt="image" src="https://github.com/user-attachments/assets/89014856-4ba7-46d1-8208-0ef775a53ba2" />

<img width="887" height="223" alt="image" src="https://github.com/user-attachments/assets/6499320e-0423-4625-af6c-da174ed08c52" />

<img width="615" height="555" alt="image" src="https://github.com/user-attachments/assets/0de4c3e0-2b47-4c72-bc5d-9801cee91574" />

<img width="923" height="195" alt="image" src="https://github.com/user-attachments/assets/2b838565-cef2-43d2-aab0-6d6f6fa32409" />

<img width="896" height="558" alt="image" src="https://github.com/user-attachments/assets/2befd23d-d960-42cc-9bb2-cd242c2b2c9d" />

## Result:

The program loads the face image and sunglasses image, resizes the sunglasses to fit the eye region, and overlays them onto the face using OpenCV. Finally, it displays the original face image and the modified image with sunglasses.
