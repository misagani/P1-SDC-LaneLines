# **P1 - Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

This project will detect lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.

To meet specifications in the project, take a look at the requirements in the [project rubric](https://review.udacity.com/#!/rubrics/322/view)

Goal
---

The goals of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on my work in a this written report

Reflection
---

Reflection describes the current pipeline, identifies its potential shortcomings and suggests possible improvements.

[//]: # (Image References)

[pipe1]: ./pipelines/whiteCarLaneSwitch_0_original.jpg "Getting Image Source"
[pipe2]: ./pipelines/whiteCarLaneSwitch_1_masked.jpg "Region Masking"
[pipe3]: ./pipelines/whiteCarLaneSwitch_2_grayscale.jpg "Grayscale"
[pipe4]: ./pipelines/whiteCarLaneSwitch_3_blurred.jpg "Gaussian Blur"
[pipe5]: ./pipelines/whiteCarLaneSwitch_4_col_sel.jpg "Color Selection"
[pipe6]: ./pipelines/whiteCarLaneSwitch_5_canny.jpg "Canny Edge"
[pipe7]: ./pipelines/whiteCarLaneSwitch_6_houghed.jpg "Hough Transform"
[pipe8]: ./pipelines/whiteCarLaneSwitch_7_lines.jpg "Draw Lines"
[pipe9]: ./pipelines/whiteCarLaneSwitch_8_final.jpg "Weighted Image"

--- 

## My Pipelines

My pipeline consists of these steps.
* **Getting Image Source.** This will return original image.

![alt text][pipe0]

* **Region Masking.** Applies an Image Masking. Only keeps the region of the image defined by the polygon formed from vertices. The rest of the image is set to black.

![alt text][pipe1]

* **Grayscale.** This will return an image with only one-color channel.

![alt text][pipe2]

* **Gaussian Blur.** Applies a Gaussian Noise Kernel.

![alt text][pipe3]

* **Color Selection.** Applies the Color Selection.

![alt text][pipe4]

* **Canny Edge.** Applies the Canny Edges Transform.

![alt text][pipe5]

* **Hough Transform.** Applies the Hough Transform.

![alt text][pipe6]

* **Draw Lines.** Drawing Solid Lines based on slope from Hough Transform result.

![alt text][pipe7]

* **Weighted Image.** Combine Lines and Real Image.

![alt text][pipe8]

## Potential Shortcomings

There are several potential shortcomings.
* Potential shortcoming would happen when lanes meet sharp-turn. Need to be fixing the slope algorithm. 
* Another shortcoming would happen if the line not solid, and the color not consistent.
* Another shortcoming would happen if the line not visible, maybe there are object covering it.
* Another shortcoming would happen if the line covered with shadow on one side. For example, if left line not covered, and right line covered, then only left line that detected by this algorithm.
* And one more shortcoming would happen if the resolution of Images/Videos different (not standardized). Because the lines that created, using fixed coordinates.



## Possible Improvements

There are several possible improvements.
* Possible improvement would be to creating a historical data of slope. So we can predict next slope depend on before data. And then we can using statistics for searching the slope, not simple just like this, only counting the average value.
* Another possible improvement would be to create dynamic algorithm for drawing a lines. Possibly by using shape of the image, and then proportionally using that for drawing a lines.
* Or maybe using more Advanced Image Processing techniques.


## Challenge

I try the Challenge video and adding one my own video. Very Excited!


## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
