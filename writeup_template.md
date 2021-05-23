# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report




[image_gray]: ./test_images_output/solidWhiteCurve_grayed.jpg "Grayscale"
[image_edges]: ./test_images_output/solidWhiteCurve_edges.jpg "Edges"
[image_lines]: ./test_images_output/solidWhiteCurve_lines.jpg "Lines"
[image_region]: ./test_images_output/solidWhiteCurve_region.jpg "Region of interest"

---

### Reflection

### 1. Lane detection pipeline description

My pipeline consisted of 5 steps:


#### 1. Convert the input image to grayscle to make it simpler for processing

![alt text][image_gray]

#### 2. Apply gaussian filter to blur the gray image a bit to reduce the noise.
#### 3. Detect edges using Canny edges function with Canny() function.
![alt text][image_edges]

#### 4. Mask the regions of interest
![alt text][image_region]

#### 5. Apply hough transformation to find the lines
![alt text][image_lines]


### 2. Potential shortcomings with your current pipeline

The result of the pipeline looks good in the 2 sample videos. However the performance is not ideal in the optiuonal challenge video. I think the potential challenges are:

 * The lines are curved.

 * Lines are fading as the road is pretty old, and there are also patches, and 
 different textures on the road.
 
 * The contrast ratio between the yellow line and the asphalt is relatively low.
 
 * The road situation changes due to shadows from the trees.


### 3. Suggest possible improvements to your pipeline

* the current parameters we use in Canny edges detection algorithm is hardcoded.

* Use more sophisticated algorithm for outlier detection. 

* To make the line detection more accurate, probably we could apply filters to filter out all colors other than yellow and white.

* Use temporal averages on the line drawing, so the lines could change smoothly.
