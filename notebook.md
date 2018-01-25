
the image distortion

why use the chessboard as a tool to calibrate the image, and how it works? how to implement it with python and opencv? 

calibrate your own camera.

perspective transform
implement a perspective transformation using python and opencv. 

Sobel operator
the x vs y direction. 
the x, y, magnitude, gradient 

the color space
rgb, hls,hsv 
hue, saturaion, color, brightness, lightness and value

the sliding window, 
using convolution to implement the sliding window. 

determine the curvature of the line. 

mapping from the pixel world to real world. 

consider how this detected lane lines can be used to support the vehicle control, what informaion it can provide? 
1. the offset of the car from the lane line center location (while this is useful in the later control stage, namely, PID, for CTE)
2. the curvature of the lane line can help with the control of the steering angel. if we could  get the look ahead distance large enough, this information can help with the trajectory planning.  
3. the line lane can help on the free space detection. the lane line range can be used to speed up other processing, this can play a role as region of interest. 
4. in general, a precise lane line can provide information of the lane line provides for human driver. 

sanity check of the detection:
1. similiar curvature
2. right distance 
3. parallel

smoothing is a technique appears quite often in self-driving courses. 

*summary of what i learned so far*:
for the lane line detection, the first approach is using the canny edge detection and then using hough transformation to detect the straight lines. this works for the straight line, but not working for the curved lines. this may can be fixed with more complicated hough transformation, for example, using it to detect the curved line, instead of the straight line. 

the other appoach is using the various features of the image, for example, the color channel,the gradient in x, y or directly or in combined manner, by applying the gradient to the images. now, instead of using hough transformation, here using a sliding window to detect the line; 

once the line is detected, it can be warped, using perspective transformation. to do the perspective transformation, the camera should be calibrated to get the image undistortated, then on the warped images, we can calculate the line curvature, and map it into the real world, the information can be used to help vehicle control.  


## Resources 
### on image distortion
https://en.wikipedia.org/wiki/Distortion_(optics://en.wikipedia.org/wiki/Distortion_(optics)

### on image calibration
http://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_calib3d/py_calibration/py_calibration.html#calibration

### on perspective transformation
http://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_imgproc/py_geometric_transformations/py_geometric_transformations.html?highlight=perspective

https://en.wikipedia.org/wiki/3D_projectio://en.wikipedia.org/wiki/3D_projection


