---
layout: post
title: Automatic practical path planning for autonomous ships
category: COLAV
---

![map]{:width="450px"}

Today ship routes are manually planned by a navigator.
This is a time consuming task is desirable to automate.
In addition to saving time spent on planning, an automatic planner may optimize the route with respect to different criteria, such as energy usage, time, weather conditions and distance from land.
However, there are several constraints placed on sailing routes.
Such a route has to be ECDIS compatible, it has to be possible to sail the route by optical navigation with help from e.g. lighthouses, and it must comply with traffic separation schemes.

A groundwork has already been carried out that interprets digital sea charts and weather data into a representation that is possible to use in route planning methods.
Some methods for automatic route planning have also been developed.
As a proposal for a project and master thesis, it is desirable that a candidate further develops the framework for automatic route planning, and implements methods that both maintain the practical requirements and optimize on given criteria.
This will involve simulated sailing of the planned routes to measure performance.

Some task suggestions are:

* Perform a literature study that deals with maritime navigation and route planning, route planning algorithms such as A\*, Voronoi diagrams and the like, as well as optimization.
* Study the work that has been carried out on the framework for interpreting digital charts and weather data.
* Further develop this framework as needed.
* Develop and test route planning algorithms that comply with the requirements for sailing, and optimize on said criteria.
* Simulate sailing of the planned routes to measure and compare performance.

It is advantageous if the candidate is comfortable with mathematical ship models, optimization or other related topics.

There is a possibility that the candidate will work closely with Kongsberg Maritime.

Supervisors: [Morten Breivik] and [Glenn Bitar]

[map]: {{site.url}}/assets/navigation-map.png
[milliAmpere]: {{site.url}}/assets/milliampere.jpg
[TTK4135]: https://www.ntnu.edu/studies/courses/TTK4135
[TTK4190]: https://www.ntnu.no/studier/emner/TTK4190
[Bitar2017]: http://hdl.handle.net/11250/2465617
[Morten Breivik]: https://www.ntnu.no/ansatte/morten.breivik
[Glenn Bitar]: https://www.ntnu.no/ansatte/glenn.bitar
