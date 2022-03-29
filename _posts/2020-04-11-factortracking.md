---
layout: post
title: Bearings-only smoothing by means of factor graphs
category: SF
---
## Background
During the last decade, factor graph optimization has become the undisputed gold standard in simultaneous localization and mapping (SLAM). The key idea is that all measurements can be modeled as probabilistic constraints on the trajectory of the vehicle. The entire trajectory can then be estimated by optimization over the joint collection of constraints. Thus, modern SLAM methods can be said to do smoothing rather than filtering, which was the dominating approach in the early days of SLAM. 

Another problem in sensor fusion, which has challenged researchers for more than 40 years, is bearing-only tracking. 
During the cold war, there was a strong focus on tracking of submarines using passive acoustic measurements. 
In more recent years, the increased focus on camera-based tracking for mobile robotics is also leading to a need for reliable solutions to bearing-only tracking. There are two fundamental challenges in bearing-only tracking. 
First, the measurement model is fundamentally nonlinear, as one only has bearing measurements and no range measurements. The absence of range information means that the measurements cannot simply be transformed into Cartesian coordinates. 
Second, the problem has limited observability. It is only possible to estimate the motion of the target if the ownship, on which the sensor is mounted, if the ownship out-manoeuvers the target (or if one can obtained information about the target's acceleration by other means, but that is typically not the case.)


All the well-known solutions to bearing-only tracking are based on filtering. Three strategies have been pursued:

1. Use an extended Kalman filter (EKF) but in a transformed coordinate system. This is intended to move the nonlinearities from the measurement model to the process model.
2. Use a bank of parallell EKFs, where each EKF corresponds to an approximate range. The idea is that the EKF that happens to have the most correct range will do better than the other EKFs.
3. Use a particle filter. The idea is that a particle filter with sufficiently many particles can approximate the non-Gaussian posterior distribution directly. 

Unfortunately, none of these approaches are foolproof, and filter divergence happens frequently. 
Recently, we have instead experimented with casting the bearing-only problem as a nonlinear optimization problem, using the factor graph library MiniSAM. This gave better estimation accuracy than the traditional approaches, but is not yet entirely satisfactory due to poor filter consistency and somewhat disappointing velocity estimates. 



|<img src="{{site.url}}/assets/irtracking.png" width="690"> | 
| <span style="color:#959595">Figure: Tracking using a single infrared camera mounted at elevation. If the elevation is decreased, it becomes more difficult to estimate the distances of the targets, and the problem turns into the infamous bearing-only problem.</span> | 

In the context of multi-target tracking, probabilistic graphical models have been studied as a framework for data association. The compatibility between a given track and a given measurement can be represented as an edge in a graphical model. 
The goal in data association is typically to evaluate the probability that a given measurement comes from a given target. 
To calculate such probabilities efficiently, with or without approximations, the structure of the graphical model can be exploited. 


Filtering remains the prevailing paradigm in target tracking. However, based on the shift from filtering to smoothing that happened in the field of SLAM,  one may ask whether graphical smoothing techniques also can be worthwhile to consider in target tracking. This may be particularly promising for highly nonlinear problems such as bearing-only tracking, where no filtering-based solution has shown acceptable performance, despite the apparent simplicity of the problem and intense research efforts over 5 decades. 

Bearing-only tracking has traditionally been mainly of interest in military applications such as anti-submarine warfare. However, the increased popularity of passive sensors (optical and infrared cameras) in autonomous vehicle systems lead to an increased need for reliable bearing-only tracking also in the civilian domain. In particular, the autonomous ferry prototype millAmpere relies on several top mounted cameras for its situational awareness. These cameras can estimate the range of other boats if they are close enough by triangulation relative to the sea surface, but for boats further away the tracking problem gradually turns into a bona-fide bearing-only problem. 


|<img src="{{site.url}}/assets/bofig2.png" width="690"> | 
| <span style="color:#959595">Figure: Estimation of the posterior density for bearing-only tracking using a particle filter. While the posterior is clearly non-Gaussian, it is nevertheless unimodal, and most likely it can be approximated fairly well by a Gaussian close to its peak. </span> | 





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

* Can factor graph libraries and graphical models in general be used to solve data association in multi-scan tracking problems? 
* Can tools for automatic differentiation (e.g. CASADI) be used to generate and evaluate association hypotheses in multi-target tracking?
* It has been claimed that the exact EHM technique (Horridge and Maskell 2006) for marginal association probabilities is an improved version of the junction tree method, which is the general brute force technique for exact inference in graphical models. Investigate this claim. 
* Implementation on real data. 
* Combining factor graph solutions to both smoothing and data association. 
* Combining factor graph solutions to tracking and SLAM.
* Multi-hypothesis data association in SLAM.

## Contact
Supervisors [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo), 
[Lars-Christian Tokle](https://www.ntnu.edu/employees/lars-christian.n.tokle) and
[Martin Vonheim Larsen (FFI)](https://www.mn.uio.no/its/english/people/aca/martinvl/) 

## Prerequisites

Useful courses include [TTK4250 Sensor fusion], TTK21 VSLAM, TTK25 Computer Vision for Control  and TTK4255 Robotic Vision. The candidate should have taken some of these already, and take some of the remaining courses in parallell with the specialization project. 


## References

* Brekke, E. (2020): “[Probabilistic graphical models](http://folk.ntnu.no/edmundfo/msc2020-2021/tk8102lecture06.pdf)”, Lecture notes in TK8102, NTNU. 
* Tokle, L.-C. (2018): “[Multi target tracking using random finite sets with a hybrid state space and approximations](https://ntnuopen.ntnu.no/ntnu-xmlui/bitstream/handle/11250/2575375/18666_FULLTEXT.pdf?sequence=1)”, MSc thesis, NTNU. 
* Kummerle et al. (2011): “[g2o: A General Framework for Graph Optimization](https://www.cct.lsu.edu/~kzhang/papers/g2o.pdf)”, Proceedings of ICRA 2011, Shanghai, China.
* Dellaert, F. (2012): “[Factor Graphs and GTSAM: A Hands-on Introduction](https://borg.cc.gatech.edu/sites/edu.borg/files/downloads/gtsam.pdf)”, Technical report, The Borg Lab, GeorgiaTech.
* Horridge, P. and Maskell, S. (2006): “[Real-Time Tracking Of Hundreds Of Targets With Efficient Exact JPDAF Implementation](https://ieeexplore.ieee.org/document/4085847)”, Proceedings of FUSION, Florence, Italy


|[<img src="https://img.youtube.com/vi/FuWedx0oLX4/0.jpg" width="450">](https://www.youtube.com/watch?v=FuWedx0oLX4) |
|<span style="color:#959595">Link to promo video of 5G technology for milliAmpere from Telia. </span> |

[TTK4250 Sensor fusion]: http://folk.ntnu.no/edmundfo/msc2019-2020/sf13chapters.pdf
