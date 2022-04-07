---
layout: post
title: Trajectory planning and collision avoidance for autonomous passenger ferries
category: INACTIVE
---
## Background

The concept of small autonomous passenger ferries in urban areas is a more flexible and environmentally-friendly alternative to bridges or manned ferries. NTNU's [Autoferry project] therefore aims to develop groundbreaking new concepts and methods which will enable the development of such ferries for urban water transport. As is apparent from the automotive industry, autonomy is maturing, and it is not a question of if, but when, autonomous vessels will emerge on a commercial scale in the maritime industry as well. There are already several initiatives taking lead on pilot projects on this field, such as Kongsberg Maritime with the cargo transport drones for Asko, and Zeabuz, a spinoff from NTNU, aiming at developing core technology and solutions for autonomous urban passenger transport.

|[![telia video]](https://www.youtube.com/watch?time_continue=1&v=FuWedx0oLX4&feature=emb_logo)|
|*Video about the Autoferry Project*|

<!-- For autonomous maritime transport to be a reality, there are two major tasks that need to be solved: Firstly, relevant aspects on the operational environment needs to be sensed and comprehended to form a sufficient situational awareness. Subsequently, mission planning needs to be performed, based on the situational awareness, to produce a feasible plan that completes the objective in a safe and secure manner. For an autonomous maritime vessel, this is done in the form of trajectory planning, on either a local or global scale.  -->

The main focus of the task we propose here will be on trajectory planning and collision avoidance for autonomous passenger vessels. In particular, on vessels maneuvering in urban environments where the traffic is unpredictable, and the available maneuverable space is limited. 
A lot of work already exists on maritime collision avoidance, but very little is focused on smaller vessels in confined or cluttered space. 
<!-- The work should therefore start by doing a literature search on existing collision avoidance methods and identifying features of the methods that make them more or less suitable for the task, before the work on developing new methods is started. -->

|<img src="{{site.url}}/assets/milliAmpere_2_on_water_during_initial_tests.png" width="650"> |
|*milliAmpere 2 during initial sea-trials in April 2021.*|

This project has a focus on applied solutions, where it is of interest that the resulting systems or algorithms are feasible in a real-world application. NTNU currently owns two prototypes on fully electric autonomous passenger ferries, the milliAmpere (video on top) and milliAmpere 2 (picture above). The candidate is therefore encouraged to aim towards performing full-scale experiments towards the end of the work (Masteroppgave). The milliAmpere platform runs an on-board computer with Ubuntu and robot operating system (ROS) which makes it simple to interface new algorithms with the existing systems such as navigation, target-tracking and dynamic positioning for trajectory tracking. 

Due to the complexity of the task of safe and collision-free maneuvering in cluttered environments, several methods and algorithms for trajectory-planning and collision avoidance are often combined into a hybrid structure, where each planner handles different aspects of the task. An example of such a structure is shown below. 

|<img src="{{site.url}}/assets/three_layer_structure.png" width="650"> |
|*Three layered COLAV structure with examples of decision-support systems that can be used in one or more of the planners.*|

It is mainly in the High-level COLAV that we want to put the focus of this task, but the problem formulation is open to input from the candidate, also on work in lower levels of the COLAV system. 

**Due to the extent of this task, it is open for up to two candidates working on separate parts of the task.** Cooperation between the candidates is not a requirement, yet it is encouraged if appropriate.

## Previous work
In (Thyri 2019, 2020), a COLAV method for passenger ferries operating in urban environments is described. In short, the method plans a velocity-profile for a predefined path so that the resulting trajectory is collision free regarding dynamic obstacles. The method is simple and intuitive, and is tested through full-scale experiments on simple canal-crossing operations. For more complex operations, this method comes in short, due to its simplicity. During the autumn of 2020 and spring of 2021, a Master student has worked on extending the principles of the method from using a predefined path, to a predefined area, effectively increasing the number of available manuevers to the trajectory planner.
A alternative for this project is to build on this work, to make a graph-based global trajectory planner that considers both static and dynamic obstacles. This is a high level COLAV, where a trajectory is planned from the current position of the vessel to the transit-destination, where considerations on static and dynamic obstacles are included. The co-supervisor Emil Thyri has also done some work in both mid-level and short-term COLAV, which can be combined to get a more complete system in simulations and experiments. 


<!-- Some previous work 

In (Thyri 2019, 2020), a COLAV method for passenger ferries operating in urban environments is described. The method in short:
* The method inputs a predefined path that is collision free with any static obstacles, as well as tracking data on moving obstacles in proximity.
* A simplified obstacle representation is made for each obstacle. The representation can be made to consider COLREGs, obstacle size and velocity. Se left picture below.. 
* The obstacle representations are transformed onto the path, based on the assumptions that the obstacles keep constant heading and velocity. This gives a two-dimensional path-time space where the area spanned by the transformed obstacle representation represents that obstacle representations occupation of the path in time,  see middle picture below.
* A visibility-graph is constructed to connect the start of the path to the end of the path in a way that does not intersect the collision-regions of the transformed obstacle representation, see right picture below. 
* The graph is traversed with a graph search algorithm to find the minimum cost path, and a velocity-profile can be calculated from that path.  -->

<!-- ## Problem formulation
This task concerns developing a COLAV system for an autonomous surface vessels operating in confined space with high and irregular traffic. 
Problems and challenges that are unique with the specific operational environment, compared to open-sea operations, needs to be identified, and holes in the ex -->

## Prerequisites
This work is a combination of both theory and practice.  The candidate should therefore favour both theoretical and experimental work. Subjects within guidance and control of marine vessels such as [TTK4190 Fartøysstyring] is advantageous, but not a requirement.

## Proposed tasks for the 5th year project (autumn 2021)
* Identify problems and challenges that are unique with the specific operational environment, compared to open-sea operations. 
* Do a literature search on existing methods for maritime collision avoidance, and identify which techniques are suitable for the specific task.
* Implement the method. Start of with the simplest implementation and build from there. 
* Evaluate and show proof of concept of the method through simulations.
* Write report.

## Proposed tasks for the Masters thesis (spring 2022)
* Continue unfinished project work.
* Improve method by introducing considerations on passenger comfort and the Convention on the International Regulations for Preventing Collisions at Sea (COLREGs).
* Make preparations for and conduct full-scale experiments with milliAmpere and/or milliAmpere 2 in Trondheim harbor.
* Write report.

## Contact
Write a short email where you explain your motivation for this task as well as about your background, and send it to [Morten Breivik] and  [Emil Thyri]. We will then arrange a Teams meeting with you to discuss the task.

## References
* Thyri, E.H. (2019): “[A Path-Velocity Decomposition Approach to Collision Avoidance for Autonomous Passenger Ferries](https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2625711)”, MSc thesis, NTNU. 
* Thyri, E.H. (2020): “[A Path-Velocity Decomposition Approach to Collision Avoidance for Autonomous Passenger Ferries in Confined Waters](https://www.sciencedirect.com/science/article/pii/S240589632031884X)”, in 2020, 21th IFAC World Congress, Berlin Germany.  


[Morten Breivik]: https://www.ntnu.no/ansatte/morten.breivik
[Emil Thyri]: https://www.ntnu.no/ansatte/emil.h.thyri
[Bjørn-Olav Holtung Eriksen]: https://www.ntnu.edu/employees/bjorn-olav.holtung.eriksen
[telia video]: {{site.url}}/assets/telia_video_snip.png
[TTK4190 Fartøysstyring]: https://www.ntnu.edu/studies/courses/TTK4190#tab=omEmnet
[Autoferry project]: https://www.ntnu.edu/autoferry