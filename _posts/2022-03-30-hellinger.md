---
layout: post
title: Measures of fidelity for digital twin simulation - multi-target distribution metrics
category: SF
---
## Background
Simulations play an important role in the development of autonomous vehicle technology. Simulations are needed to carry out the thousands and millions of tests required before a system can be certified as safe. Furthermore, simulations can be used to train artificial intelligence methods such as convolutional neural networks. For both these tasks, the question arises: How can we assess that the simulation is sufficiently realistic and accurate?

In [(Vasstein 2021)] we have proposed that such an assessment can be based on the following principle: The simulation is considered indistinguishable from the real world if the situational awareness that the agent obtains from the real world data is the same as the situational awareness that the agent obtains from the simulated replica of the same scenario. 

To make this abstract criterion concrete, we looked at the output of a multi-target tracking method used to track other boats in the vicinity of the autonomous ferry milliAmpere. The output of the method used, the joint integrated probabilistic data assocation (JIPDA), consists of state estimates, covariances and existence probabilities, which together constitute a multi-Bernoulli multi-target distribution. Various metrics can be calculated to quantify how much two distributions differ, similarly to how one can calculate the distance between two points in Cartesian space using the standard Euclidean metric. In this work, we used the Hellinger distance, which gives zero if the distributions are identical, and one if they have no similarity at all. 

The results so far indicate that a low value of the Hellinger metric can be taken as proof that the situational awareness in the real world and the simulation are identical. However, it is also a somewhat unforgiving measure: False alarms, biases and the variable quality of velocity estimates can all lead to high Hellinger values. 


|<img src="{{site.url}}/assets/irtracking.png" width="690"> | 
| <span style="color:#959595">Figure: Tracking using a single infrared camera mounted at elevation. If the elevation is decreased, it becomes more difficult to estimate the distances of the targets, and the problem turns into the infamous bearing-only problem. From [Helgesen et al. 2020].</span> | 

Bla bla

|<img src="{{site.url}}/assets/bofig2.png" width="690"> | 
| <span style="color:#959595">Figure: Estimation of the posterior density for bearing-only tracking using a particle filter. While the posterior is clearly non-Gaussian, it is nevertheless unimodal, and this makes it reasonable to hope that optimization-based solutions can be successful. </span> | 





## Scope

The goal of the 5th year project is two-fold. First, we would like to get a firmer understanding of how the multi-target Hellinger metric behaves for typical tracking output such as multi-Bernoulli multi-target densities. Second, it is also of interest to compare it with other possible similarity measures.
The plan is to work with data recorded from milliAmpere together with simulated data from the Autoferry Gemini. It may also be desirable to record additional data in the beginning of the semester, and it may be useful to work with simpler simulations in e.g. pure Matlab or Python. 

## Proposed Tasks for the 5th year project

Tasks such as the following are proposed for the 5th year project. The candidate is only expected to address a subset of these in the specialization project. 

1. Make yourself familiar with basic theory for random finite sets and metrics for multi-target densities.  
2. Implement the Hellinger metric and some other multi-Bernoulli distance measures on two purely simulated data sets and assess whether the distance measures are meaningful. Other distance measures can be the Kullback-Leibler divergence and various measures in the so-called class of Csiszar information functionals.
3. Propose guidelines for threshold values: When is the distributional metric low enough to consider the output of the two trackers similar?
4. Propose tuning strategies using a distributional metric. How can, e.g., the Hellinger metric, be used to decide reasonable values of clutter rates, detection probabilities and covariances in a multi-target tracking system?
5. To evaluate the multi-Bernoulli Hellinger metric we make use of importance sampling. For tracking output with more than a handful of tracks more efficient evaluation techniques are needed. One possibility can be to make use of assignment techniques such as Murty's method. 
6. Write report.

## Proposed Tasks for the master thesis

The project work aims to be extended into a master thesis for the spring of 2021. In addition to the tasks already mentioned, the following tasks can be suitable topics for a master thesis.

* To label or not to label? In multi-Bernoulli random finite sets, target identities are discarded. This means that the multi-Bernoulli Hellinger metric will be insensitive to events where track swaps occur. An alternative is to develop distributional metrics for so-called labeled random finite sets. The concept of labeled random finite sets is a highly debated topic in the sensor fusion community, and the findings of this project may have important implications for this debate. 
* Develop techniques for evaluating the Hellinger metric for other multi-target distributions than the multi-Bernoulli, such as the Poisson multi-target distribution and multi-Bernoulli mixtures.

## Contact
Supervisors [Edmund F. Brekke](http://www.ntnu.no/ansatte/edmundfo) and 
[Kjetil Vasstein](https://www.ntnu.no/ansatte/kjetv)

## Prerequisites

The candidate should have taken the course  [TTK4250 Sensor fusion] or similar before beginning this 5th year project. Background in detection theory, from e.g. [TTT4275 Estimation, Detection and Classification] will also be useful. 

## References

* Vasstein, K., Helgesen, Ø. K. and Brekke, E. (2022): “Hellinger metrics for validating high fidelity simulators through target tracking”, Submitted to Fusion 2022. Available on request. 
* Vasstein, K., Brekke, E., Mester, R. and Eide, E. (2020): “[Autoferry Gemini: a real-time simulation platform for electromagnetic radiation sensors on autonomous ships](https://iopscience.iop.org/article/10.1088/1757-899X/929/1/012032)”, Proceedings of ICMASS. 


|[<img src="https://img.youtube.com/vi/Ry3-yxVaDuE/0.jpg" width="450">](https://www.youtube.com/watch?v=Ry3-yxVaDuE) |
|<span style="color:#959595">Link to video of milliAmpere autonomy demonstration. </span> |

[TTK4250 Sensor fusion]: http://folk.ntnu.no/edmundfo/msc2019-2020/sf13chapters.pdf
[(Vasstein 2021)]: https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2781031
[Autoferry Gemini]: https://iopscience.iop.org/article/10.1088/1757-899X/929/1/012032
[TTT4275 Estimation, Detection and Classification]: https://www.ntnu.edu/studies/courses/TTT4275#tab=omEmnet