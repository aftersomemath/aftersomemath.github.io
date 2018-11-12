---
layout: page
title: Mission 7 of the International Aerial Robotics Competition
# description: a project with a background image
img16x9: /assets/img/iarc-target-crop.gif
current: false
permalink: /projects/iarc-mission-7/
---

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/0w_acYpwZiE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>
<div class="col three caption">
    IARC 2018 qualification demonstrating autonomous interaction with a moving target
</div>

I was a co-lead and core technical contributer to the Pitt's <a href="http://www.aerialroboticscompetition.org/">International Aerial Robotics Competition</a> (IARC) in 2017 and 2018. As summarized on the <a href="http://pittras.org/projects/IARC/">Pitt RAS project page</a>. "The IARC is an annual competition requiring teams to develop aerial robots that solve problems on the cutting edge of what is currently achievable by any aerial robots, whether owned by industry or governments. Mission 7 involved developing an autonomous drone capable of interacting with randomly moving robots on the ground to direct them towards a goal".

In 2017 the team had the Most Points and won Best System Design at the American Venue. In 2018, the team repeated these succeses and also received the Best Technical Paper award. <a href="http://www.aerialroboticscompetition.org/mission7.php">Mission 7</a> was completed by Zhejiang University in 2018 at the Asian-Pacific venue.

<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/drone-image.jpg" alt="" title="IMU System Overview"/>
</div>
<div class="col three caption">
    The 2018 Competition Drone containing a Jetson TX2, Intel NUC6i7KYK NUC, 5 Intel Realsense Cameras, 1 global shutter cameras, KDE direct propulsion system, and lots of batteries.
</div>

The team produced substantial software, hardware, and electronics as over 30 students contributed to create an entirely custom UAV. Many major systems including flight control, obstacle detection, and computer vision algorithms were specially designed for this mission. ROS and OpenCV were used extensively; over 10 ROS packages were created along with numerous ROS nodes.

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/su-1Q3NBxsQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>
<div class="col three caption">
    IARC 2018 footage where obstacle avoidance and remaining within arena boundaries was demonstrated
</div>

At home the team demonstrated target interaction, obstacle avoidance, navigation, and control using the custom software stack. At competition in 2018 everything except target interaction was demonstrated. Technical gremlins (primarily lighting problems) wreaked havoc on the last days of testing making it impossible to test target interaction in the final days.

# Main Personal Contributions
My work focused on controls and state estimation, however I was involved in electronics and mechanical design as well. The subsystems I focused on are listed below. For more details, the appropriate section of the <a href="http://pittras.org/projects/iarc/2018/08/10/update-iarc-technical-postmortem.html">Technical Postmortem</a> is linked.

## Controller and Optical Flow Plot
<div class="img_row">
    <a href="{{ site.baseurl }}/assets/img/iarc-controller.png" target="_blank">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/iarc-controller.png" alt="" title="IARC Controller and Flow Performance"/>
    </a>
</div>
<div class="col three caption">
    Click on the image to enlarge<br/>
    Graph showing controller and flow estimation performance when flying a 2 meter square formation<br/>
    Legend is at the top right, the X axis is in seconds, Y axis is in meters, meters/sec, or meters/sec^2 as appropriate<br/>
</div>

The overall performance of the control and estimation systems described below are shown in the above figure. It depicts achivement of X and Y position and velocity targets, estimates of velocity and position from the kalman filter, and raw estimates of flow coming from the optical flow estimator.

## Controls
### Time Variant, Non-linear Rotor Thrust Modeling
<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/controller-plot.png" alt="" title="Thrust Model Visualized"/>
</div>
<div class="col three caption">
    Visualized model showing possible ending thrusts based on an applied voltage and a given starting thrust
</div>

Operating a 5 kg UAV quickly required an accurate model of the propulsion system. A innovative method was created which allows for accurate predicions to be made in an open loop manner using presolved discretized models. <a href="http://pittras.org/projects/iarc/2018/08/10/update-iarc-technical-postmortem.html#dynamic-thrust-model" target="_blank">Technical Postmortem Section</a>

This model was discussed in the *6 Degree of Freedom UAV Thrust Model Summary* available on the <a href="/publications/">publications page</a>.

### Motion Profile Controller
<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/iarc-SingleAxisController.png" alt="" title="Controller for a single axis"/>
</div>
<div class="col three caption">
    Controller Design Diagram
</div>
In order to support a responsive interactions with moving targets, a custom linear controller was created. Due to the accuracy of the thrust model used, it was possible to specify acceleration setpoints directly. This was crucial for accurately and repeatedly interacting with the moving targets. <a href="http://pittras.org/projects/iarc/2018/08/10/update-iarc-technical-postmortem.html#motion-profile-controller" target="_blank">Technical Postmortem Section</a>

<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/iarc-target.gif" alt="" title="2018 Drone Target Touch"/>
</div>
<div class="col three caption">
    The 2018 Competition Drone autonomously making contact with a moving target.
</div>

### Flight Controller
A cleanflight based flight controller was used. This was contrary to the conventional wisdom of using a Pixhawk with either PX4 or Ardupilot. However, this decision allowed us to use custom controller more suited to the IARC Mission 7. <a href="http://pittras.org/projects/iarc/2018/08/10/update-iarc-technical-postmortem.html#flight-controller" target="_blank">Technical Postmortem Section</a>.

## State Estimation
### Texture Classification for Boundary Detection
<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/arena-detector.gif" alt="" title="Texture Classification Demo"/>
</div>
<div class="col three caption">
    An early test of the texture classification system.
</div>

In order to remain within arena boundaries, a method of detecting areas as outside of an arena was required. A texture classifier was created using Tensorflow for this purpose. <a href="http://pittras.org/projects/iarc/2018/08/10/update-iarc-technical-postmortem.html#arena-boundary-detection" target="_blank">Technical Postmortem Section</a>

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/9l7DOeNJ3So" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>
The above video shows the UAV using the boundary detector to "bounce off walls" similar to an old-fahsioned screensaver.

### Optical Flow
<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/optical-flow.gif" alt="" title="Optical Flow Demonstration"/>
</div>
<div class="col three caption">
    (Left) Visualization of the optical flow technique used to estimate the drones velocity<br/>
    (Right) Visualization of statistical filter used to filter flow vectors
</div>
A custom velocity estimation system was implemented using OpenCV’s implementation of Lucas-Kanade optical flow with pyramids. It was coupled with a statistical filter  which detected outliers based on the variance of the two dimensional distribution of the flow vectors. The technique allowed vectors to be ignored that were known to be on the top of moving targets.

The flow estimated was combined with other sensors in an EKF (<a href="http://wiki.ros.org/robot_localization">robot localization</a>), a few minutes a flying would only result in approximately one meter of drift. Velocity estimates were within accurate to within 5 cm/s. <a href="http://pittras.org/projects/iarc/2018/08/10/update-iarc-technical-postmortem.html#optical-flow">Technical Postmortem Section</a>

## Electronics
### 30V 30A eight channel DC Circuit Breaker Safety System for 6DOF UAV
<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/30A-eight-channel-breaker.png" alt="" title="30V 30A eight channel DC Circuit Breaker"/>
</div>
<div class="col three caption">
    An eight channel 30V, 30A circuit breaker designed for emergency power removal
</div>
A 7 kg 6 DOF UAV was designed and built, however software did not have time to make the transition to the new airframe for the 2018 competition. The above circuit breaker was designed and built for this UAV. <a href="http://pittras.org/projects/iarc/2018/08/10/update-iarc-technical-postmortem.html#6-degree-of-freedom-uav">Technical Postmortem Section</a>
