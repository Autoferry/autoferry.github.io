---
layout: post
title: Trajectory planning and collision avoidance for the worlds first autonomous passenger ferry
category: COLAV
---
## Background
Over the past decade, NTNU has developed concepts and technology related to autonomy for maritime surface vessels. One outcome of this research is the production of milliAmpere and milliAmpere II. The milliAmpere (video below) is a prototype for an autonomous passenger and is under continuous development. It has the capacity to perform fully autonomous transit operations, which is demonstrated through a 3 hour continuous autonomous operation in a canal in Trondheim (video below). The milliAmpere II (picture below), is a full-scale autonomous passenger ferry, and is set to demonstrate an autonomous passenger ferry service concept in Trondheim in 2022. 
Furthermore, in 2020 the sum of the research on maritime autonomy at NTNU culminated in NTNU establishing[ Zeabuz], a company aiming at make maritime autonomy accessible to mobility changemakers globally, enabling potentially radically new transport systems.



|[![three hour test video]](https://www.youtube.com/watch?v=Ry3-yxVaDuE&list=PLc2vvxBHfBcoHvfcIRsFROmJzXhbJCvb5&index=1&ab_channel=NTNUCybernetics)|
|*Video about the Autoferry Project*|

The focus of this project will be on trajectory planning and collision avoidance for autonomous surface vessels operating in confined environments like urban areas, canals and ports, where both static and dynamic obstacles must be considered simultaneously. Furthermore, considerations should be made to a subset of the rules in the COLREGs, the "rules of the road" on water, which applied to all vessels.

The ambition for the combined work of the project work and Master's thesis should be an algorithm for long-term (5-10 min) trajectory planning which produces rules-compliant, dynamically feasible trajectories, where the trajectory shows a good tradeoff between safety and efficiency. The candidate is encouraged to solve the problem by the use of optimization tools like CasADi, which has good support for Matlab and Python. 

The thesis proposal is given by NTNU in collaboration with Zeabuz. It will be supervised by [Morten Breivik] from NTNU, and [Emil Thyri] from Zeabuz. This enables the candidate to utilize existing resources from both Zeabuz and NTNU when needed.  Furthermore, the experimental platforms of NTNU facilitates full-scale experiments towards the end of the Master's work, to test and demonstrate the the capacity of the developed algorithms.  

This task is comprehensive, and requires a motivated candidate with a ambitions in the field of maritime autonomy.

|<img src="{{site.url}}/assets/milliAmpere_2_on_water_during_initial_tests.png" width="650"> |
|*milliAmpere 2 during initial sea-trials in April 2021.*|


## Prerequisites
The task is focused on a practical problem, while solving it requires a good theoretical understanding of the underlying aspects. The candidate should favour such a combination.  Subjects within guidance and control of marine vessels, and optimization, e.g. [TTK4190 Fartøysstyring] and [TTK4135 - Optimalisering og regulering] is advantageous. The candidate should have good programming skills in Python (alternatively C++). 

## Contact
Write a short email where you explain your motivation for this task as well as about your background, and send it to [Morten Breivik] and  [Emil Thyri]. We will then arrange a meeting with you to discuss the task.

<!-- ## References
* Thyri, E.H. (2019): “[A Path-Velocity Decomposition Approach to Collision Avoidance for Autonomous Passenger Ferries](https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2625711)”, MSc thesis, NTNU. 
* Thyri, E.H. (2020): “[A Path-Velocity Decomposition Approach to Collision Avoidance for Autonomous Passenger Ferries in Confined Waters](https://www.sciencedirect.com/science/article/pii/S240589632031884X)”, in 2020, 21th IFAC World Congress, Berlin Germany.   -->


[Morten Breivik]: https://www.ntnu.no/ansatte/morten.breivik
[Emil Thyri]: https://www.ntnu.no/ansatte/emil.h.thyri
[three hour test video]: {{site.url}}/assets/telia_video_snip.png
[TTK4190 Fartøysstyring]: https://www.ntnu.edu/studies/courses/TTK4190#tab=omEmnet
[TTK4135 - Optimalisering og regulering]: https://www.ntnu.no/studier/emner/TTK4135#tab=omEmnet
[Autoferry project]: https://www.ntnu.edu/autoferry
[ Zeabuz]: https://www.zeabuz.com/