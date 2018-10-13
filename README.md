# **Finding Lane Lines on the Road**

## The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road by using Python and OpenCV
* Reflect on my work in a written report by using markdown file


[//]: # (Image References)
[image1]: ./test_images/solidWhiteCurve_laneFound.jpg

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps.
* Step 1: Standardize the image by using cv2.resize(image, (960, 540))
* Step 2: Convert the image from RGB to HSV. Then use the hsv_mask based on the V (brightness) value to capture the features of brightness of lanes
* Step 3: Apply Gaussian blurring (the technique from the course) to the masked image
* Step 4: Apply Canny function to capture the edges
* Step 5: Define the region of interest
* Step 6: Define parameters for Hough lines and draw the lines   

In order to draw a single line on the left and right lanes, I modified the **draw_lines()** function by the following steps:
* Define the slope and center of line elements from the function **_cv2.HoughLinesP_**
* Separate left and right lanes based on different slopes. Basically positive slope is right lane and negative slope is left lane
* Average all the right and left lanes. Then do an extrapolation to the top and bottom of the lane

If you'd like to include images to show how the pipeline works, here is how to include an image:

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline

The images (or videos) in the project are based on the following assumptions:
* The images from the camera always has the same position with respect to the road
* There is no other obstacle in front of the camera
* There are always white and/or yellow lines in the image
* The weather condition is good in order to allow me capture the feature of the lines

One potential shortcoming would be if one of the above assumptions is not true - for example, the image position changes, my predefined _**Region of Interest**_ function wouldn't be functioning properly.  

Another shortcoming could be if there is one car in front of the camera, it would give more challenges for the pipeline function.


### 3. Suggest possible improvements to your pipeline

The possible improvements could be
* Update the _**Region of Interest**_ dynamically
* If no line is detected, the pipeline could estimate the right and left lanes based on previous information or based on some other references (I think I would learn more information/techniques from the course)
"# CarND-LaneLines-P1" 
"# CarND-LaneLines-P1" 
"# CarND-LaneLines-P1" 
