#**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

###1. Pipeline

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

* Hough results are filtered according to slope ((y2-y1)/(x2-y2)) (positive right line/negative left line)
* Vertical and Horizontal slopes are filtered out
* The mean slope and standard dev is calculated
* Outliers of mean+2_standard_devs are excluded
* Mean slope is recalculated for left and right lines
* Mean y-intercept is calculated
* Lines starting from the bottom edge, going to .6*max_y are calculated using the mean left and right slope and y_intercept y=mx+b
* A circular buffer of the mean left and right slopes of the last ten frames is kept to filter out outliers

![Alt text](./Pipeline/6_lines_from_hough.png?raw=true "Hough Lines")

The resulting lines are overlaid onto the original input image

![Alt text](./Pipeline/7_overlaid.png?raw=true "Hough Lines applied on input image")


---

### Reflection



###2. Identify potential shortcomings with your current pipeline

* The current pipeline is jittery at times.


###3. Suggest possible improvements to your pipeline

* To improve performance a check on the line y-intercept and a ring buffer of sensible y-intercepts could be kept from frame to frame.
* y-intercepts can only change as fast as a lane change (e.g. 1000 pixels/s->25 pixels/frame-to-frame) 
* Confidence in the lane could be color-coded (e.g. how many hough lines are detected)


