---
layout: post
title: 360 degrees view for the operator of milliAmpere 2
category: Camera Object Tracking
---
## Background

When tracking multiple objects in using some sensor one often uses a object detector to detect a point measurement or bounding box before one uses this in a joint integrated probabilistic data association tracker or multiple hypothesis tracker. For a camera, however, this disregards much of the available information of the object present in the image patch inside the bounding box. This is true both for data association and and localization.

Computer vision has another widely used technique known as Lucas-Kanade algorithm that track image patches and can estimate the relative 3D pose. 

 CHANGE: 
 
 < -----------
|[<img src="https://img.youtube.com/vi/uxvKOmjzXvU/0.jpg" width="450">](https://www.youtube.com/watch?v=uxvKOmjzXvU) |
|<span style="color:#959595">360 Degree Camera on a Mercedes. </span> |

## Scope

The goal of this project is to develop a system that enables the operator of milliAmpere 2 to obtain 360 degree vision around milliAmpere 2, to improve the operator's situational awareness during remote control. 

## Proposed Tasks for the 5th year project

In the 5th year project the goal is to develop a system for image stitching, fusion and transformation that can be used to achieve the 360 degree vision. 

1. Calibrate cameras.
2. Chose and implement a solution for synchronsiation. Should all cameras be triggered simultaneously, or do you want to fuse images slightly apart in time?
3. Record test data.
4. Derive correct transformations to obtain a bird eye view.
5. Implement a method for fusing the images. 
6. Assess the suitability of the implementation for remote control. 

|<img src="{{site.url}}/assets/ma2.jpg" width="650" > | 
| <span style="color:#959595">milliAmpere 2 pictured 15th of June 2021. The cabinets for cameras can be seen. </span> | 

## Proposed Tasks for the master thesis

Several variations of the subsequent master thesis are possible. All of these are focused on making the image stitching system into a more elaborate system for situational awareness. Possible tasks may include some of the following:

* Make a real-time fused video stream onboard milliAmpere 2.
* Make a complete system for transferring the fused video stream to the shore control centre at Nyhavna. 
* Integrate sensor fusion and automated situational awareness from the autonomy system into the fused video stream. 
* Would it be useful to install additional downwards tilted cameras on milliAmpere 2 or stationary surroundings to further improve the operator's situational awareness?

|<img src="{{site.url}}/assets/scc.png" width="650" > | 
| <span style="color:#959595">The shore control centre at Nyhavna where a remote operator may be located.</span> | 

## Autoferry

The candidate will be associated with the [AUTOFERRY] project, which is about the concept of small autonomous passenger ferries in urban areas as a more flexible and environmentally-friendly alternative to bridges or manned ferries. 
The candidate will also collaborate with researchers in [SFI AUTOSHIP], which is an 8-years research-based innovation centre that will contribute to Norwegian players taking a leading role in the development of autonomous ships for safe and sustainable operations.

## Contact
Supervisor: [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo).
## Prerequisites

The candidate should have taken the course [TTK4255 Robotic Vision] or similar before beginning this 5th year project. 

## References

* Brekke, E. et al. (2022): [“milliAmpere: An Autonomous Ferry Prototype”](https://folk.ntnu.no/edmundfo/papers/icmass-milliampere-2022.pdf), To appear in Proc. ICMASS. 
* Simon Baker and Iain Matthews. Lucas-kanade 20 years on: A unifying framework. Int. J. Computer Vision, 56(3):221–255, 2004.


|[<img src="https://img.youtube.com/vi/Ry3-yxVaDuE/0.jpg" width="450">](https://www.youtube.com/watch?v=Ry3-yxVaDuE) |
|<span style="color:#959595">Link to video of milliAmpere autonomy demonstration. </span> |

[TTK4255 Robotic Vision]: https://www.ntnu.edu/studies/courses/TTK4255#tab=omEmnet
[(Vasstein 2021)]: https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2781031
[Autoferry Gemini]: https://iopscience.iop.org/article/10.1088/1757-899X/929/1/012032
[TTT4275 Estimation, Detection and Classification]: https://www.ntnu.edu/studies/courses/TTT4275#tab=omEmnet
[AUTOFERRY]: https://www.ntnu.edu/autoferry
[SFI AUTOSHIP]: https://www.ntnu.edu/sfi-autoship
----------------------------- >
