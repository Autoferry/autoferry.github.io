---
layout: post
title: Simulation-based evaluation of collision avoidance methods for autonomous ferry scenarios.
category: COLAV
---
## Background
Mission-planing, collision avoidance, navigation and control systems for autonomous marine vessels are fields that currently receive much attention. This is driven by the growing interest from industry that see the economical potential in replacing existing non-autonomous maritime traffic with more autonomous solutions, in addition to new emerging markets that are enabled by the new technology. For any of this to be a reality, the autonomous systems that are developed need to be tested and evaluated to a degree where they are provably as safe or safer than non-autonomous systems. Since such extensive testing through full scales sea-trials is exhausting and expensive, in addition to that several test-scenarios are impossible to perform without too high risk of damage, a major part of this evaluation and validation needs to be performed through simulations. 

For such simulation based validation to be effective, the simulator needs to provide a representative representation of the real-world environment that the autonomous system is to operate in. For autonomous systems designed to work anywhere, this can be impossible, but for autonomous systems operating in a confined location, this is an achievable task. Examples of this is autonomous passenger- and car-ferries, that operate between two or more fixed locations within a small area. For such operations, it is possible to gather sufficient information about the operational area to recreate a representative model in a simulator, and thereby evaluate and validate an autonomous guidance system for operation in that specific environment. 

|<img src="{{site.url}}/assets/kristiansund_with_example_transits.png" width="310"> |
|Kristiansund is an interesting use-case since it has the "Sundbåten" connecting the four parts of the city along the transits in green. The city has some big ships like the "Hurtigrute" that travel along the red lines, and a lot of leisure vessels, with blue lines as examples transit lanes.|

## Problem Formulation
This tasks concerns setting up representative simulation environments for testing autonomous ferry operations, both in urban and rural locations. This includes defining some (3-4) use-cases to consider. Suggestions are
* Kristiansund with the "Sundbåt"
* Trondheim with the ravnkloa-Brattøra transit,
* Tønsberg with an urban city ferry and 
* the Horten-Moss car-ferry transit. 

Once the use-cases are defined, the candidate should gather enough relevant information about the areas to be able to recreate the relevant activities  in the simulator. This might include; analyzing AIS data, nautical maps, commercial traffic and "rutetabeller", calling up local harbour authorities, field-trips for data gathering etc. The simulator should be made to represent nominal conditions in addition to extreme cases with some randomness. 

The simulator should be augmented to emulate a model of a situational awareness system. This includes looking into different sensor packages and configurations in terms of field-of-view, range and fidelity, to make a model with an interface that provides detection and tracking data of the same quality as can be expected by a a variety of state of the art situational awareness system. This is essential for determining a guidance and COLAV systems requirements to the situational awareness system. 

The simulator should also include vessel-to-vessel interactions in a accordance with COLREGs. This can be 

To aid the evaluation, the candidate should implement evaluation metrics of the type described in (Woerner 2016) and (Nakamura & Okada 2019). These are metrics designed to evaluate COLREGs compliance. Metrics for evaluating passenger comfort, i.e. based on acceleration and yaw rate,  should also be implemented.

Both under development and when the simulator is complete, the candidate should use it to test one or more COLAV algorithms in both single-situation and long-duration operation The objective of the task is to either validate (or at-least provide some assurance) or find the shortcoming of a guidance and COLAV system for autonomous operation in a specific environment.


## Prerequisites
This work is a combination of both theory and practice. The task is open to creative solutions and the candidate should therefore be motivated to do work both independently and discuss problems/solutions with the supervisors. Subjects within guidance and control of marine vessels is advantageous, but not a requirement.


|<img src="{{site.url}}/assets/milliAmpere_sea_trials.png" width="450"> |
|The experimental platform milliAmpere during testing in Trondheim harbor.|

## Proposed Tasks for the 5th year project
* Define 3-4 use-cases to consider
* Gather information about the use-case environment e.g. map-data, traffic patterns, etc. 
* Implement a simulator with logical interfaces for testing an autonomous guidance system.
* Use the simulator to evaluate one or more autonomous guidance systems with COLAV functionality in the defined use-cases.
* Write report.

## Proposed Tasks for the Masters Thesis
* Continue unfinished work from project thesis.
* Evaluate the performance of the simulator, by doing a manual evaluation of situations and compare it to the implemented metrics. Suggest and implement improvements to the metrics if needed. 
* Include situational awareness emulation.
* Based on the progress, the candidate along with the supervisors will define more tasks.
* Write masters thesis.

## Contact

Kontakt: [Morten Breivik] and [Emil Thyri]

[Morten Breivik]: https://www.ntnu.no/ansatte/morten.breivik
[Emil Thyri]: https://www.ntnu.no/ansatte/emil.h.thyri
## References

* Woerner, K. (2016): “[Multi-contact protocol-constrained collision : avoidance for autonomous marine vehicles]”, PhD Thesis, Massachusetts Institute of Technology.
*Nakamura, S., & Okada, N. (2019, March): “[Development of AUtomatic Collision Avoidance System and  Quantitative  Evaluation  of  the  Maneuvering  Results.]”, in International  Journal  on  Marine Navigation and Safety of Sea Transportation, 13(1), 133-141.
