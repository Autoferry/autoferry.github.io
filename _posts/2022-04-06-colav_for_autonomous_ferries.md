---
layout: post
title: Trajectory planning and collision avoidance for the worlds first autonomous passenger ferry
category: COLAV
---
## Background
Over the past decade, NTNU has developed concepts and technology related to autonomy for maritime surface vessels. One outcome of this research is the production of milliAmpere and milliAmpere II. The milliAmpere (video below) is a prototype for an autonomous passenger and is under continuous development. It has the capacity to perform fully autonomous transit operations, which is demonstrated through a 3 hour continuous autonomous operation in a canal in Trondheim (video below). The milliAmpere II (picture below), is a full-scale autonomous passenger ferry, and is set to demonstrate an autonomous passenger ferry service concept in Trondheim in 2022. Furthermore, in 2020 the sum of the research on maritime autonomy at NTNU culminated in NTNU establishing Zeabuz, a company aiming at providing a new urban mobility concept based on autonomous passenger ferries.

|[![telia video]](https://www.youtube.com/watch?v=Ry3-yxVaDuE&list=PLc2vvxBHfBcoHvfcIRsFROmJzXhbJCvb5&index=1&ab_channel=NTNUCybernetics)|
|*Video about the Autoferry Project*|

The focus of this project will be on trajectory planning and collision avoidance for autonomous surface vessels operating in confined environments like urban areas, canals and ports, where both static and dynamic obstacles must be considered simultaneously. Furthermore, considerations should be made to a subset of the rules in the COLREGs, the "rules of the road" on water, which applied to all vessels.

The ambition for the combined work of the project work and Master's thesis should be an algorithm for long-term (5-10 min) trajectory planning which produces rules-compliant, dynamically feasible trajectories, where the trajectory shows a good tradeoff between safety and efficiency. The candidate is encouraged to solve the problem by the use of optimization tools like CasADi, which has good support for Matlab and Python. 

This task is comprehensive, and requires a motivated candidate with a ambitions in the field of maritime autonomy.

The experimental platforms of NTNU facilitates full-scale experiments towards the end of the Master's work, to both test and demonstrate the the capacity of the developed algorithms. 


|<img src="{{site.url}}/assets/milliAmpere_2_on_water_during_initial_tests.png" width="650"> |
|*milliAmpere 2 during initial sea-trials in April 2021.*|



## Prerequisites
This work is a combination of both theory and practice.  The candidate should therefore favour both theoretical and experimental work. Subjects within guidance and control of marine vessels, and optimization, such as [TTK4190 Fartøysstyring] and [TTK4135 - Optimalisering og regulering] is advantageous.

<!-- ## Proposed tasks for the 5th year project (autumn 2021)
* Identify problems and challenges that are unique with the specific operational environment, compared to open-sea operations. 
* Do a literature search on existing methods for maritime collision avoidance, and identify which techniques are suitable for the specific task.
* Implement the method. Start of with the simplest implementation and build from there. 
* Evaluate and show proof of concept of the method through simulations.
* Write report. -->

<!-- ## Proposed tasks for the Masters thesis (spring 2022)
* Continue unfinished project work.
* Improve method by introducing considerations on passenger comfort and the Convention on the International Regulations for Preventing Collisions at Sea (COLREGs).
* Make preparations for and conduct full-scale experiments with milliAmpere and/or milliAmpere 2 in Trondheim harbor.
* Write report. -->

## Contact
Write a short email where you explain your motivation for this task as well as about your background, and send it to [Morten Breivik] and  [Emil Thyri]. We will then arrange a Teams meeting with you to discuss the task.

<!-- ## References
* Thyri, E.H. (2019): “[A Path-Velocity Decomposition Approach to Collision Avoidance for Autonomous Passenger Ferries](https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2625711)”, MSc thesis, NTNU. 
* Thyri, E.H. (2020): “[A Path-Velocity Decomposition Approach to Collision Avoidance for Autonomous Passenger Ferries in Confined Waters](https://www.sciencedirect.com/science/article/pii/S240589632031884X)”, in 2020, 21th IFAC World Congress, Berlin Germany.   -->


[Morten Breivik]: https://www.ntnu.no/ansatte/morten.breivik
[Emil Thyri]: https://www.ntnu.no/ansatte/emil.h.thyri
[Bjørn-Olav Holtung Eriksen]: https://www.ntnu.edu/employees/bjorn-olav.holtung.eriksen
[telia video]: {{site.url}}/assets/telia_video_snip.png
[TTK4190 Fartøysstyring]: https://www.ntnu.edu/studies/courses/TTK4190#tab=omEmnet
[TTK4135 - Optimalisering og regulering]: https://www.ntnu.no/studier/emner/TTK4135#tab=omEmnet
[Autoferry project]: https://www.ntnu.edu/autoferry