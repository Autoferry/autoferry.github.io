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

In the context of multi-target tracking, probabilistic graphical models have been studied as a framework for data association. The compatibility between a given track and a given measurement can be represented as an edge in a graphical model. 
The goal in data association is typically to evaluate the probability that a given measurement comes from a given target. 
To calculate such probabilities efficiently, with or without approximations, the structure of the graphical model can be exploited. 

Filtering remains the prevailing paradigm in target tracking. However, based on the shift from filtering to smoothing that happened in the field of SLAM,  one may ask whether graphical smoothing techniques also can be worthwhile to consider in target tracking. This may be particularly promising for highly nonlinear problems such as bearing-only tracking, where no filtering-based solution has shown acceptable performance, despite the apparent simplicity of the problem and intense research efforts over 5 decades. 

Bearing-only tracking has traditionally been mainly of interest in military applications such as anti-submarine warfare. However, the increased popularity of passive sensors (optical and infrared cameras) in autonomous vehicle systems lead to an increased need for reliable bearing-only tracking also in the civilian domain. In particular, the autonomous ferry prototype MillAmpere relies on several top mounted cameras for its situational awareness. While these cameras 








## Scope
As a primary objective, this project aims to say something about the suitability of different factor graph libraries for applications in target tracking. 

## Proposed Tasks for the 5th year project

1. Make yourself familiar with the standard model of multi-target tracking and popular methods such as JIPDA, PHD filter, CPHD filter and PMBM filter.
2. Study the PMBM-based derivation of the JIPDA, and do the required derivations to replace the JIPDA with LMIPDA.
3. Design simulation scenarios and benchmark measures to compare tracking methods. 
4. Compare basic LMIPDA, PMBM-based LMIPDA, PHD filter, basic JIPDA, PMBM-based JIPDA and CPHD filter. 
5. Write report.

## Proposed Tasks for the master thesis

The project work aims to be extended into a master thesis for the spring of 2021. Several directions are possible depending on the interest of the student. 

* Development of an LMIPDA method tailored to be used in a drone-based tracking system. 
* Can strategies such as those used in an LMIPDA also be used in a more complex JIPDA or PMBM filter? One project that possibly could be addressed in this manner is clustering and cluster-splitting of nearby tracks. 
* Integration of multiple models using the IMM framework.
* Integration of wake models. 
* Integration of visibility probabilities. 
* Benchmarking on several real world data sets. 

## Contact
For more information, contact supervisors [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo) or
[Lars-Christian Tokle](https://www.ntnu.edu/employees/lars-christian.n.tokle) 

## References

* Tokle, L.-C. (2018): “[Multi target tracking using random finite sets with a hybrid state space and approximations](https://ntnuopen.ntnu.no/ntnu-xmlui/bitstream/handle/11250/2575375/18666_FULLTEXT.pdf?sequence=1)”, MSc thesis, NTNU. 
* Kummerle et al. (2011): “[g2o: A General Framework for Graph Optimization](https://www.cct.lsu.edu/~kzhang/papers/g2o.pdf)”, Proceedings of ICRA 2011, Shanghai, China.
