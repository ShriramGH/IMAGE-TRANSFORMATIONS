# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
#### Import numpy module as np and pandas as pd.
<br>

### Step 2:
#### Assign the values to variables in the program.
<br>

### Step 3:
#### Get the values from the user appropriately.
<br>

### Step 4:
#### Continue the program by implementing the codes of required topics.
<br>

### Step 5:
#### Thus the program is executed in google colab.
<br>

## Program:

### Developed By : Shriram S

### Register Number : 212222240098

#### Installing OpenCV , importing necessary libraries and displaying images  

```py
# Install OpenCV library
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images 
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

```

#### (i) Image Translation
```py
# Load an image from URL or file path
image_url = 'Ex-4_1.jpeg'  
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)
```

#### (ii) Image Scaling
```py

# Load an image from URL or file path
image_url = 'Ex-4_2.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis


# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("Original Image:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)

```




#### (iii) Image shearing
```py
# Load an image from URL or file path
image_url = 'Ex-4_3.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)

```



#### (iv) Image Reflection

```py
# Load an image from URL or file path
image_url = 'Ex-4_4.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

```

##### (a) → Reflecting Horizontally

```py
# Display original and reflected images

show_image(image)
print("↑ Original Image")
show_image(reflected_image_horizontal)
print("↑ Reflected Horizontally")
```

##### (b) → Reflected Vertically

```py
show_image(image)
print("↑ Original Image")
show_image(reflected_image_vertical)
print("↑ Reflected Vertically")

```

##### (c) → Reflecting Horizontally & Vertically
```py

show_image(image)
print("↑ Original Image")
show_image(reflected_image_both)
print("↑ Reflected Both")

```

### (v) Image Rotation

```py
# Load an image from URL or file path
image_url = 'Ex-4_5.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)

```



### (vi) Image Cropping

```py
# Load an image from URL or file path
image_url = 'Ex-4_6.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)

```




## Output:

### (i) Image Translation
<br>
<br>

![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/d6f7ba1d-df2a-4f6f-affd-894676214c19)![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/24f8cbad-fe91-49fc-b944-596d263f529c)


<br>
<br>

### (ii) Image Scaling
<br>
<br>

![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/5886ceb6-b6e4-4b01-8882-2c64b6963bb6)![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/5c3204e2-7a43-4711-b71a-031dd1cf20ee)


<br>
<br>


### (iii) Image shearing
<br>
<br>

![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/e94bed67-3eba-4529-89e0-e59a48a00171) ![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/e003f526-5ec2-40a1-9303-80871d260e43)


<br>
<br>


### (iv) Image Reflection


#### Reflecting Horizontally

![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/d89502e7-eefa-4358-b7ee-5fa870950318)![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/18eb1acf-ebb6-4730-bffe-3af0821dbff6)




#### Reflecting Vertically

![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/fa9d3751-ad8c-4c2e-b919-7968bb99fa41) ![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/3ace7c1e-cefe-4332-bb47-503e0746dd98)


#### Reflecting Horizontally & Vertically

![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/3b5a44e4-4406-4a1f-8cdf-9a42d2ab6c3e)![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/33655dfd-3980-4a74-bfd2-2397921782e4)


<br>
<br>


### (v) Image Rotation
<br>
<br>

![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/37653f1d-f89c-44e8-ae57-65331d853d56) ![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/9cad5e73-8b26-4a46-b44b-569375e2cb5c)


<br>
<br>



### (vi) Image Cropping
<br>
<br>

![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/8fb2e562-a755-4b9a-ad0c-c4a57f9edbe9)![image](https://github.com/ShriramGH/IMAGE-TRANSFORMATIONS/assets/117991122/93611d31-3416-4b00-b4b9-2b6543a5951d)


<br>
<br>




## Result: 

### Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
