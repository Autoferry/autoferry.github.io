---
layout: post
title: Multivariate modeling and adaptive control of autonomous ferries
category: COLAV
---

## Background

The concept of small autonomous passenger ferries in urban areas is a more flexible and environmentally-friendly alternative to bridges or manned ferries. NTNU's [Autoferry](https://www.ntnu.edu/autoferry) project therefore aims to develop groundbreaking new concepts and methods which will enable the development of such ferries for urban water transport.

As part of this, NTNU has developed the ferry prototype "milliAmpere", which is a 5 meter long prototype for testing technology enabling small passenger ferries for urban environments. Extensive research has been done on milliAmpere the recent years, and a new full-scale version is currently under construction, which will be used for a ferry crossing between Ravnkloa and Fosenkaia.

|<img src="{{site.url}}/assets/milliampere.jpg" width="450"> |
|The experimental platform milliAmpere during testing in Trondheim harbor.|

|[<img src="https://img.youtube.com/vi/FuWedx0oLX4/0.jpg" width="450">](https://www.youtube.com/watch?v=FuWedx0oLX4) |
|milliAmpere is fitted with 5G technology from Telia. The above imange links to a promo video from Telia.|

The milliAmpere ferry is equipped with batteries, two azimuth thrusters, navigation sensors and a control system. In addition, the ferry can be equipped with a lidar, cameras and a radar in order to detect obstacles such that an autonomy system can avoid obstacles when crossing the canal. In addition to algorithms interpreting sensor data and planning collision-free paths, a motion control system which can steer the ferry on a given path is required. When developing such a control system, it is beneficial to have an accurate model of the ferry. Previously, a 3DOF model of the ferry has been identified, but this model neither captures all the dynamics of the vessel or has perfect parameter values.

## Problem formulation

In this project proposal, you will develop methods for modeling, identification and adaptive control based on the [big-data cybernetics (BDC)](https://www.tekna.no/fag-og-nettverk/IKT/ikt-bloggen/stordata-kybernetikk) pipeline in order to capture dynamics not covered by the existing ferry model. This involves multivariate analysis of residuals in order to select both basis functions and parameter values. You will build upon existing work that started in 2019.

Proposed tasks:

* Get familiar with the existing work done on modeling and adaptive control for milliAmpere
* Perform a literature study on alternative approaches
* Perform simulations to assess the robustness of the modeling, identification and adaptive control approach. This should include simulations with external disturbances, model changes and measurement noise.
* Implement the algorithms on milliAmpere and test the approach in full-scale experiments in Trondheim harbor

It is desirable to continue the work in a Masters Thesis for the spring of 2021.

### Prerequisites

The following courses are recommended, but not mandatory:  

* [TTK4190 Fartøysstyring](https://www.ntnu.no/studier/emner/TTK4190)
* [TTK4260 Innføring i multivariat datamodellering](https://www.ntnu.no/studier/emner/TTK4260)

The candidate should also have good practical skills, as the project involves practical implementation and testing of the system.

### Contact

Write a short email where you explain your motivation for this work as well as about your background, and send it to: [Morten Breivik] and [Bjørn-Olav H. Eriksen]

We will then arrange a Skype meeting with you to discuss the task.

[Morten Breivik]: https://www.ntnu.no/ansatte/morten.breivik
[Bjørn-Olav H. Eriksen]: https://www.ntnu.no/ansatte/bjorn-olav.holtung.eriksen
