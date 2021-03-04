# FeetAndShoeMeasurement - Feet and Shoe size measurements without Deep Learning
**Problem** : Determine the Feet and corresponding Shoe size of a person without Deep Learning, given a image clicked by the person itself. 

## How to Evaluate?
* Clone the repo
* Install required packages using requirements.txt
* keep the image inside "data" folder. A sample image has already been kept in data folder.
* run main.py

## Working Aproach
* convert raw image to HSV format
* Remove noise using Gaussian Blur
* Run k-means clustering on preprocessed image for color based segmentation
* Detect the edges in clustered image. 
* Find contours in Edge Detection output 
* Generate the bounding Box to get the height/width of Paper and Feet

## Libraries used
* OpenCV
* Sklearn

## Assumptions
* Printer Paper is used as a reference (Height/Width is known and White background will help in Preprocessing)
* Foot should be in center, touching one edge of paper.
* Floor color should be different than white. 
* Image should be clicked form top angle. 
* Paper should be completely visible in the clicked image. 

## Sample outputs

<p align="center">
  <img src="./images/sampleopt.png">
</p>

## Shoe Size charts for Mens and Womens
**Designed Solution gives feet size in CM's, that can be compared with below chart for Corresponding Shoe Size**
<p align="center">
  <img src="./images/ShoeSizeChart.png">
</p> 


## Limitations
* If floor color is white, then it will difficult to segment the paper. 
* Feet should not go out of the paper. Currently A4 size printer paper has ben chosen as reference. To fit all sizes, A1 paper can be taken as reference.
* If there is no closed curv after edge detection, its difficult to find bounding box. Only closed curv is considered as a contour. And bounding box is generated on top of that. As it can be seen in the below image, bounding box is not generated on feet but only on the paper.
<p align="center">
  <img src="./images/wrongcnt.png" width=70% height=70% >
</p>  



## Other Ideas
* Deep learning models (Trained on feet and shoe Dataset) can be used to segment the paper and feet with more accuracy. One can use "[Part Grouping Network](https://arxiv.org/abs/1808.00157)" 


## References 
* OpenCV - https://docs.opencv.org/3.4/d4/d73/tutorial_py_contours_begin.html
* Part grouping Network - [Paper](https://arxiv.org/abs/1808.00157)
