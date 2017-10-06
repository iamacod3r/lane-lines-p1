# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

[//]: # (Image References)

[whiteCurve]: ./test_images/solidWhiteCurve.jpg "solidWhiteCurve - original"
[whiteCurveOutput]: ./test_images/output/solidWhiteCurve.jpg "solidWhiteCurve - output"
[whiteRight]: ./test_images/solidWhiteRight.jpg "solidWhiteRight - original"
[whiteRightOutput]: ./test_images/output/solidWhiteRight.jpg "solidWhiteRight - output"
[yellowCurve]: ./test_images/solidYellowCurve.jpg "solidYellowCurve - original"
[yellowCurveOutput]: ./test_images/output/solidYellowCurve.jpg "solidYellowCurve - output"
[yellowCurve2]: ./test_images/solidYellowCurve2.jpg "solidYellowCurve2 - original"
[yellowCurve2Output]: ./test_images/output/solidYellowCurve2.jpg "solidYellowCurve2 - output"
[yellowLeft]: ./test_images/solidYellowLeft.jpg "solidYellowLeft - original"
[yellowLeftOutput]: ./test_images/output/solidYellowLeft.jpg "solidYellowLeft - output"
[whiteSwitch]: ./test_images/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch - original"
[whiteSwitchOutput]: ./test_images/output/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch - output"


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the drawLines() function.

In order to find lane line I prepared two main functions. These are processVideo and processImage() functions. 

processVideo function is read the video file and video images send to processImage function.

processImage function is consisted with all required the image process functions.
This function return to back with processed image.

processImage function then first converts the HLS color field by calling the processWhiteYellow function. The white and yellow color areas are found separately on the image. It combines these masks and applies them on the image. With the grayScale function, I got the color channel I need in the image. I reduced the noise on the image with the Gaussian Blur function. I applied Canny transform with canny function. With the regionOfInterest function I have specified the areas of interest on the image. I have specified lines with the houghLines function. I use the laneLines and averageLine functions to determine the slopes, lengths, line numbers of the left and right lanes, and to fit the image.

Last step using drawLines() function I draw left and right lane lines and combine with the original image.
drawLines() except a list of lines as the second parameter. Each line is a list of 4 values (x1, y1, x2, y2). The data type needs to be integer for cv2.line to work without throwing an error.

Pipeline drawLines lines on the output images:
![alt text][whiteCurve]
![alt text][whiteCurveOutput]
![alt text][whiteRight]
![alt text][whiteRightOutput]
![alt text][yellowCurve]
![alt text][yellowCurveOutput]
![alt text][yellowCurve2]
![alt text][yellowCurve2Output]
![alt text][yellowLeft]
![alt text][yellowLeftOutput]
![alt text][whiteSwitch]
![alt text][whiteSwitchOutput]


### 2. Identify potential shortcomings with your current pipeline

Right lane line should be more stable.

### 3. Suggest possible improvements to your pipeline

It only detects the straight lane lines. It is an advanced topic to handle curved lanes (or the curvature of lanes). We'll need to use perspective transformation and also poly fitting lane lines rather than fitting to straight lines.

