---
layout: post
title: Optical flow for tracking maritime objects
category: SF
---
## Background

When tracking multiple objects using some sensor one often uses a object detector on each sensor frame to detect point measurements or bounding boxes before feeding this to for instance a joint integrated probabilistic data association (JIPDA) (Musicki & Evans, 2004) tracker or multiple hypothesis tracker (MHT) (Reid, 1979). For a camera, however, this disregards much of the available information of the object present in the image patch inside the bounding box. This is true both for data association and and localization. Bounding boxes typically vary by some pixels in size and location relative to the given object over time.

Computer vision has another widely used technique known as optical flow. Optical flow can, according to Wikipedia, be defined as the distribution of apparent velocities of movement of brightness pattern in an image. One popular algorithm for this is the Lucas-Kanade algorithm that track parameterized image patches and can estimate the relative 3D pose (up to scale) (Baker & Matthews, 2004), although dense optical flow can also be performed, e.g. per pixel. However, first detecting objects using optical flow can fail if the camera is moving to much or the object to detect is to detect os more or less at standstill with respect to the background. It also does not give information on the type of object detected.

## Scope

The goal of this project is first too look at the relative performance of single frame detectors used in a tracker compared to an optical flow tracker. 
Secondly it is then to see wheter one can combine them to ideally get the best of both worlds and with this improve tracking performance.

The project will mainly use real data recorded in the canal or on the Trondheims fjord from the milliAmpere1&2 platforms (See below for a video of milliAmpere1) or our simulator ([Autoferry Gemini]), but can also preferably test the implementation on standard benhmark data such as [The Multiple Object Tracking Benchmark](https://motchallenge.net).

|<img src="{{site.url}}/assets/ma2.jpg" width="650" > | 
| <span style="color:#959595">milliAmpere 2 pictured 15th of June 2021. </span> | 

## Proposed Tasks for the 5th year project

The 5th year project goal is to evaluate optical flow tracking performance compared to a track by detect tracker such as JIPDA or MHT on multiple data sets.

1. Do a litterature review on optical flow tracking methods.
2. Implement and test one or more of the optical flow trackers (such as Lukas-Kanade) to track a given boat.
3. Implement automatic track initialization.
4. Compare the perfomance, in terms of correctly detecting objects and their localization error, to one of our detection and tracking pipelines on multiple data sets.

## Proposed Tasks for the master thesis

The aim of the master thesis is to combine the single shot detector with the optical flow tracker in some way, and then use this in a JIPDA or MHT for tracking multiple marine objects. 

Additionally one can try to make this work across all the cameras on the sensor platform, and test the implementation on data where the objects pass from one camera to another.

* Read up on multiple target tracking.
* Implement a optical flow and single shot combination.
* (Optionally) Handle object passing from one camera to another.
* Evaluate detection statistics and tracker performance.
* (Optionally) Make the implementation operate in real time and do a live demonstration.

|<img src="{{site.url}}/assets/scc.png" width="650" > | 
| <span style="color:#959595">The shore control centre at Nyhavna where a remote operator may be located.</span> | 

## Autoferry

The candidate will be associated with the [AUTOFERRY] project, which is about the concept of small autonomous passenger ferries in urban areas as a more flexible and environmentally-friendly alternative to bridges or manned ferries. 
The candidate will also collaborate with researchers in [SFI AUTOSHIP], which is an 8-years research-based innovation centre that will contribute to Norwegian players taking a leading role in the development of autonomous ships for safe and sustainable operations.

## Contact
Supervisor: [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo), [Lars-Christian N. Tokle](https://www.ntnu.no/ansatte/lars-christian.n.tokle).
## Prerequisites

The candidate should have taken at least one of the courses [TTK4250 Sensor Fusion] or [TTK4255 Robotic Vision], or equivalent, before beginning this 5th year project. 

## References

* Reid, D. (1979). An algorithm for tracking multiple targets. IEEE Transactions on Automatic Control, 24 (6), 843–854. https://doi.org/10.1109/TAC.1979.1102177
* Musicki, D. and Evans, R. (2004). Joint integrated probabilistic data association: JIPDA. IEEE Transactions on Aerospace and Electronic Systems, 40(3), 1093–1099. https://doi.org/10.1109/TAES.2004.1337482
* Brekke, E. et al. (2022): [“milliAmpere: An Autonomous Ferry Prototype”](https://folk.ntnu.no/edmundfo/papers/icmass-milliampere-2022.pdf), To appear in Proc. ICMASS. 
* Simon Baker and Iain Matthews (2004): Lucas-kanade 20 years on: A unifying framework. Int. J. Computer Vision, 56(3):221–255.


|[<img src="https://img.youtube.com/vi/Ry3-yxVaDuE/0.jpg" width="450">](https://www.youtube.com/watch?v=Ry3-yxVaDuE) |

|<span style="color:#959595">Link to video of milliAmpere autonomy demonstration. </span> |

[TTK4255 Robotic Vision]: https://www.ntnu.edu/studies/courses/TTK4255#tab=omEmnet
[(Vasstein 2021)]: https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2781031
[Autoferry Gemini]: https://iopscience.iop.org/article/10.1088/1757-899X/929/1/012032
[TTK4250 Sensor Fusion]: https://www.ntnu.edu/studies/courses/TTT4250#tab=omEmnet
[AUTOFERRY]: https://www.ntnu.edu/autoferry
[SFI AUTOSHIP]: https://www.ntnu.edu/sfi-autoship
