---
layout: post
title: Bearing-only smoothing by means of factor graphs
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
| <span style="color:#959595">Figure: Tracking using a single infrared camera mounted at elevation. If the elevation is decreased, it becomes more difficult to estimate the distances of the targets, and the problem turns into the infamous bearing-only problem. From [Helgesen et al. 2020].</span> | 

As an alternative to filter-based solutions, we have recently experimented with a factor-graph solution to bearing-only tracking. In this work, the lightweight factor graph library miniSAM was used. The results outperformed traditional methods with regards to position accuracy, but were less impressive with regards to other performance measures. 

|<img src="{{site.url}}/assets/bofig2.png" width="690"> | 
| <span style="color:#959595">Figure: Estimation of the posterior density for bearing-only tracking using a particle filter. While the posterior is clearly non-Gaussian, it is nevertheless unimodal, and this makes it reasonable to hope that optimization-based solutions can be successful. </span> | 





## Scope
The primary objective of this project is develop a method for bearing-only tracking through smoothing and nonlinear optimization, and analyze its performance on real and simulated data of relevance to the use case of an autonomous pedestrian ferry. 



## Proposed Tasks for the 5th year project

A starting point for the 5th year project is the miniSAM implementation of bearing-only smoothing reported in ([Helgesen and Brekke 2022]). An important goal will be to either find a way of extracting and utilising the covariances in this framework, or to replace it with a framework (e.g. full GTSAM) which enables analysis and utilisation of the covariances. 

1. Make yourself familiar with basic theory for probabilistic graphical models.  
2. Make yourself familiar g2o, GTSAM and possibly other available factor graph libraries. Summarize main similarities and differences. 
3. Formulate bearing-only tracking as a nonlinear smoothing and optimization problem, using the Bayes tree framework. Investigate to which extent this formulation should be related to the matrix algebra of the ISAM2 SLAM method. 
4. Implement a solution to the nonlinear smoothing and optimization problem formulated in Task 3.
5. Compare with benchmarking methods such as range-parameterized EKF and particle filter, using both simulated data and real data recorded from the cameras onboard milliAmpere.
6. Write report.

## Proposed Tasks for the master thesis

The project work aims to be extended into a master thesis for the spring of 2021. Several directions are possible depending on the findings in the 5th year project.  

* The solution sketched above solves a filtering and smoothing problem, but does not handle misdetections and false alarms. For this, the bearing-only solution must be expanded to a track method that also includes data association. 
* We don't know for sure whether the in-built optimization methods in factor graph libraries are sufficient for a highly non-linear problem such as bearing-only tracking. These are typically variations of Gauss-Newton or Levenberg-Marquardt, which do not take the full Hessian into account. 
* Bearing-only tracking will inevitably suffer from lack of observability in many real-life scenarios. This can be addressed by integrating bearing-only tracking in a larger multi-sensor tracking system which also involves active sensors such as radar and lidar. It can also be addressed by investigating bearing-only tracking as a limit case of passive tracking with georeferencing ([Helgesen et al. 2020]). In both cases, a challenge arises because the methods hitherto used for multi-sensor tracking and georeferencing in the milliAmpere ecosystem are purely filter-based. 

## Contact
Supervisors [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo) and 
[Øystein K. Helgesen](https://www.ntnu.no/ansatte/oystein.k.helgesen)

## Prerequisites

The candidate should have take at least one of the two courses  [TTK4250 Sensor fusion] and [TTK4255 Robotic Vision] before this project. Additional courses in estimation or SLAM will be useful. 

## References

* Brekke, E. (2020): “[Probabilistic graphical models](http://folk.ntnu.no/edmundfo/msc2020-2021/tk8102lecture06.pdf)”, Lecture notes in TK8102, NTNU. 
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