#**Finding Lane Lines on the Road** 

##Writeup Template

###You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./Pipeline/1_import.png "Initial Import"
[image2]: ./Pipeline/2_grayscale.png "Image is grayscaled"
[image3]: ./Pipeline/3_blur_gray.png "Gaussian blur to reduce noise"
[image4]: ./Pipeline/4_canny.png "Canny Filter"
[image5]: ./Pipeline/5_canny_roi.png "ROI applied to Canny Filter"
[image6]: ./Pipeline/6_lines_from_hough.png "Hough lines"
[image7]: ./Pipeline/7_overlaid.png "Hough Lines applied on input image"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
