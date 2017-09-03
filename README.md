## Project: Search and Sample Return

**Training / Calibration**  
## The Simulator
The first step is to download the simulator build that's appropriate for your operating system.  Here are the links for [Linux](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Linux_Roversim.zip), [Mac](	https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Mac_Roversim.zip), or [Windows](https://s3-us-west-1.amazonaws.com/udacity-robotics/Rover+Unity+Sims/Windows_Roversim.zip).  

You can test out the simulator by opening it up and choosing "Training Mode".  Use the mouse or keyboard to navigate around the environment and see how it looks.

* Download the simulator and take data in "Training Mode"
* Test out the functions in the Jupyter Notebook provided
* Add functions to detect obstacles and samples of interest (golden rocks)
* Fill in the `process_image()` function with the appropriate image processing steps (perspective transform, color threshold etc.) to get from raw images to a map.  The `output_image` you create in this step should demonstrate that your mapping pipeline works.
* Use `moviepy` to process the images in your saved dataset with the `process_image()` function.  Include the video you produce as part of your submission.

**Autonomous Navigation / Mapping**

* Fill in the `perception_step()` function within the `perception.py` script with the appropriate image processing functions to create a map and update `Rover()` data (similar to what you did with `process_image()` in the notebook). 
* Fill in the `decision_step()` function within the `decision.py` script with conditional statements that take into consideration the outputs of the `perception_step()` in deciding how to issue throttle, brake and steering commands. 
* Iterate on your perception and decision function until your rover does a reasonable (need to define metric) job of navigating and mapping.  

[//]: # (Image References)

[image1]: /RoboND-Rover-Project-master/misc/rover_image.jpg
[image2]: /RoboND-Rover-Project-master/calibration_images/example_grid1.jpg
[image3]: /RoboND-Rover-Project-master/calibration_images/example_rock1.jpg 
[image4]: /RoboND-Rover-Project-master/output/Results.png

## [Rubric](https://review.udacity.com/#!/rubrics/916/view) Points
### Here I will consider the rubric points individually and describe how I addressed each point in my implementation.  

---
### Writeup / README

### Notebook Analysis
#### 1. Run the functions provided in the notebook on test images (first with the test data provided, next on data you have recorded). Add/modify functions to allow for color selection of obstacles and rock samples.

![alt text][image1]

The code in Notebook is not modified at any cell. The data is been recorded by the training mode and tested through this python notebook successfully.

#### 1. Populate the `process_image()` function with the appropriate analysis steps to map pixels identifying navigable terrain, obstacles and rock samples into a worldmap.  Run `process_image()` on your test data using the `moviepy` functions provided to create video output of your result. 

![alt text][image2]

The process_image() in notebook is executed as it is without changes to get the idea of whole execution and also the new dataset is being made into a movie and shown in notebook using moviepy.

![alt text][image3]

### Autonomous Navigation and Mapping

#### 1. Fill in the `perception_step()` (at the bottom of the `perception.py` script) and `decision_step()` (in `decision.py`) functions in the autonomous mapping scripts and an explanation is provided in the writeup of how and why these functions were modified as they were.

perception.py has a function `perception_setp(Rover)` which is similar to process_image() in notebook. Its been tweaked and modifified after taking help from different sources given in the course. The changes are using existing functions to apply perspective transform to an image, applying color threshold for identifiying navigable terrain, obstables and rocks, updading the frames to be displayed during autonomous mode and updating navigable map.

decision.py is all about making decisions after receiving object from perception.py. The code itself was capable of moving forward, steering and brakes. The updates in the code includes picking a rock if its infront of rover, checking whether all six rocks have been collected and recording starting position coordinates.

#### 2. Launching in autonomous mode your rover can navigate and map autonomously.  Explain your results and how you might improve them in your writeup.  


![alt text][image4]

After several tries of going back and forth in the guidelines of Udacity Repository, Youtube walkthrough and help from Slack, the results were very good. The rover was moving on its own based on perception and most importantly the fedility was 83.2% after covering 40% of map. Also the code for identifying and picking rock was also a success for me. 
I was running the autonomous mode on 1024x768 resuolution with graphics quality as fantastic. With smooth performance on Windows 10 I was able to pick 5 rocks after covering 98.5% of map. There is improvement needed regarding testing how to get back to starting position. Also I always have worked on Linux but the simulator was running at very low frames per second so I will also look into it as well.




