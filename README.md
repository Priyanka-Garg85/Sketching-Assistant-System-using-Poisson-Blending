## Sketching-Assistant-System-using-Poisson-Blending

A web application to generate new and custom faces/sketches using the concept of Poisson Blending involves concept of feature extraction, image manipulation, array manipulation, clustering and deep learning.

This project aims to encapsulate our skills obtained during our course and our specializations. Sketch Assistant System is a Python tool that simplifies sketch creation. It offers users an easy and expressive way to create unique sketches effortlessly using prompts like options.

It begins by assuming that common facial features can be extracted and classified using techniques like facial landmark identification and bounding box determination. These features are then organized using the K-means algorithm to identify common patterns and variations in facial traits.

Once facial features are clustered, the project utilizes Poisson Blending to generate sketches based on user preferences. This allows users to quickly generate sketches for artistic or forensic purposes, providing them with interactive tools to sculpt faces according to their vision and imagination.



# Requirements

> numpy:  coordinates function to convert and access arrays. Used for mathematical methods such as finding mean, min-max function, floor, ceiling functions, sqrt functions, random choice function, concatenate function,  reading npz file etc.

> pandas:  reading csv file.

> scipy:  used during Poisson Blending for methods like laplacian() and linalg() which are used for gradient solving and linear least square solving.

> matplotlib: used for subplot generation of faces in matrices, making of rectangular boxes during feature extraction (use of matplotlib.patches) and graph generation.

> cv2:  to access, normalise, resize the images.

> skimage:  to resize cropped images.

> sklearn:  used to perform K-Means clustering.

> os:  to access directory

# Algorithms Used:

> K-Means Clustering:  used to collect similar features together.

> Poisson Blending:  involves use of masks to create create a new image by combining an input image with a target image.


# Methodology Flowchart
<img width="200" height="400" alt="image" src="https://github.com/user-attachments/assets/40b68f3f-c634-46d6-8980-d7fbb0dfebb2" />     <img width="200" height="400" alt="image" src="https://github.com/user-attachments/assets/655a3998-a7f3-4683-9977-756c5e15df42" />


# Implementation and steps involved:

# 1. Data Acquisition:
Acquired face image dataset from Kaggle consisting of 7049 faces with 15 keypoints. Data divided into images (npz file) and corresponding keypoints (csv file).
# 2. Preprocessing:
Null point values removed, resulting in 2140 images with 15 key points.
# 3. Bounding Boxes:
Defined bounding boxes around facial components using landmarks. Ensured bounding boxes cover facial features with minimal overlap.
# 4. Isolation of Features:
Features isolated using bounding boxes stored in separate matrices for each feature.
# 5. Applying K-Means:
Used K-means clustering to group similar facial features and remove duplicates. Clustering ensures similar features are grouped together for further analysis

# 6. Techniques Used in Sketch Generation:
> 6.1 Mask Generation:
. Masks created to facilitate Poisson Blending, denoting regions of interest like eyes, nose, mouth.
. Masks define regions where AI model focuses analysis, aiding in feature incorporation.

> 6.2 Poisson Blending:
Involves target image, input data, and masks.
. Target image: Grayscale outline of a face, providing sketch-like appearance.
. Masks used to isolate regions for blending corresponding facial features.
. Each facial component blended with target image using Poisson Blending technique.
. Resulting image composed of layers of target image and masks for each facial component.
. Mirroring used for simplicity, e.g., one eye selected and mirrored to represent both eyes.

# 7. Web Application
Our project concludes with the creation a user interface in form of a web application where users get to pick and choose features of their choice which are then blended together as per the discussed methodology and result is a unique face/sketch.

Use of python backend principles have been made. Django and docker have been utilised.
<img width="400" height="600" alt="image" src="https://github.com/user-attachments/assets/c83be184-04b5-4472-83b9-779c50374c07" />


# Resulting Sketch
<img width="300" height="600" alt="image" src="https://github.com/user-attachments/assets/8445397a-e04d-4470-94d1-41495a144b2a" />    <img width="300" height="600" alt="image" src="https://github.com/user-attachments/assets/e49efc3b-1ee8-4331-9ed2-40019ae48865" />

Fig.  Adding an eye of choosing (chosen attribute, corresponding mask and target image) and The other eye is a mirror image of previously chosen

<img width="300" height="600" alt="image" src="https://github.com/user-attachments/assets/0595fc23-7614-4fbe-9570-f20addc76232" />    <img width="300" height="600" alt="image" src="https://github.com/user-attachments/assets/e6ac9b81-7d94-4ace-a2cd-2427c0974120" />

Fig. Addition of nose and  Addition of mouth with a complete sketch






