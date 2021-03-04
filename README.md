# FeetAndShoeMeasurement - Feet and Shoe size measurements without Deep Learning
Feet Plus Shoe size Measurement without Deep Learning

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

## Assumptions
* Printer Paper is used as a reference (Height/Width is known and White background will help in Preprocessing)
* Foot should be in center, touching one edge of paper.
* Image should be clicked form top angle. 
* Paper should be completely visible in the clicked image. 


