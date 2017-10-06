# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

In order to find lane line I prepared two main functions. These are processVideo and processImage() functions. 

processVideo function is read the video file and video images send to processImage function.

processImage function is consisted with all required the image process functions.
This function return to back with processed image.

processImage function then first converts the HLS color field by calling the processWhiteYellow function. The white and yellow color areas are found separately on the image. It combines these masks and applies them on the image. With the grayScale function, I got the color channel I need in the image. I reduced the noise on the image with the Gaussian Blur function. I applied Canny transform with canny function. With the regionOfInterest function I have specified the areas of interest on the image. I have specified lines with the houghLines function. I use the laneLines and averageLine functions to determine the slopes, lengths, line numbers of the left and right lanes, and to fit the image.

Last step using drawLines() function I draw left and right lane lines and combine with the original image.

Pipeline drawLines lines on the output images:
[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

[image1]: ./examples/grayscale.jpg "Grayscale"
[image1]: ./examples/grayscale.jpg "Grayscale"
[image1]: ./examples/grayscale.jpg "Grayscale"
[image1]: ./examples/grayscale.jpg "Grayscale"
