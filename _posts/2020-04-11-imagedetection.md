---
layout: post
title: Improved detection in camera video
category: SF
---
## Background
The first step in the situational awareness pipeline of any autonomous vehicle is to detect other vehicles and obstacles. This can be done by means of transponder systems (e.g. AIS), active exteroceptive sensors (radar, lidar) or passive exteroceptive sensors (optical and infrared cameras). Typically, a detection procedure processes every scan or image from the sensors independently, and feeds the extracted blobs to a tracking method, which declares a threat if it is able to establish a track on consecutive detections. 

For active sensors, relatively straightforward thresholding and segmentation techniques are typically used for detection. For passive sensors, especially for optical cameras, more advanced object recognition techniques are generally preferred. Convolutional neural networks (CNNs) have emerged as the undisputed benchmark leader in recent years. A handful of MSc students have worked on CNNs for ship detection in optical and infrared images in connection with the [Autosea project], see for example (Grini 2019).  

No detector is perfect. CNNs come with their own strengths and weaknesses. They can be trained to detect objects that would be very difficult to describe in more explicit terms, but are ill equipped to detect objects that differ too much from the training data. Their black-box nature make it difficult to analyze or predict their behaviour. Standard CNNs are, in common with other methods that work on single images, unable to exploit dynamic information that only can extracted from a sequence of images. 







## Scope
As a primary objective, this project aims to say something about the suitability of different factor graph libraries for applications in target tracking. At an early stage in the autumn semester, a more concrete application, such as one of the two examples mentioned above, should be chosen for a more in-depth study. 

This can be a project for one student or for two students working together. 

## Proposed Tasks for the 5th year project

1. Make yourself familiar with basic theory for probabilistic graphical models. Summarize the main types of models and key results in your report.  
2. Make yourself familiar g2o, GTSAM and possibly other available factor graph libraries. Summarize main similarities and differences. 
3. Choose a tracking problem for in-depth study. Develop a solution by means of factor graph techniques. 
4. Compare the performance of your solution with standard techniques.  
5. Write report.

## Proposed Tasks for the master thesis

The project work aims to be extended into a master thesis for the spring of 2021. Several directions are possible depending on the interest of the student. 

* It has been claimed that the exact EHM technique for marginal association probabilities is an improved version of the junction tree method, which is the general brute force technique for exact inference in graphical models. Investigate this claim. 
* Can factor graph libraries and graphical models in general be used to solve data association in multi-scan tracking problems? 
* Implementation on real data. 
* Combining factor graph solutions to both smoothing and data association. 
* Combining factor graph solutions to tracking and SLAM.
* Multi-hypothesis data association in SLAM.

## Contact
Supervisors [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo) and
[Øystein Kaarstad Helgesen](https://www.ntnu.edu/employees/oystein.k.helgesen) 

## References

* Grini, S. (2019): “[Object Detection in Maritime Environments: Systematic Training and Testing of Deep Learning-based Detection Methods for Vessels in Camera Images](http://folk.ntnu.no/edmundfo/msc2019-2020/grini_simen_msc_reduced.pdf)”, MSc thesis, NTNU. 

[Autosea project]: https://www.ntnu.edu/autosea
