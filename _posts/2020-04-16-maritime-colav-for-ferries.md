---
layout: post
title: Trajectory planning and collision avoidance for autonomous passenger ferries
category: COLAV
---
## Background
The concept of small autonomous passenger ferries in urban areas is a more flexible and environmentally-friendly alternative to bridges or manned ferries. NTNU's [Autoferry project] therefore aims to develop groundbreaking new concepts and methods which will enable the development of such ferries for urban water transport.

As part of this, NTNU has developed the ferry prototype “milliAmpere”, which is a 5 meter long prototype for testing technology enabling small passenger ferries for urban environments. The milliAmpere platform runs an on-board computer with Ubuntu and robot operating system (ROS) which makes it simple to interface new algorithms with the existing systems on the ferry for full scale experiments and testing.

[![telia video]](https://www.youtube.com/watch?time_continue=1&v=FuWedx0oLX4&feature=emb_logo)


In (Thyri 2019, 2020), a COLAV method for passenger ferries operating in urban environments is described. The method in short:
* The method inputs a predefined path that is collision free with any static obstacles, as well as tracking data on moving obstacles in proximity.
* A simplified obstacle representation is made for each obstacle. The representation can be made to consider COLREGs, obstacle size and velocity. Se left picture below.. 
* The obstacle representations are transformed onto the path, based on the assumptions that the obstacles keep constant heading and velocity. This gives a two-dimensional path-time space where the area spanned by the transformed obstacle representation represents that obstacle representations occupation of the path in time,  see middle picture below.
* A visibility-graph is constructed to connect the start of the path to the end of the path in a way that does not intersect the collision-regions of the transformed obstacle representation, see right picture below. 
* The graph is traversed with a graph search algorithm to find the minimum cost path, and a velocity-profile can be calculated from that path. 

|<img src="{{site.url}}/assets/laying_object_representation.png" width="310"> ||<img src="{{site.url}}/assets/path_time_obstacle_representation.png" width="310"> ||<img src="{{site.url}}/assets/vgraph_with_regions_of_collision.png" width="310"> |
|Simplified obstacle representation.||Transformation of four obstacle representations to path-time space.||Vgraph constructed in path time space. Red polygons indicate regions of collision. Graph is traversed to find a velocity profile.|

This method is simple, intuitive and predictable. It is tested trough simulations and full-scale experiments, and prove to work well in the situations it was designed for, which is confined waters and high traffic environments such as harbor and canal-areas.
Yet, it comes with some limitations. The method limits the maneuvering options, since the path is predefined and therefore only adapting the velocity is possible. This makes the method perform poorly in open waters, where changes in heading are preferable, since they are more visible.  This restriction also limits the ability to consider the International Regulations for Preventing Collisions at Sea (COLREGs), which are the "traffic rules" on water.

## Problem formulation

This task concerns developing a COLAV system that is based on or inspired by the concepts of the mentioned method, with the intention of improving on some of the limitations of the method. The author of (Thyri 2019, 2020) will be co-supervisor.

A suggested approach is to augment the method from (Thyri 2019, 2020) to input a transit area instead of a path, where the transit area contains the start and end-position of the transit and is free of any static obstacles. The moving obstacles can then be transformed onto a volumed spanned by the transit area and time. The moving obstacles will become cylinders in this volume. This volume can then be traversed by e.g. constructing a directed visibility graph in 3D and searching it with Dijkstra.
This will allow for changes in both heading and velocity, and facilitates more COLREGs compliant maneuvering, in addition to increased safety and passenger comfort. 

## Prerequisites
This work is a combination of both theory and practice.  The candidate should therefore favour both theoretical and experimental work. Subjects within guidance and control of marine vessels such as [TTK4190 Fartøysstyring] is advantageous, but not a requirement.



## Proposed tasks for the 5th year project
* Get familiar with the concepts of the velocity-planner that is described in (Thyri 2019, 2020). 
* Formulate an approach to expanding the path-time method to an area-time method. This will be done with support from the supervisors.
* Implement the method. Start of with the simplest implementation and build from there. 
* Evaluate and show proof of concept of the method through simulations.
* Write report.

## Proposed tasks for the Masters thesis
* Continue unfinished project work.
* Improve method by introducing passenger comfort and COLREGs considerations.
* Make preparations for and conduct full-scale experiments in Trondheim harbor.
* Write report.

## Contact
Write a short email where you explain your motivation for this work as well as about your background, and send it to [Morten Breivik], [Emil Thyri] and [Bjørn-Olav Holtung Eriksen]. We will then arrange a Skype meeting with you to discuss the task.


## References
* Thyri, E.H. (2019): “[A Path-Velocity Decomposition Approach to Collision Avoidance for Autonomous Passenger Ferries](https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/2625711)”, MSc thesis, NTNU. 
* Thyri, E.H. (2020): “[SA Path-Velocity Decomposition Approach to Collision Avoidance for Autonomous Passenger Ferries in Confined Waters] in 2020, 21th IFAC World Congress, Berlin Germany, in press.  


[Morten Breivik]: https://www.ntnu.no/ansatte/morten.breivik
[Emil Thyri]: https://www.ntnu.no/ansatte/emil.h.thyri
[Bjørn-Olav Holtung Eriksen]: https://www.ntnu.edu/employees/bjorn-olav.holtung.eriksen
[telia video]: {{site.url}}/assets/telia_video_snip.png
[TTK4190 Fartøysstyring]: https://www.ntnu.edu/studies/courses/TTK4190#tab=omEmnet
[Autoferry project]:https://www.ntnu.edu/autoferry