# ADVANCED LANE FINDING

The goals of this project are the following: 
  1. Compute the camera calibration matrix and distortion coefﬁcients given a set of chessboard images. 
  2. Apply a distortion correction to raw images. 
  3. Use color transforms, gradients, etc., to create a thresholded binary image. 
  4. Apply a perspective transform to rectify binary image ("birds-eye view"). 
  5. Detect lane pixels and ﬁt to ﬁnd the lane boundary. 
  6. Determine the curvature of the lane and vehicle position with respect to center. 
  7. Warp the detected lane boundaries back onto the original image. 
  8. Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.


## CAMERA CALIBRATION

The first step of this project was to calibrate the camera and calculate the distorsion coefficients. This can be seen in the second cell of the jupyter notebook and the results in this picture ![Calibrated](https://github.com/ranceaaa/PROJECT-2---ADVANCED-LANE-FINDING/blob/master/images/calibrated.png).

## COLOR AND GRADIENTS TRANSFORMATIONS

This part took a lot of time because I was trying to find a 'perfect' combination. This wasn't possible and the best one I came with can be found in function: best_mask. <> More pictures can be seen in the images folder.

## PERSPECTIVE TRANSFROMATION

In this part of the project, the goal was to change the perspective to a top view perspective. This was done in functions warp and unwarp

## LINE DETECTION USING POLYNOMIAL

Line detection is achieved using 2 functions: fit_polynomial and search_around_poly. The first one is doing a complete detection and the second one is looking only on the top to check for changes and detect the new lines. <> 

## CURVATURE AND CAR POSITION

The curvature is calculated in both pixels and an approximation to meters. Also, the position on the road is approximated in meters considering that the camera is positioned in the middle of the car. (functions: measure_curvature_pixels, measure_curvature_real, calculate_pos.

## FINAL RESULTS

After all the computations were made, the images is unwarped and a mask with the lane is applied (green color)

In output_video folder, the videos can be seen. The first one: project_video is using only fit_polynomial function. The second one: challenge_video si using both fit_polynomial and search_around_poly functions and takes into consideration the last detected lanes.

## PROBLEMS

1. Region of interest ( perspective transform) / camera position on different videos
2. If it is too small, line dot line combination couldn't be detected sometimes
