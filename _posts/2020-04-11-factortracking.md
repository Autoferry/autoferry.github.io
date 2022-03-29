---
layout: post
title: Bearings-only smoothing by means of factor graphs
category: SF
---
## Background
During the last decade, factor graph optimization has become the gold standard in simultaneous localization and mapping (SLAM). The key idea is that all measurements can be modeled as probabilistic constraints on the trajectory of the vehicle. The entire trajectory can then be estimated by optimization over the joint collection of constraints. Thus, modern SLAM methods can be said to do smoothing rather than filtering, which was the dominating approach in the early days of SLAM. 

Another problem in sensor fusion, which has challenged researchers for more than 40 years, is bearing-only tracking. 
During the cold war, there was a strong focus on tracking of submarines using passive acoustic measurements. 
In more recent years, the increasing focus on computer vision for mobile robotics also leads to a need for reliable solutions to bearing-only tracking. 
Bearing-only tracking is particularly challenging because it is a nonlinear problem with limited observability. 
The movement of the target can only be estimated if the ownship makes stronger manoeuvers. 

|<img src="{{site.url}}/assets/irtracking.png" width="690"> | 
| <span style="color:#959595">Figure: Tracking using a single infrared camera mounted at elevation. If the elevation is decreased, it becomes more difficult to estimate the distances of the targets, and the problem turns into the infamous bearing-only problem.</span> | 

As an alternative to filter-based solutions, we have recently experimented with a factor-graph solution to bearing-only tracking. In this work, the lightweight factor graph library miniSAM was used. The results outperformed traditional methods with regards to position accuracy, but were less impressive with regards to other performance measures. 

|<img src="{{site.url}}/assets/bofig2.png" width="690"> | 
| <span style="color:#959595">Figure: Estimation of the posterior density for bearing-only tracking using a particle filter. While the posterior is clearly non-Gaussian, it is nevertheless unimodal, and this makes it reasonable to hope that optimization-based solutions can be successful. </span> | 





## Scope
The primary objective of this project is develop a method for bearing-only tracking through smoothing and nonlinear optimization, and analyze its performance on real and simulated data of relevance to the use case of an autonomous pedestrian ferry. 



## Proposed Tasks for the 5th year project

A starting point for the 5th year project is the miniSAM implementation of Helgesen and Brekke (2022). An important goal will be to either find a way of extracting and utilising the covariances in this framework, or to replace it with a framework (e.g. full GTSAM) which enables analysis and utilisation of the covariances. 

1. Make yourself familiar with basic theory for probabilistic graphical models.  
2. Make yourself familiar g2o, GTSAM and possibly other available factor graph libraries. Summarize main similarities and differences. 
3. Formulate bearing-only tracking as a nonlinear smoothing and optimization problem, using the Bayes tree framework. Investigate to which extent this formulation should be related to the matrix algebra of the ISAM2 SLAM method. 
4. Implement a solution to the nonlinear smoothing and optimization problem formulated in Task 3.
5. Compare with benchmarking methods such as range-parameterized EKF and particle filter, using both simulated data and real data recorded from the cameras onboard milliAmpere.
6. Write report.

## Proposed Tasks for the master thesis

The project work aims to be extended into a master thesis for the spring of 2021. Several directions are possible depending on the findings in the 5th year project.  

* The solution sketched above solves a filtering and smoothing problem, but does not handle misdetections and false alarms. For this, the bearing-only solution must be expanded to a track method that also includes data association. 
* One possible weakness with popular factor graph libraries could be their optimization methods. These are typically some variation of Gauss-Newton or Levenberg-Marquardt, which does not take the full Hessian into account. For a highly non-linear problem such as bearing-only tracking,  improvements may perhaps be achieved by implementing a more direct Newton-based optimization method. 
* Bearing-only tracking will inevitably suffer from lack of observability in many real-life scenarios. This can be addressed by integrating bearing-only tracking in a larger multi-sensor tracking system which also involves active sensors such as radar and lidar. It can also be addressed by investigating bearing-only tracking as a limit case of passive tracking with georeferencing. In both cases, a challenge arises because the methods hitherto used for multi-sensor tracking and georeferencing in the milliAmpere ecosystem are purely filter-based. 

## Contact
Supervisors [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo), 
[Lars-Christian Tokle](https://www.ntnu.edu/employees/lars-christian.n.tokle) and
[Martin Vonheim Larsen (FFI)](https://www.mn.uio.no/its/english/people/aca/martinvl/) 

## Prerequisites

Useful courses include [TTK4250 Sensor fusion], TTK21 VSLAM, TTK25 Computer Vision for Control  and TTK4255 Robotic Vision. The candidate should have taken some of these already, and take some of the remaining courses in parallell with the specialization project. 


## References

* Brekke, E. (2020): “[Probabilistic graphical models](http://folk.ntnu.no/edmundfo/msc2020-2021/tk8102lecture06.pdf)”, Lecture notes in TK8102, NTNU. 
* Helgesen, Ø. K. and Brekke, E. (2022): “[Bearings-only tracking using factor graphs](https://ntnuopen.ntnu.no/ntnu-xmlui/bitstream/handle/11250/2575375/18666_FULLTEXT.pdf?sequence=1)”, Submitted to Fusion 2022. 
* Kummerle et al. (2011): “[g2o: A General Framework for Graph Optimization](https://www.cct.lsu.edu/~kzhang/papers/g2o.pdf)”, Proceedings of ICRA 2011, Shanghai, China.
* Dellaert, F. (2012): “[Factor Graphs and GTSAM: A Hands-on Introduction](https://borg.cc.gatech.edu/sites/edu.borg/files/downloads/gtsam.pdf)”, Technical report, The Borg Lab, GeorgiaTech.
* Horridge, P. and Maskell, S. (2006): “[Real-Time Tracking Of Hundreds Of Targets With Efficient Exact JPDAF Implementation](https://ieeexplore.ieee.org/document/4085847)”, Proceedings of FUSION, Florence, Italy


|[<img src="https://img.youtube.com/vi/FuWedx0oLX4/0.jpg" width="450">](https://www.youtube.com/watch?v=FuWedx0oLX4) |
|<span style="color:#959595">Link to promo video of 5G technology for milliAmpere from Telia. </span> |

[TTK4250 Sensor fusion]: http://folk.ntnu.no/edmundfo/msc2019-2020/sf13chapters.pdf
