### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. 
  - First, I converted the images to grayscale. 
  - then I used gaussian_blur to smooth the gray images.
  - then I useed canny edge detection to find out eges.
  - then I mask out the region I don't interest.
  - then I used hough algrithm to find out Lines.
  - In the end, I selected those reasonable lines and created lanes accordingly and drawed lanes on to the original image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by 
- Calculate lines's slope.
- Filter out those lines with low slope, which could not be part of lane line.
- According to the slope to classify those lines, find out them belong to left or right lane.
- Collect useable lines.
- Finally, use np.polyfit to find out the left/right lane individually and draw them out. 


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the car doing a steep turn. My pipeline would totally lost its function.  

Another shortcoming could be what would happen when the car rides on a lane, it would fail to detect that lane. 


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to merge previous video frame's lane data into current frame's lane prediction, so the lane drawing could be more stable, to reduce the oscillation.
