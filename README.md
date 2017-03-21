#**Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Pipeline

Original frame is imported:

![Alt text](./Pipeline/1_import.png?raw=true "Original Input image")

Frame is grayscaled:

![Alt text](./Pipeline/2_grayscale.png?raw=true "Grayscaled")

Gaussian blur is applied to reduce noise:

![Alt text](./Pipeline/3_blur_gray.png?raw=true "Gaussian blur to reduce noise")

Canny Filter is applied to detect edges:

![Alt text](./Pipeline/4_canny.png?raw=true "Canny Filter")

ROI from (bottom_left) (max_x/2-x_res/50, .6*max_y) (max_x/2+x_res/50, .6*max_y) (bottom_right):

![Alt text](./Pipeline/5_canny_roi.png?raw=true "ROI applied to Canny Filter")

* Hough results are filtered according to slope ((y2-y1)/(x2-y2)) (positive righ line/negative left line)
* Vertical and Horizontal slopes are filtered out
* The mean slope and standard dev is calculated
* Outliers of mean+2_standard_devs are excluded
* Mean slope is recalculated for left and right lines
* Mean y-intercept is calculated
* Lines starting from the bottom edge, going to .6*max_y are calculated using the mean left and right slope and y_intercept y=mx+b

![Alt text](./Pipeline/6_lines_from_hough.png?raw=true "Hough Lines")

The resulting lines are overlaid onto the original input image

![Alt text](./Pipeline/7_overlaid.png?raw=true "Hough Lines applied on input image")


---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 




###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
