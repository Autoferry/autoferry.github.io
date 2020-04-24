---
layout: post
title: Autonomous supervisory control of ferry crossing
category: COLAV
---

## Background

The concept of small autonomous passenger ferries in urban areas is a more flexible and environmentally-friendly alternative to bridges or manned ferries. Autoferry therefore aims to develop groundbreaking new concepts and methods which will enable the development of such ferries for urban water transport.

As part of this, NTNU has developed the ferry prototype "milliAmpere", which is a 5 meter long prototype for testing technology enabling small passenger ferries for urban environments. Extensive research has been done on milliAmpere the recent years, and a new full-scale version is currently under construction, which will be used for a ferry crossing between Ravnkloa and Fosenkaia.

|<img src="{{site.url}}/assets/milliampere.jpg" width="450"> |
|The experimental platform milliAmpere during testing in Trondheim harbor.|

|[<img src="https://img.youtube.com/vi/FuWedx0oLX4/0.jpg" width="450">](https://www.youtube.com/watch?v=FuWedx0oLX4) |
|milliAmpere is fitted with 5G technology from Telia. The above imange links to a promo video from Telia.|

The milliAmpere ferry is equipped with batteries, two azimuth thrusters, navigation sensors and a control system. In addition, the ferry can be equipped with a lidar, cameras and a radar in order to detect obstacles such that an autonomy system can avoid obstacles when crossing the canal.

## Problem formulation

The project is related to the full-scale version of milliAmpere, where a DP system will be used to perform low-level control on the ferry which the autonomy system interfaces.

A high-level supervisory controller is necessary as part of the autonomy system. The controller should automatically make the necessary reconfiguration and fault mitigation in the event of equipment failure or other hazards. This includes selection of equipment such as thrusters and sensors where there is redundancy, in order to provide fault tolerance. It also includes the identification of hazardous conditions where emergency shutdown or emergency responses are needed, and execution of the necessary functions. The system should also monitor the performance of dynamic positioning, maneuvering, docking and anti-collision systems.

The project will focus on algorithm development and simulation, while a continuation into a master thesis project will focus on real-time implementation and experimental testing.

### Contact

Contact: [Tor Arne Johansen] and [Bjørn-Olav H. Eriksen]

[Tor Arne Johansen]: https://www.ntnu.no/ansatte/tor.arne.johansen
[Bjørn-Olav H. Eriksen]: https://www.ntnu.no/ansatte/bjorn-olav.holtung.eriksen
