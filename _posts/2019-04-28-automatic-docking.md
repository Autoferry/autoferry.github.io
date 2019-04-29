---
layout: post
title: Energy-optimized automatic docking for ferries
category: COLAV
---

![Docking illustration]{:width="450px"}

For a given ferry connection, a ferry may dock up to 20 times every day.
For the ship's operators this can be a challenging, stressful and time-consuming task.
Difficulties may arise from external variables such as weather conditions or harbor layout, or from internal conditions such as stress.
Often the ship's operators have to restart the docking procedure after a failed attempt, causing delays and increase in fuel consumption.
Regular accidents also occur which damage the harbor or the ferry itself.

Kongsberg Maritime (KM) have developed a solution for automatic docking of _Bastø VI_, one of the ferries servicing the Horten--Moss connection, run by _Bastø Fosen_.
The main benefit of performing automatic docking is to have a repeatable docking procedure which is consistent in both duration and energy consumption.
KM's solution implements several criteria posed by _Bastø Fosen_, including speed limits at certain distances from the berthing point.
These criteria are the safety margins that allow for manual takeover in cause of failure.
Another important aspect to automatic docking is graphical representation of intent and status for the ship's operators.

We propose a project and master's thesis that consider developing an energy-optimized trajectory planner for automatic docking.
This trajectory planner must account for any safety criterion related to the docking procedure, and must try to obtain an energy-optimized trajectory.
The candidate will perform a literature study which includes path and trajectory planning, optimization theory and solutions, ship modeling and control.
The candidate should be familiar and comfortable with both ship modeling and optimization.
It is advantageous that the candidate has completed [TTK4135] and [TTK4190].

![milliAmpere]{:width="450px"}

We propose the following tasks:
* Perform background research and a literature study of ship modeling, optimization, path planning and trajectory planning
* Study and evaluate safety criteria for docking procedures
* Implement a simulation framework for testing ship controllers, trajectory planners and docking scenarios
* Implement (and develop) controllers for low-speed trajectory tracking
* Develop and implement graphical tools that show the ship's intent and deviations from the planned trajectory.
* Develop and implement one or more methods for energy-optimized trajectory planning for automatic docking
* Test the trajectory methods in simulation
* Perform experiments on a model ship (e.g. milliAmpere, depicted above)
* Measure performance in terms of computational requirements, safety margins, energy consumption and travel time
* Evaluate whether optimization-based trajectory planners are feasible for use in automatic docking

There is a possibility that the candidate will cooperate closely with KM.

Supervisors: [Morten Breivik] and [Glenn Bitar]

[Docking illustration]: {{site.url}}/assets/horten-docking.png
[milliAmpere]: {{site.url}}/assets/milliampere.jpg
[TTK4135]: https://www.ntnu.edu/studies/courses/TTK4135
[TTK4190]: https://www.ntnu.no/studier/emner/TTK4190
[Bitar2017]: http://hdl.handle.net/11250/2465617
[Morten Breivik]: https://www.ntnu.no/ansatte/morten.breivik
[Glenn Bitar]: https://www.ntnu.no/ansatte/glenn.bitar
