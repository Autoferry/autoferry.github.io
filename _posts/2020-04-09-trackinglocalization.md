---
layout: post
title: Joint tracking and localization
category: SF
---
## Background
The autonomous ferry prototype MilliAmpere is equipped with GNSS localization and several exteroceptive sensors (radar, lidar, optical cameras and infrared cameras). In addition, there are plans to furnish its environment with additional shore-based sensors to enable monitoring from other angles. In fact, a surveillance station consisting of a radar and an optical camera has already been installed at Brattøra. Data from this station have been analyzed in a couple of previous MSc projects. 

Shore-based sensors can serve three purposes. First, they can be used for continuous monitoring of the environment to learn typical behaviour patterns of traffic in the area. Second, they can be used to discover and monitor threats in areas that the ferry itself cannot see, because of occlusions or blind zones. Third, they can be used to keep track of the location of the ferry itself, in case its GNSS localization should fail. 



## Scope
The goal of this combined specalization and Master's project is to make progress towards the realization of a joint tracking and localization system for MilliAmpere and its successor MilliAmpere2.


## Proposed Tasks for the 5th year project

1. Choice of sensor architecture. Make a judgement of strengths and weaknesses of different configurations.
2. Installation of sensors. 
3. Synchronization and calibration. 
4. Experiment. Record data with MillliAmpere in the canal, and with/without other vessels in the vicinity. 
5. Detection and object recognition. Convolutional neural networks may be combined with standard thresholding and segmentation techniques. 
6. Multi-target tracking of MilliAmpere and other vessels. Fusion with GNSS data with and without RTK.

This is intended to be a project with a strong hands-on flavour, but for a more theoretically inclined student it is also possible to solve the entire project using the MilliAmpere digital twin. 

## Proposed Tasks for the master thesis

The project work aims to be extended into a master thesis for the spring of 2021. Several directions are possible depending on the interest of the student. 

*  Fusion with ongoing work on simultaneous localization and mapping (SLAM). 
* Identify and put in place additional infrastructure needed for real-time implementation. Make real-time implementation. 
* Solving the merged measurement problem: When other boats come very close to the ferry, the radar is likely to return a single merged measurements, and this can confuse the tracking system. 
* Dealing with navigation uncertainty in multi-target tracking. 
* Include a shore-mounted event camera in the sensor configuration. 

## Contact
For more information, contact main supervisor [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo)

## References

* Helgesen, Ø., et al. (2020): “[Low Altitude Georeferencing for Imaging Sensors in Maritime Tracking](http://folk.ntnu.no/edmundfo/msc2019-2020/Georeferencing_paper)”, Accepted for publication at the IFAC World Congress, Berlin, Germany,
* Helgesen, Ø., et al. (2019): “[Sensor Combinations in Heterogeneous Multi-sensor Fusion for Maritime Target Tracking](https://ieeexplore.ieee.org/document/9011297)”, Proceedings of FUSION, Ottawa, Canada.
* Skjellaug, E. (2019): “[Feature-based laser odometry for autonomous ferry](http://folk.ntnu.no/edmundfo/msc2019-2020/Skjellaug-laser-odo.pdf)”, Specialization project, NTNU. 
* Ødven, M. (2018): “[Lidar-based SLAM for Autonomous Ferry](http://folk.ntnu.no/edmundfo/msc2019-2020/MasterFinalReducedMarius.pdf)”, MSc thesis, NTNU
* Pedersen, J. (2018): “[Harbor Surveillance with a K-best, Track Terminating, Hypothesis-Oriented MHT](http://folk.ntnu.no/edmundfo/msc2019-2020/masteroppgaveJesperPedersenReduced.pdf)”, MSc thesis, NTNU
