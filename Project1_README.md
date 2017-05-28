## Project: Search and Sample Return
### Readme : This file is meant to guide the reviewer along the steps and methods taken to accomplish the project in hope of clarifying to the reviewer the steps taken with clarity.

---


**The steps of this project are the following:**  

**Training / Calibration**  

* Recorded data was taken  "Training Mode", the data is storded in the "Recorded dataset " zip file. 
* Original Jupyter Notebook which was provided ran succufely 
* Functions were added  to detect obstacles and samples of interest (golden rocks)
* The `process_image()` function was filled with the appropriate image processing steps (perspective transform, color threshold etc.) to get from raw images to a map.  The `output_image` was created, the results  demonstrated that our mapping pipeline works.
* The  `moviepy` function was used to process the images our saved dataset with the `process_image()` function. Video is included as test_mapping.mp4 you may run the file to check the results of the notebook. (Also to fully run the jupyter notebook kindly note that the calibration folder and recorded dataset zip filed should be uncompressed and in the same folder as the code folder.

**Autonomous Navigation / Mapping**

* The  `perception_step()` function was filled within the `perception.py` script with the appropriate image processing functions to create a map and update `Rover()`. 
* The  `decision_step()` function within the `decision.py` was tuned for better deicision making . 
  

[//]: # (Image References)

[image1]: ./reults/img_1.png
[image2]: ./results/img_2.png
[image3]: ./results/img_3.png

## [Rubric](https://review.udacity.com/#!/rubrics/916/view) Points
### Here I will consider the rubric points individually and describe how I addressed each point in my implementation.  

---
### Writeup / README

#### 1. Provide a Writeup / README that includes all the rubric points and how you addressed each one.  You can submit your writeup as markdown or pdf.  

This write up has been provided.

### Notebook Analysis
#### 1. Run the functions provided in the notebook on test images (first with the test data provided, next on data you have recorded). Add/modify functions to allow for color selection of obstacles and rock samples.
*Several functions were added to the original python notebook :   
*Prespective transform with the indicated source and destination point using opencv function warpPrespective and getPrespective.  
*Detecting the rock samples:This was done by selcting the pixels between upper and lower RGB threshold (between 60,60,45, and 255,255,0)  
*Detecting obstacles:This was done by selcting the pixels between  lower RGB threshold of (160,160,160) however a lower threshold was also implemented to not select the black pixels the unknow regiond that is why a lower threshold of (3,3,3) was put in place.  
*The rotation and translation functions were added based on the formulas provided during the lessons.  
You may refer to the below images for the actual results obtained :  

![alt text][image1]
![alt text][image2]
![alt text][image3]  

#### 1. Populate the `process_image()` function with the appropriate analysis steps to map pixels identifying navigable terrain, obstacles and rock samples into a worldmap.  Run `process_image()` on your test data using the `moviepy` functions provided to create video output of your result. 
  
  *Process image () was populated according the subfunctions described above. You may refer to the video test_mapping.mp4 to check the results
### Autonomous Navigation and Mapping

#### 1. Fill in the `perception_step()` (at the bottom of the `perception.py` script) and `decision_step()` (in `decision.py`) functions in the autonomous mapping scripts and an explanation is provided in the writeup of how and why these functions were modified as they were.


#### 2. Launching in autonomous mode your rover can navigate and map autonomously.  Explain your results and how you might improve them in your writeup.  

Here I'll talk about the approach I took, what techniques I used, what worked and why, where the pipeline might fail and how I might improve it if I were going to pursue this project further.  



![alt text][image3]


