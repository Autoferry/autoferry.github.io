---
layout: post
title: Integrated detection and tracking
category: SF
---
## Background

An automated situational awareness systems for autonomous vehicles must detect and track nearby moving objects to avoid collisions. 
The majority of tracking methods, whether optical or radar-based, are based on the philosophy of tracking-by-detection, where the tracking method is fed detections from a stream of images or sensor scans. Typically, these detections of a single-shot nature: Every image in the stream is processed independently of the other images. 

Clearly, this is in principle suboptimal. By processing several images simultaneously, one may have sufficient information available to discover moving objects that would be impossible to detect from a single images. 
One underlying principle that can be used to track a moving object without single-shot detections is that of track-before-detect: We integrate the data along potential trajectories in time and space, and identify those trajectories that actually appear to have been followed by moving objects. 
This principle is directly implemented in the Hough transform.

|<img src="{{site.url}}/assets/hough-transform.png" width="700"> | 
| Example of Hough transform on simulated data. On the left (x=time, y=position) a target is moving upwards from lower left corner. On the right this corresponds to a unique maximum in the space of initial position and path angle. |

This raises the question of whether there exist other fundamental principles that can be used to develop multiscan detection techniques. Furthermore, the nature of multiscan detection techniques will depend on the type of sensors. 
Video streams from optical cameras are rich on information which no doubt can support multi-scan detection, but it is hard to pin down the exact principles one should use, as deep learning no doubt will play a fundamental role. 
Video streams from infrared data will often have a lower signal-to-noise ratio, and richness of information is largely replaced by the monotonous gradient between and hot and cold. Tracking with infrared cameras has been an important motivation for multi-scan detection methods.
In typical lidar data there is no intensity values to integrate along the potential paths. One can, however, count the number of hits along different paths. 
In radar data, raw signal analysis can sometimes be used for this kind of analysis, both often the only data made available to the user is thresholded data. 



## Scope

The goal of the 5th year project is to make a survey over techniques that exist for multi-scan detection. 
The goal of the master thesis is to implement and analyse one such technique of relevance to the sensors onboard milliAmpere 1 and 2. 

## Proposed Tasks for the 5th year project

The 5th year project should aim to answer the following research questions, as systematically as possible:

1. Are there examples of multiscan detection methods developed for optical, infrared, lidar and radar data? Are the methods tested on simulations or on real data? What kind of domains are the data from?
2. What are the core principles underlying the methods? Are they model-based on data-driven through machine learning? 
3. Can anything be said about performance gains over single-shot detection methods?
4. Can anything be said about computational complexity?
5. Are there any weaknesses in robustness or reliability?


## Proposed Tasks for the master thesis

In the master thesis the goal is to implement a multiscan detection method on data from milliAmpere 1 or milliAmpere 2.

* Choose one of the approaches from the 5th year project and justify the choice.
* Implement the approach.  
* Evaluate performance using several measures. Precision-recall or receiver-operating-characteristic should be among these. 


## Autoferry

The candidate will be associated with the [AUTOFERRY] project, which is about the concept of small autonomous passenger ferries in urban areas as a more flexible and environmentally-friendly alternative to bridges or manned ferries. 
The candidate will also collaborate with researchers in [SFI AUTOSHIP], which is an 8-years research-based innovation centre that will contribute to Norwegian players taking a leading role in the development of autonomous ships for safe and sustainable operations.


## Contact
Supervisor: [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo).
## Prerequisites

The candidate will benefit from having taken the courses [TTK4255 Robotic Vision] and [TTK4250 Sensor Fusion]. Both [TTT4275 Estimation, Detection and Classification] and [TDT4265 - Computer Vision and Deep Learning] will also be very useful. 


## References

* Brekke, E. et al. (2022): [“milliAmpere: An Autonomous Ferry Prototype”](https://folk.ntnu.no/edmundfo/papers/icmass-milliampere-2022.pdf), To appear in Proc. ICMASS. 

* Carlson, B. D. et al. (1994): [“Search radar detection and track with the Hough transform. I. system concept”](https://ieeexplore.ieee.org/document/250410), IEEE Transactions on Aerospace and Electronic Systems, vol 30 no 1.


|[<img src="https://img.youtube.com/vi/Ry3-yxVaDuE/0.jpg" width="450">](https://www.youtube.com/watch?v=Ry3-yxVaDuE) |
|<span style="color:#959595">Link to video of milliAmpere autonomy demonstration. </span> |

[TTK4255 Robotic Vision]: https://www.ntnu.edu/studies/courses/TTK4255#tab=omEmnet
[(Vasstein 2021)]: https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2781031
[Autoferry Gemini]: https://iopscience.iop.org/article/10.1088/1757-899X/929/1/012032
[TTT4275 Estimation, Detection and Classification]: https://www.ntnu.edu/studies/courses/TTT4275#tab=omEmnet
[TTK4250 Sensor Fusion]: https://www.ntnu.no/studier/emner/TTK4250#tab=omEmnet
[TDT4265 - Computer Vision and Deep Learning]: https://www.ntnu.no/studier/emner/TDT4265#tab=omEmnet
[AUTOFERRY]: https://www.ntnu.edu/autoferry
[SFI AUTOSHIP]: https://www.ntnu.edu/sfi-autoship