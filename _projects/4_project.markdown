---
layout: page
title: Wearable Sensing System to Estimate Lower Limb State
# description: a project with a background image
img16x9: /assets/img/imu-system.png
current: false
permalink: /projects/wearable-imu-limb-angle-estimation/
---

Completed in the Summer of 2017, this project used used 6 IMU's to estimate lower limb state. The wearable system was designed to support research in using functional electrical stimulation to correct gait abnormalities such as drop foot.

A peer-reviewed paper was written for *Ingenium: Undergraduate Research Undergraduate Research at the Swanson School of Engineering*. Citation available <a href="/publications/">here</a>.

# Synopsis

A custom embedded system was made to interface with six MPU9250 IMU's with a 1 khz update rate. The system included a Raspberry Pi, microcontroller, custom circuit boards, and substantial supporting software. Additionally a commerical Functional Electrical Stimulation Device was interfaced with the system. Sensor data could be forwarded through Wi-Fi in real-time for processing by simulink or a ROS application.

<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/imu-system.png" alt="" title="IMU System Overview"/>
</div>
<div class="col three caption">
    Main system components
</div>


For a validation of the system a basic limb-angle estimation algorithm was designed using 6 instances of the popular <a href="http://x-io.co.uk/open-source-imu-and-ahrs-algorithms/">Madgwick Filter</a>. The following plot shows the results of a user taking a single (slow) step.

<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/imu-plot.png" alt="" title="Plot of the limb angles measured by the limb angle estimation system"/>
</div>
<div class="col three caption">
    Plot of the limb angles measured by the limb angle estimation system over the course of one step
</div>
