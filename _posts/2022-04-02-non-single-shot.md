---
layout: post
title: Integrated detection and tracking
category: SF
---
## Background

An automated situational awareness systems for autonomous vehicles must detect and track near by moving objects to avoid collisions. 
The majority of tracking methods, whether optical or radar-based, are based on the philosophy of tracking-by-detection, where the tracking method is fed detections from a stream of images or sensor scans. Typically, these detections of a single-shot nature: Every image in the stream is processed independently of the other images. 

Clearly, this is in principle suboptimal. By processing several images simultaneously, one may have sufficient information available to discover moving objects that would be impossible to detect with any reasonable confidence from a single image. 
One underlying principle that can be used to track a moving object without single-shot detections is that of track-before-detect: We integrate the data along potential trajectories in time and space, and identify those trajectories that actually appear to have been followed by moving objects. 
This principle is directly implemented in the Hough transform.

This raises the question of whether there exist other fundamental principles that can be used to develop multi-scan detection techniques. Furthermore, nature of multi-scan detection techniques will depend on the type of sensors. 
Video streams from optical cameras are rich on information which no doubt can support multi-scan detection, but it is hard to pin down the exact principles one should use, as deep learning no doubt will play a fundamental role. 
Video streams from infrared data will often have a lower signal-to-noise ratio, and richness of information is largely replaced by the monotonous gradient between and hot and cold. Tracking with infrared cameras has been an important motivation for multi-scan detection methods.
In typical lidar data there is no intensity values to integrate along the potential paths. One can, however, count the number of hits along different paths. 
In radar data, raw signal analysis can sometimes be used for this kind of analysis, both often the only data made available to the user is thresholded data. 



## Scope

The goal of the 5th year project is to make a survey over techniques that exist for multi-scan detection. 
The goal of the master thesis is to implement and analyse one such technique of relevance to the sensors onboard milliAmpere 1 and 2. 

## Proposed Tasks for the 5th year project

The 5th year project involves the following tasks

1. Bla
2. Bla 
3. Bla 
4. Bla 
5. Bla 
6. Bla

## Proposed Tasks for the master thesis

Several variations of the subsequent master thesis are possible. 

* Bla 
* Bla 
* Bla 


## Contact
Supervisor: [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo).
## Prerequisites

The candidate should have taken the course [TTK4255 Robotic Vision] or similar before beginning this 5th year project. 

## References

* Brekke, E. et al. (2022): [“milliAmpere: An Autonomous Ferry Prototype”](https://folk.ntnu.no/edmundfo/papers/icmass-milliampere-2022.pdf), To appear in Proc. ICMASS. 



|[<img src="https://img.youtube.com/vi/Ry3-yxVaDuE/0.jpg" width="450">](https://www.youtube.com/watch?v=Ry3-yxVaDuE) |
|<span style="color:#959595">Link to video of milliAmpere autonomy demonstration. </span> |

[TTK4255 Robotic Vision]: https://www.ntnu.edu/studies/courses/TTK4255#tab=omEmnet
[(Vasstein 2021)]: https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2781031
[Autoferry Gemini]: https://iopscience.iop.org/article/10.1088/1757-899X/929/1/012032
[TTT4275 Estimation, Detection and Classification]: https://www.ntnu.edu/studies/courses/TTT4275#tab=omEmnet