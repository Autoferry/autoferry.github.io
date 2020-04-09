---
layout: post
title: Joint tracking and localization
category: SF
---
## Background
The autonomous ferry prototype MilliAmpere is equipped with GNSS localization and several exteroceptive sensors (radar, lidar, optical cameras and infrared cameras). In addition, there are plans to furnish its environment with additional shore-based sensors to enable monitoring from other angles. In fact, a surveillance station consisting of a radar and an optical camera has already been installed at Brattøra. Data from this station have been analyzed in a couple of previous MSc projects. 

Shore-based sensors can serve three purposes. First, they can be used for continuous monitoring of the environment to learn typical behaviour patterns of traffic in the area. Second, they can be used to discover and monitor threats in areas that the ferry itself cannot see, because of occlusions or blind zones. Third, they can be used to keep track of the location of the ferry itself, in case its GNSS localization should fail. 



## Scope
The goal of this combined specalization and Master's project is to make progress towards the realization of such a joint tracking and localization system. 


## Proposed Tasks for the 5th year project

1. Conduct a literature survey on the state-of-the-art in SLAM using lidars and other range finders.
2. Conduct a literature survey on methods for localization relative to known landmarks and maps. 
3. Implement a chosen SLAM method on data recorded using the lidar onboard Milliampere. 
4. Implement a chosen localization method on data recorded using the lidar onboard Milliampere. 
5. Compare the performance of the two approaches in the project report. 

## Proposed Tasks for the master thesis

The project work aims to be extended into a master thesis for the spring of 2018. Key challenges that should be addressed are expected to be data association, integration with inertial navigation system and real-time implementation. 

## Contact
For more information, contact main supervisor [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo)

## References

* Ødven, M. (2019): “[Lidar-based SLAM for Autonomous Ferry](http://folk.ntnu.no/edmundfo/msc2019-2020/MasterFinalReducedMarius.pdf)”, MSc thesis, NTNU
* Dalhaug, N. (2019): “Lidar-based localization for autonomous ferry”, MSc thesis, NTNU, in writing. 