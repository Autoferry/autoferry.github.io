---
layout: post
title: Transformers
category: SF
---
## Background

One of the most important research questions in sensor fusion in the 2020s is whether one should use model-based or model-free methods. The success of deep learning in several vision related tasks have led to a strong momentum for model-free methods. Generally, model-based methods appear to work best for problems where simple models are available, where geometry plays a central role and where accuracy is important. On the other hand, deep learning tend to outperform model-based methods for problems that are so complex that adequate models cannot really be specified, and for problems where classification plays a central role. 

Multi-target tracking with sensors such as radar can be described by relatively simply models. These models describe both the kinematics involved in the problem, and the premises for data association. When these models are used in tracking algorithms, a need for enumerating data association hypotheses arises. The complexity of this is exponential, and drastic approximations are inevitable. Therefore, it has recently been argued that deep learning also may outperform model-based methods for such problems. 

The architecture used for deep learning as a solution for data association is that of the transformer neural network. Originally proposed as a solution for speech interpretation, the transformer aims to learn relationships between sequences. Such a pair of sequences could be the sequence of measurements and the sequence of target states (or more generally, descriptors or sufficient statistics for the sets of targets during a sequence of time steps). 

The most interesting potential for transformers in multi-target tracking is not necessarily as a solution to the standard model of multi-target tracking. Several non-standard tracking problems, such as extended object tracking, are more complex, so that exact solutions are entirely out of the question.  For the autonomous ferries milliAmpere 1 and 2, extended object tracking is potentially a key enabler, as these ferries often will have navigate very close to other vessels of various sizes.


## Scope
The objective of this project is to investigate the potential of deep learning for multi-target tracking using lidar or radar.


## Proposed Tasks for the 5th year project

A starting point for the 5th year project is the comparisons between the MultiTarget Tracking Transformer (MT3) and the Poisson Multi-Bernoulli Mixture Filter reported in Pinto 2021 and Pinto 2022. The goal is to assess whether MT3 is a viable alternative to model-based methods for tracking problems in maritime situational awareness. 

1. Summarize basic theory of multi-target tracking and transformer networks.
2. Design suitable test scenarios.
3. Open source implementations of both PMBM and MT3 exist. Use these on the simulated scenarios. Perform additional training of the transformer network by means of simulated data if necessary.
4. Evaluate performance, by measures such as the GOSPA metrics, run-time and statistical consistency.  
5. Write report.

## Proposed Tasks for the master thesis

The project work aims to be extended into a master thesis for the spring of 2021. In the master thesis the goal is to look at one of the non-standard tracking problems, such as extended object tracking. Since this largely is a proof-of-concept project, it may be most interesting to tailor the work for lidar or radar, so that large amounts of training data easily can be simulated. Tasks:

* yyy
* yyy
* yyy

## Autoferry

The candidate will be associated with the [AUTOFERRY] project, which is about the concept of small autonomous passenger ferries in urban areas as a more flexible and environmentally-friendly alternative to bridges or manned ferries. In 2017, the autonomous ferry prototype milliAmpere was launched. In 2021 it was accompanied by the larger and more advanced autonomous ferry milliAmpere 2.

## Contact
Supervisors [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo) and 
[Øystein K. Helgesen](https://www.ntnu.no/ansatte/oystein.k.helgesen)

## Prerequisites

No particular courses are needed, but [TTK4250 Sensor fusion] and [TDT4265 - Computer Vision and Deep Learning] will together give an ideal background for this project.

## References

* Helgesen, Ø. K. and Brekke, E. (2022): “[Bearings-only tracking using factor graphs](https://folk.ntnu.no/edmundfo/fusion2022preprints/HelgesenBrekkeBearingFactor.pdf)”, Submitted to Fusion 2022. 
* Helgesen, Ø. K., Brekke, E., Stahl, A. and Engelhardtsen, Ø. (2020): “[Low Altitude Georeferencing for Imaging Sensors in Maritime Tracking](https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2758973)”, Proceedings of IFAC World Congress. 
* Kummerle et al. (2011): “[g2o: A General Framework for Graph Optimization](https://www.cct.lsu.edu/~kzhang/papers/g2o.pdf)”, Proceedings of ICRA 2011, Shanghai, China.
* Dellaert, F. (2012): “[Factor Graphs and GTSAM: A Hands-on Introduction](https://borg.cc.gatech.edu/sites/edu.borg/files/downloads/gtsam.pdf)”, Technical report, The Borg Lab, GeorgiaTech.


|[<img src="https://img.youtube.com/vi/Ry3-yxVaDuE/0.jpg" width="450">](https://www.youtube.com/watch?v=Ry3-yxVaDuE) |
|<span style="color:#959595">Link to video of milliAmpere autonomy demonstration. </span> |

[TTK4250 Sensor fusion]: http://folk.ntnu.no/edmundfo/msc2019-2020/sf13chapters.pdf
[Helgesen et al. 2020]: https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2758973
[Helgesen and Brekke 2022]: https://folk.ntnu.no/edmundfo/fusion2022preprints/HelgesenBrekkeBearingFactor.pdf
[TTK4255 Robotic Vision]: https://www.ntnu.edu/studies/courses/TTK4255#tab=omEmnet
[(Helgesen and Brekke 2022)]: https://folk.ntnu.no/edmundfo/fusion2022preprints/HelgesenBrekkeBearingFactor.pdf
[AUTOFERRY]: https://www.ntnu.edu/autoferry
[TDT4265 - Computer Vision and Deep Learning]: https://www.ntnu.no/studier/emner/TDT4265#tab=omEmnet