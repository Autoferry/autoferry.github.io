---
layout: post
title: Multivariate modeling and control of autonomous ferries
category: COLAV
---

The concept of small autonomous passenger ferries in urban areas is a more flexible and environmentally-friendly alternative to bridges or manned ferries. Autoferry therefore aims to develop groundbreaking new concepts and methods which will enable the development of such ferries for urban water transport.

As part of this, NTNU has developed the ferry prototype "milliAmpere", which is a 5 meter long prototype for testing technology enabling small passenger ferries for urban environments. Extensive research has been done on milliAmpere the recent years, and a new full-scale version is currently under construction, which will be used for a ferry crossing between Ravnkloa and Fosenkaia.

![milliAmpere]{:width="450px"}

The milliAmpere ferry is equipped with batteries, two azimuth thrusters, navigation sensors and a control system. In addition, the ferry can be equipped with a lidar, cameras and a radar in order to detect obstacles such that an autonomy system can avoid obstacles when crossing the canal. In addition to algorithms interpreting sensor data and planning collision-free paths, a control system which can steer the ferry on a given path is required. When developing such a control system, it is beneficial to have an accurate model of the ferry. Previously, a 3DOF model of the ferry has been identified, but this model neither captures all the dynamics of the vessel or has perfect parameter values.

In this project proposal, you will develop methods for multivariate modeling and identification in order to capture dynamics not covered by the existing ferry model. This involves multivariate analysis of residuals in order to select both basis functions and parameter values. This work was initiated in 2019, and you will build upon existing work on the topic.

Proposed tasks:

* Get familiar with the existing work done on multivariate modeling on milliAmpere
* Perform a literature study on alternative approaches
* Perform simulations to assess the robustness of the modeling and identification approach. This should include simulations with external disturbances, model changes and measurement noise.
* Implement the algorithms on milliAmpere and test the approach in experiments

It is desirable to continue the work in a Masters Thesis.

Kontakt: [Morten Breivik] and [Bjørn-Olav H. Eriksen]

[Morten Breivik]: https://www.ntnu.no/ansatte/morten.breivik
[Bjørn-Olav H. Eriksen]: https://www.ntnu.no/ansatte/bjorn-olav.holtung.eriksen
