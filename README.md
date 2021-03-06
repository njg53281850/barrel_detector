# barrel_detector
This repository contains sample code to detect an element with specific color property (a blue barrel in this project) from an image. 

The file "hand-label.py" is used to manually label region of interest from training images as samples.

The file "model_build.py" is used to build Gaussian model based on samples get from last step. Here, input image is converted from RGB to YCRCB color space and it is assumed that value of Cr and that of Cb at each pixel satisfy a 2-dimensional Gaussian distribution. Mean and covariance to build Gaussian model as well as prior probability of each color class are calculated using "model_build.py" and results are stored as ".npy" files.

The file "barrel_detector" is used to detect the specific element from a new image. It defines a class called "BarrelDector" and there are mainly two methods in this class: segment_image and get_bounding_box. Input of both of them are image read using cv2.imread() method. Output of "segment_image" is a binary mask (area of interest: 1, other: 0) of the original image. Output of "get_bounding_box" is a list of list with information of boundary of area of interest. Each list inside contains the coordinate of the left-up corner and the right-down corner of a boundary. If needed, the boundaries can be drawn on the mask or original image.

package used in this project: numpy, matplotlib, scikit-image, open-cv, roipoly
