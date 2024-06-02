# Sketching-Assistant-System-using-Poisson-Blending
A web application to generate new and custom faces/sketches using the concept of Poisson Blending involves concept of feature extraction, image manipulation, array manipulation, clustering and deep learning.
# Requirements
> numpy: coordinates function to convert and access arrays. Used for mathematical methods such as finding mean, min-max function, floor, ceiling functions, sqrt functions, random choice function, concatenate function,  reading npz file etc
> pandas: reading csv file. 
> scipy: used during Poisson Blending for methods like laplacian() and linalg() which are used for gradient solving and linear least square solving.
> matplotlib: used for subplot generation of faces in matrices, making of rectangular boxes during feature extraction (use of matplotlib.patches) and graph generation 
> cv2: to access, normalise, resize the images
> skimage: to resize cropped images
> sklearn: used to perform K-Means clustering
> os: to access directory
# Algorithms Used:
> K-Means Clustering: used to collect similar features together
> Poisson Blending: involves use of masks to create create a new image by combining an input image with a target image.


