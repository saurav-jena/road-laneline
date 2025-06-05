Lane Detection is a computer  vision  task  that  involves  identifying  the boundaries  of  driving  lanes  in  a video  or image  of a  road scene. The  goal is  to  accurately  locate  and  track  the  lane  markings  in  real-time, even  in challenging  conditions  such  as  poor  lighting ,  glare ,  or  complex  road layouts.
![image](https://github.com/user-attachments/assets/2141f84c-1801-44cf-bec7-c801c9fcd8c6)
// Gaussian Smoothing
 Apply Gaussian filter to the input image
 // Gradient Calculation
 Compute gradient magnitudes and directions using Sobel operators
 // Non-maximum Suppression
6For each pixel in the gradient direction:
    Check if it is a local maximum, preserving only those values
 // Double Thresholding![image](https://github.com/user-attachments/assets/acec7e4c-a075-4cf3-96fb-222202f3e410)
For each pixel in the gradient magnitude
 If above high threshold, mark as strong edge
   If between high and low thresholds, mark as weak edge
.   Otherwise, mark as non-edge
. // Edge Tracking by Hysteresis
For each weak edge pixel:
 If connected to a strong edge, mark as part of the edge
   Otherwise, discard the weak edge
 Final result is an image with detected edges
![image](https://github.com/user-attachments/assets/47545230-d9fa-4abc-bd03-be0d8611cbb2)
This Python code uses OpenCV and Matplotlib to process a video, implementing road lane detection. It reads a video file, applies Canny edge detection, creates a region of interest, and uses the Hough transform to identify and draw road lanes on each frame. The region_of_interest function defines a triangular area in the bottom half of the frame, focusing on the road. The draw_the_lines function overlays detected lane lines on the original frame. The process function converts the image to grayscale, applies Canny edge detection, and then identifies and draws lines using the Hough transform. The code continuously processes video frames, displaying the output with highlighted road lanes. Pressing 'q' exits the video playback loop. This script is a simple demonstration of road lane detection in a video stream using computer vision techniques.
![image](https://github.com/user-attachments/assets/6e7b82c0-6e08-4f65-bf4c-c7f81ba15849)
