---
title: "Air Pollution Monitoring With Mobile Robots"
layout: post
toc: false
image: "images/paper/system.png"
---

_Here, I want to briefly present some ideas from my first research paper [1]. My intention is that even my blue-collar parents would get a basic understanding of the research topic, even though they’d have to rely on DeepL.com for translation – sorry! ;-)_

![]({{ site.baseurl }}/images/paper/system.png)

## Air Pollution Affects Us All
Thanks to our major car manufacturers and _Dieselgate_, we all know that air pollution is a major risk. In fact, more than 400,000 premature deaths are linked to air pollution – and that’s only in the European Union! According to the WHO, more than seven million people worldwide are killed by polluted air. Nine out of ten people breathe air that exceeds the WHO’s guidelines. This means that diesel cars are only a small part of the problem. Air pollution has to be tackled in many different areas and I will focus on the area of occupational health. Especially industry workers – hello, dad! – are exposed to toxic gases and dust particles that are harmful to the human body.

For the sake of simplification, let’s imagine a steel factory:
![]({{ site.baseurl }}/images/paper/factory-workers.png)

Here we see some workers and also an area of polluted air. Polluted air may consist of dust particles or gases that emerge during industrial processes in the factory. To minimize the impact of air pollution on our workers, we have to reduce the concentration of toxic particles (e.g., by adapting the factory’s ventilation system) or at a minimum reduce the time our workers are exposed to these hazardous spots. The latter would be particularly easy in the example above.
## Approaches for Environmental Monitoring
In reality, however, we have the problem that we don’t really know where these highly polluted areas actually are. Since airborne particles are distributed by underlying physical processes (e.g., advection and diffusion), predicting the distribution of air pollutants is no trivial task. Health experts who try to estimate the health risks for workers can typically only take measurements at one location each time. During their measurement campaign, they may cover different locations, but in the end, they have information of varying recency – and for many areas, they don’t have any measurements at all. On top of that, a human health expert cannot monitor the factory 24/7. Typically, the exposition of a worker is estimated based on single-day campaigns. Seasonal effects like weekends or intermediate increased production volume can only partly be taken into account. The takeaway is: Even with expert knowledge it is not always possible to get a precise understanding of the spatial and temporal distribution of air pollutants.
![steel factory](/images/factory-expert.png)
What’s the best approach to get a precise understanding of the distribution of air pollutants in a given area? The boring, scientific answer is: we don’t know. But we have some ideas. Our idea is a combinatory system that consists out of stationary sensors and mobile robots. The system is coined RASEM (Robot-assisted Environmental Monitoring for Air Quality Assessment in Industrial Scenarios) after the same-named European funded research project [2]. The hardware system consists of the following two pillars:
### Stationary Sensing Nodes
Multiple stationary sensing nodes form a wireless sensor network. A single sensing node consists of sensors for temperature, humidity, dust, and gas. Here, we are using very low-cost sensors to achieve unit costs below 300 € per node. This enables us the continuous monitoring of environmental parameters at different locations. The more nodes we set up, the better is our rough understanding of the overall concentration levels.
### Mobile Robots
We are using ground and aerial robots that are equipped with high-quality sensors. With the robots, we can collect data in areas that are not covered by the stationary sensors.  We can also cross-calibrate the low-cost sensors with the high-quality sensors.
## Reducing Health Risks by Making Sense Out of Data
Getting the data is only one part of the process. The end result should be to minimize the health risks for humans by developing effective mitigation measures. To enable this, we aim to develop algorithms that create 3D distribution maps of air pollutants. These maps shall visualize, how specific air pollutants are distributed in the factory overtime.

Of course, this is already an active research field and different approaches for this problem exist. So-called _Gaussian processes_ are widely used to represent the distribution of pollutants. Researchers have proven that mobile robots, stationary sensor networks, or the combination of both yield good results for this task. Recent research also tries to leverage advances in the field of machine learning.

With our RASEM system, we aim to develop novel algorithms to predict the distribution of dust and gases at unknown locations. One potential that comes into mind is the incorporation of additional information into a model. Most models are primarily data-driven, which means their prediction is mainly based on the immediate input data. In contrast, whenever we humans perform predictions, we make heavy use of our _intuition_. We just _know_ that we can’t move through walls, because we learned this the hard way a long time ago (an except may be if you’re delivered a Hogwarts acceptance letter by owl post around your eleventh birthday, but then you’re out of the scope of this blog). Likewise, the performance of a model could be improved significantly, if an intuition on the relevant physics is incorporated into it. Better predictions of the distribution of air pollutants could be made by inputting not only sensor measurements, but also information on industrial processes (e.g., how often and how long a specific industrial process occurs) or the environment (e.g., how the factory looks like and which areas are used for what).

![]({{ site.baseurl }}/images/paper/factory-system.png)

In the upcoming year, we are going to evaluate the proposed system under real conditions at industrial sites in Finland. With our project, which is a cooperation of diverse research institutes and industrial partners, we aim to generate new knowledge that can eventually contribute a small part to the global risk of air pollution.

## References
[1] NP Winkler, PP Neumann, A Säämänen, E Schaffernicht, AJ Lilienthal: High-quality meets low-cost: Approaches for hybrid-mobility sensor networks, Materials Today: Proceedings, Volume 32, Part 2, 2020, Pages 250-253, DOI: [https://doi.org/10.1016/j.matpr.2020.05.799](https://doi.org/10.1016/j.matpr.2020.05.799).

[2] [https://projects.safera.eu/project/20](https://projects.safera.eu/project/20)