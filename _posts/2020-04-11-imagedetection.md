---
layout: post
title: Improved ship detection in camera video
category: SF
---
## Background
The first step in the situational awareness pipeline of any autonomous vehicle is to detect other vehicles and obstacles. This can be done by means of transponder systems (e.g. AIS), active exteroceptive sensors (radar, lidar) or passive exteroceptive sensors (optical and infrared cameras). Typically, a detection procedure processes every scan or image from the sensors independently, and feeds the extracted blobs to a tracking method, which declares a threat if it is able to establish a track on consecutive detections. 

For active sensors, relatively straightforward thresholding and segmentation techniques are typically used for detection. For passive sensors, especially for optical cameras, more advanced object recognition techniques are generally preferred. Convolutional neural networks (CNNs) have emerged as the undisputed benchmark leader in recent years. A handful of MSc students have worked on CNNs for ship detection in optical and infrared images in connection with the [Autosea project], see for example ([Grini 2019]).  

|<img src="{{site.url}}/assets/revolt-sequence.png" width="700"> | 
| Can you spot the small boat ReVolt in the third IR image? | 

No detector is perfect. CNNs come with their own strengths and weaknesses. They can be trained to detect objects that would be very difficult to describe in more explicit terms, but are ill equipped to detect objects that differ too much from the training data. Their black-box nature make it difficult to analyze or predict their behaviour. Standard CNNs are, in common with other methods that work on single images, unable to exploit dynamic information that only can extracted from a sequence of images. More specifically, we have observed false alarms caused by buildings mistaken for ships, and misdetections because a boat was difficult to distinguish from the background. The latter is especially a problem in infrared images. 


Several approaches may be taken in the pursuit of more reliable detectors. Some of these are outlined below. 

First, it is possible to design detectors that work on the video stream, instead of individual images. Even if the object in question, e.g., a kayak, is clearly visible in any individual images, spatio-temporal processing of several images simultaneously can reveal the presence of the object. In the tracking community, this is known as track-before-detect (TBD). Work in this direction may follow along the lines of TBD, it may employ neural networks working directly on the video stream, or it may analyze the spatio-temporal variability of the data using multivariate regression techniques. 

Second, a better basis for detection decisions can be obtained by fusion of different sensors before detection. For example, the data from a camera and a lidar may be combined into an extrapolated point cloud that is more dense than the original lidar point cloud, and which also maintains the color information from the camera data. 

Third, standard CNN methods (Faster-RCNN, YOLO, SSD) only provide bounding boxes, and do not perform any segmentation. Better performance can perhaps be achieved by integrating the segmentation process into the detection procedure. This can be done in a variety of ways (Autoencoders, [Mask RCNN]). 


|<img src="{{site.url}}/assets/eskilfergecropped.jpg" width="650" > | 
| milliAmpere with its radar-infrared-optical sensor rig. | 

## Scope
The main goal of this project is to investigate the potential of alternatives to bounding-box CNN approaches for detection in optical and infrared images, to be used in situational awareness for the autonomous ferry prototype milliAmpere. This can be a project for a single student or a group of students. Several data sets are available, both include infrared images, optical images, infrared video, and joint infrared, lidar and radar video. While all these data sets can be used for testing, there may be a need for recording additional data sets depending on the amount of training data that is needed.  

## Proposed Tasks for the 5th year project

The details of the specialization project will depend on the interest of the student, but the following elements should in any case be part of it. 

1. Fundamental theory and algorithm description of the chosen detection method. 
2. Data consolidation: What are the available data sets, and which data sets do you use for training, validation and testing?
3. Implementation.
4. Performance evaluation. Precision and recall, or equivalent measures, must be part of this analysis. 

## Proposed Tasks for the master thesis

In the master thesis, the goal will be to make the developments from the 5th year project ready for integration in the sensor fusion systems of milliAmpere and milliAmpere2. This will include tasks such as the following. 

* Evaluation of detector performance on data recorded using the onboard sensors of the autonomous ferry. 
* Algorithms for segmentation and measurement extraction if this has not already been solved as part of the 5th year project. 
* Evaluation of mean square error statistics (i.e., measurement covariance) for the extraction algorithms. 
* Identification of any other weaknesses that could make the proposed detector unreliable. This may include poor performance under certain environmental conditions, erroneous performance when water drops rest on the lens, or significant violations of Markov property. Suggest and implement mitigation measures. 
* Real-time implementation. GPU implementation is likely to be necessary. 

## Contact
Supervisors [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo) and
[Øystein Kaarstad Helgesen](https://www.ntnu.edu/employees/oystein.k.helgesen) 

## References

* Grini, S. (2019): “[Object Detection in Maritime Environments: Systematic Training and Testing of Deep Learning-based Detection Methods for Vessels in Camera Images](http://folk.ntnu.no/edmundfo/msc2019-2020/grini_simen_msc_reduced.pdf)”, MSc thesis, NTNU. 
* Olsen, R. (2019): “[Sensor fusion of radar data with deep learning based detection and tracking of ships in camera images](https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2625695)”, MSc thesis, NTNU. 
* He et al. (2017): “[Mask R-CNN](https://ieeexplore.ieee.org/document/8237584)”, Proceedings of ICCV, Venice, Italy. 



|[<img src="https://img.youtube.com/vi/FuWedx0oLX4/0.jpg" width="450">](https://www.youtube.com/watch?v=FuWedx0oLX4) |
|milliAmpere is fitted with 5G technology from Telia. The above image links to a promo video from Telia.|


[Autosea project]: https://www.ntnu.edu/autosea
[Grini 2019]: http://folk.ntnu.no/edmundfo/msc2019-2020/grini_simen_msc_reduced.pdf
 [Mask RCNN]: https://ieeexplore.ieee.org/document/8237584
