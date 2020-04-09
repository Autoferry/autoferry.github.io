---
layout: post
title: Visual SLAM and localization for autonomous ferry
category: NO
---
## Background
The navigation of the autonomous ferry Milliampere is currently based on GNSS. For improved robustness, especially in docking scenarios,
this system should be complemented by navigation done purely by means of onboard sensors. 
The ferry is currently equipped with lidar, radar, optical cameras and infrared cameras. 

The sensors can be used as a data source for localization relative to known landmarks or an established map, or as a data source for simultaneous localization and mapping (SLAM). 
Visual SLAM is currently a very hot research topic, but there are very few demonstrations of SLAM in maritime harbor environments in the research literature. 
A much less explored topic is SLAM and localization by means of infrared cameras. 

|<img src="{{site.url}}/assets/eskilfergecropped.jpg" width="570"> | 
| The sensor rig that was installed on top of Milliampere during April 2019. | 

## Scope for the 5th year project

The autonomous ferry Milliampere is equipped with 360 degree coverage of both optical and infrared cameras. The scope of the 5th year project is to explore the possibilities for using these cameras for localization purposes. Based on a literature survey on state-of-the art in Visual SLAM and localization, and somel recent MSc theses on SLAM at ITK, the candidate should early in the semester make plans for an interesting comparison of different techniques. Possibilities include:
- Optical SLAM (e.g., ORB-SLAM) versus optical localization. 
- Optical SLAM versus infrared SLAM. 
- Infrared SLAM versus infrared localization. 
- Different degrees of fusion with the inertial navigation system (INS) and other exteroceptive sensors such as lidar.

The 5th year project should also include data collection experiments early in the semester. These data are likely to be the main data set during most of the work with the MSc project as well. 

|<img src="{{site.url}}/assets/ir-eskil.jpg" width="570"> | 
| Based on preliminary data it seems likely that IR-based SLAM should be possible in Trondheim's harbor areas. | 

## Scope for the master thesis

Given a successful 5th year project, the main goal for the MSc project will be to make the methods sufficiently robust and fast to be used as part of closed-loop docking experiments. Key elements in this work are expected to be:
- Integration with the INS and its error-state Kalman filter. Should the outputs of localization and INS be fused in a loosely couple architectured, or should IMU data be used as input to SLAM in a tightly coupled architecture?
- Data association: How do we ensure that the right landmarks are being matched?
- Real-time programming: How to make sure that the program never crashes or takes too long time?

## Contact
For more information, contact main supervisor [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo)

## References

* Shin, Y.-S. and Kim, A. (2019): “[Sparse Depth Enhanced Direct Thermal-infrared SLAM Beyond the Visible Spectrum](https://arxiv.org/pdf/1902.10892.pdf)”, arXiv e-print
* Ødven, M. (2019): “[Lidar-based SLAM for Autonomous Ferry](http://folk.ntnu.no/edmundfo/msc2019-2020/MasterFinalReducedMarius.pdf)”, MSc thesis, NTNU
* Fan, Z. (2016): "[Brief Review on Visual SLAM: A Historical Perspective](https://fzheng.me/2016/05/30/slam-review/)".