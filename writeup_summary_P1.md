# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images/out_solidWhiteCurve.jpg

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

#### For the images:

My pipeline **"draw_lane_line(image)"** consisted of 5 steps. 
1. Convert the images to grayscale

1. Use gaussian blur to reduce image details

1. Use canny function to find the edges from image

1. Set a region of interest to focus on the potential area for lane lines

1. In hough transform function, I seperated positive and negtive slope of the lines, and did a simply polyfit to get left and right lines

![alt text][image1]

#### For the videos:

I found the image pipeline is not working perfect for each image inside the video, if we treat every single frame as a seperate image, the result will be discrete and machine will be confused with sudden changes.

So in my pipeline **"draw_lane_line_optimize(images)"** i was trying to get all the frames as input and do some smooth between frames, but i don't have enough time to finish it.

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when the lane is curving so it will not be detected as a straignt line any more. 

Another shortcoming could be if we have multiple candidates all looks like lanes due to the direction and edges are all confusing the result.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to change the ROI to a adjustable area so it can be changed during time.

Another potential improvement could be to smoothing the lines over time.
