---
layout: page
title: Desktop Model for HITL Simulation of CubeSat Mission Objectives
# description: a project with a background image
img: /assets/img/hacksat-gimbal-crop.gif
current: false
permalink: /projects/hitl-cubesat/
---

This project started in August of 2018 with the goal of working towards an academic constellation of free-flying CubeSats. A gimbal mounted CubeSat model containing representations of expected hardware was designed to enable rapid software iteration and testing. Usage would help minimize risks associated with first-time academic CubeSat programs because it reduces difficutly in performing in unit, functional, and system testing of software.

The CubeSat model included a Raspberry Pi and Teensy 3.2 for simulating the interaction between a microcontroller and more powerful computer. The control board contained support for three reaction wheels with encoders and current sensing. It also featured a 9-axis IMU and temperature sensor. The system was powered via a 2 cell 1.5 Ah LiPo battery.

Basic functionality of the hardware was achieved and interaction between the physical model and a running instance of <a href="https://software.nasa.gov/software/GSC-16720-1">42</a> (an open-source general purpose flight software developed at NASA) was demonstrated. The hastily designed gimbal proved too resistant and quickly caused saturation of the reaction wheels. Future work looks to move the model into a sphere that can float in a small pool of water.

This project was part of a collaboration with Christopher Manderino, a student working under Dr. Alan George at the <a href="https://nsf-shrec.org/">NSF Center for Space High-Performance and Reconfigurable Computing</a>.

<div class="img_row">
    <img class="col one left" src="{{ site.baseurl }}/assets/img/hacksat-gimbal-crop.gif" alt="" title="CubeSat gimbal"/>
    <img class="col one left" src="{{ site.baseurl }}/assets/img/hacksat-in-gimbal.jpg" alt="" title="CubeSat model mounted in gimbal"/>
    <img class="col one left" src="{{ site.baseurl }}/assets/img/hacksat-render1.jpg" alt="" title="CubeSat model without frame"/>
</div>
<div class="col three caption">
	(Left) Early prototype gimbal to hold the CubeSat model<br/>
	(Center) Model CubeSat replica to be mounted in the gimbal<br/>
	(Right) Model CubeSat with frame removed to show custom electronics hardware.
</div>
