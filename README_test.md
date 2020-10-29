# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

This project is to detect lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.


Files contained in this repository:
  ./test_images - Original images for testing and output Images with lane lines 
  ./test_videos - Origianl videos for testing
  ./test_videos_output - Videos with lane lines

---

**Lane Line Detection Testing Image Example**

Original Image:
![](./test_images/solidWhiteCurve.jpg)
Output Image with Lanes:
![](./test_images/solidWhiteCurveProcessed.png)

---
### Project Summary
---
There are three parts to the reflection:

### 1. Pipeline of Project
* 1. Describe the pipeline
* Step 0 - Get Image and the size of image
* Step 1 - Convert a image to Grayscale of the image
* Step 2 - Apply Gaussian smoothing / blurring to the grayscaled image
* Step 3 - Apply Canny edge detector to find all edges
* Step 4 - Define the region of interest and apply region masking surroundings
* Step 5 - Apply Hough transformation to find the lines in the region of interest
* Step 6 - Draw the lines on the edge of the image using draw_lines() function. More than one lines are generated from the previous step for left/right lane. Use the slope to detect if a specific line belongs to the left/right lane. Then fit a liear polynomial among all the points and use that line as the left/right lane. It helps to reduce the number of lines in the image.

### 2. Identify any shortcomings
* One shortcoming is on the curve, the line cannot follow fast enough to the speed of slope changes  
* The lane line direction is not always correct when the actual lane in is not that clear.
* optional challenge - cannot show stable visibility (slope calc should be re-do)


### 3. Suggest possible improvements
* Missing lane - interpolate previous frame's lanes to accomodate missing/blur lanes 
* Light Adaptability - video processing needs some level or exploitation to adapt various light conditions  (very bright sunlight can cause reflction of white lane, very dark light in the night can cause lots of missing lanes) 
* more precise calculation (i.e. instead of linear slope, some sort of elliptical line) algorithm is needed to detect curved lanes.


