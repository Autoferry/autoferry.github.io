---
layout: post
title: Improved detection in camera video
category: SF
---
## Background
The first step in the situational awareness pipeline of any autonomous vehicle is to detect other vehicles and obstacles. This can be done by means of transponder systems (e.g. AIS), active exteroceptive sensors (radar, lidar) or passive exteroceptive sensors (optical and infrared cameras). Typically, a detection procedure processes every scan or image from the sensors independently, and feeds the extracted blobs to a tracking method, which declares a threat if it is able to establish a track on consecutive detections. 

For active sensors, relatively straightforward thresholding and segmentation techniques are typically used for detection. For passive sensors, especially for optical cameras, more advanced object recognition techniques are generally preferred. Convolutional neural networks (CNNs) have emerged as the undisputed benchmark leader in recent years. A handful of MSc students have worked on CNNs for ship detection in optical and infrared images in connection with the [Autosea project], see for example (Grini 2019).  

No detector is perfect. CNNs come with their own strengths and weaknesses. They can be trained to detect objects that would be very difficult to describe in more explicit terms, but are ill equipped to detect objects that differ too much from the training data. Their black-box nature make it difficult to analyze or predict their behaviour. Standard CNNs are, in common with other methods that work on single images, unable to exploit dynamic information that only can extracted from a sequence of images. More specifically, we have observed false alarms caused by buildings mistaken for ships, and misdetections because a boat was difficult to distinguish from the background. The latter is especially a problem in infrared images. 

Several approaches may be taken in the pursuit of more reliable detectors. Some of these are outline below. 

First, it is possible to design detectors that work on the video stream, instead of individual images. Even if the object in question, e.g., a kayak, is clearly visible in any individual images, spatio-temporal processing of several images simultaneously can reveal the presence of the object. In the tracking community, this is known as track-before-detect (TBD). 

Second, a better basis for detection decisions can be obtained by fusion of different sensors before detection. For example, the data from a camera and a lidar may be combined into an extrapolated point cloud that is more dense than the original lidar point cloud, and which also maintains the color information from the camera data. 

Third, standard CNN methods (Faster-RCNN, YOLO, SSD) only provide bounding boxes, and do not perform any segmentation. Better performance can perhaps be achieved by integrating the segmentation process into the detection procedure. This can be done in a variety of ways (Autoencoders, Mask RCNN). 




## Scope
The main goal of this project is to investigate the potential of alternatives to bounding-box CNN approaches for detection in optical and infrared images. This can be a project for a single student or a group of students. Several data sets are available, both include infrared images, optical images, infrared video, and joint infrared, lidar and radar video. While all these data sets can be used for testing, there may be a need for recording additional data sets depending on the amount of training data that is needed.  

## Proposed Tasks for the 5th year project

The details of the specialization project will depend on the interest of the student, but the following elements should in any case be part of it. 

1. Fundamental theory and algorithm description of the chosen detection method. 
2. Data consolidation: What are the available data sets, and which data sets do you use for training, validation and testing?
3. Implementation.
4. Performance evaluation. Precision and recall, or equivalent measures, must be part of this analysis. 

## Proposed Tasks for the master thesis

In the master thesis, the goal will be to make the developments from the 5th year project ready for integration in the sensor fusion systems of MilliAmpere and MilliAmpere2. This will include tasks such as the following. 

* Evaluation of detector performance on data recorded using the onboard sensors of the autonomous ferry. 
* Algorithms for segmentation and measurement extraction if this has not already been solved as part of the 5th year project. 
* Evaluation of mean square error statistics (i.e., measurement covariance) for the extraction algorithms. 
* 

## Contact
Supervisors [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo) and
[Øystein Kaarstad Helgesen](https://www.ntnu.edu/employees/oystein.k.helgesen) 

## References

* Grini, S. (2019): “[Object Detection in Maritime Environments: Systematic Training and Testing of Deep Learning-based Detection Methods for Vessels in Camera Images](http://folk.ntnu.no/edmundfo/msc2019-2020/grini_simen_msc_reduced.pdf)”, MSc thesis, NTNU. 

[Autosea project]: https://www.ntnu.edu/autosea
