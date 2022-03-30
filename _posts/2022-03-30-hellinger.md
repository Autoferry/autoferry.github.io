---
layout: post
title: Fidelity measures for digital twin simulation - The multi-target Hellinger distance and beyond
category: SF
---
## Background
Simulations play an important role in the development of autonomous vehicle technology. Simulations are needed to carry out the thousands and millions of tests required before a system can be certified as safe. Furthermore, simulations can be used to train artificial intelligence methods such as convolutional neural networks. For both these tasks, the question arises: How can we assess that the simulation is sufficiently realistic and accurate?

In (Vasstein et al. 2022) we have proposed that such an assessment can be based on the following principle: The simulation is considered indistinguishable from the real world if the situational awareness that the agent obtains from the real world data is the same as the situational awareness that the agent obtains from the simulated replica of the same scenario. 

To make this abstract criterion concrete, we looked at the output of a multi-target tracking method used to track other boats in the vicinity of the autonomous ferry milliAmpere. The output of the method used, the joint integrated probabilistic data assocation (JIPDA), consists of state estimates, covariances and existence probabilities, which together constitute a multi-Bernoulli multi-target distribution. Various metrics can be calculated to quantify how much two distributions differ, similarly to how one can calculate the distance between two points in Cartesian space using the standard Euclidean metric. In this work, we used the Hellinger distance, which gives zero if the distributions are identical, and one if they have no similarity at all. 


|<img src="{{site.url}}/assets/irtracking.png" width="690"> | 
| <span style="color:#959595">Figure: Tracking using a single infrared camera mounted at elevation. If the elevation is decreased, it becomes more difficult to estimate the distances of the targets, and the problem turns into the infamous bearing-only problem. From [Helgesen et al. 2020].</span> | 

Bla bla

|<img src="{{site.url}}/assets/bofig2.png" width="690"> | 
| <span style="color:#959595">Figure: Estimation of the posterior density for bearing-only tracking using a particle filter. While the posterior is clearly non-Gaussian, it is nevertheless unimodal, and this makes it reasonable to hope that optimization-based solutions can be successful. </span> | 





## Scope



The primary objective of this project is develop a method for bearing-only tracking through smoothing and nonlinear optimization, and analyze its performance on real and simulated data of relevance to the use case of an autonomous pedestrian ferry. 



## Proposed Tasks for the 5th year project

Bla bla

1. Make yourself familiar with basic theory for probabilistic graphical models.  
2. Make yourself familiar g2o, GTSAM and possibly other available factor graph libraries. Summarize main similarities and differences. 
3. Formulate bearing-only tracking as a nonlinear smoothing and optimization problem, using the Bayes tree framework. Investigate to which extent this formulation should be related to the matrix algebra of the ISAM2 SLAM method. 
4. Implement a solution to the nonlinear smoothing and optimization problem formulated in Task 3.
5. Compare with benchmarking methods such as range-parameterized EKF and particle filter, using both simulated data and real data recorded from the cameras onboard milliAmpere.
6. Write report.

## Proposed Tasks for the master thesis

The project work aims to be extended into a master thesis for the spring of 2021. Several directions are possible depending on the findings in the 5th year project.  

* Bla bla
* Bla bla
* Bla bla

## Contact
Supervisors [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo) and 
[Kjetil Vasstein](https://www.ntnu.no/ansatte/kjetv)

## Prerequisites

The candidate should either have taken the course  [TTK4250 Sensor fusion] or take it in parallell with the 5th year project. 
## References

* Vasstein, K., Helgesen, Ø. K. and Brekke, E. (2022): “[Hellinger metrics for validating high fidelity simulators through target tracking](https://folk.ntnu.no/edmundfo/fusion2022preprints/VassteinHellinger.pdf)”, Submitted to Fusion 2022. 
* Vasstein, K., Brekke, E., Mester, R. and Eide, E. (2020): “[Autoferry Gemini: a real-time simulation platform for electromagnetic radiation sensors on autonomous ships](https://iopscience.iop.org/article/10.1088/1757-899X/929/1/012032)”, Proceedings of ICMASS. 


|[<img src="https://img.youtube.com/vi/Ry3-yxVaDuE/0.jpg" width="450">](https://www.youtube.com/watch?v=Ry3-yxVaDuE) |
|<span style="color:#959595">Link to video of milliAmpere autonomy demonstration. </span> |

[TTK4250 Sensor fusion]: http://folk.ntnu.no/edmundfo/msc2019-2020/sf13chapters.pdf
[(Vasstein et al. 2022)]: https://folk.ntnu.no/edmundfo/fusion2022preprints/VassteinHellinger.pdf