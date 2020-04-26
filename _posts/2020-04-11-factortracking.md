---
layout: post
title: Factor graphs in target tracking
category: SF
---
## Background
During the last decade, so-called pose graph optimization has become the undisputed gold standard in simultaneous localization and mapping (SLAM). The key idea is that all measurements can be modeled as probabilistic constraints on the trajectory of the vehicle. The entire trajectory can then be estimated by optimization over the joint collection of constraints. Thus, modern SLAM methods can be said to do smoothing rather than filtering, which was the dominating approach in the early days of SLAM. 

The key construction underlying this is the concept of a factor graph, or more generally probabilistic graphical models. 
Popular SLAM methods such as ISAM2 and ORB-SLAM make use of advanced factor graph libraries such as GTSAM and g2o, which can enable the user to work efficiently with graph-based representations of knowledge. 
While these libraries have had their breakthrough as frameworks for SLAM, their potential applications may also include a wealth of other sensor fusion problems such as target tracking. Below, we sketch two reasons why factor graphs can be of interest in target tracking. 

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
