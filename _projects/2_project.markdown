---
layout: page
title: UAV with 6 Controllable Degrees of Freedom (Capstone Project)
# description: a project with a background image
img16x9: /assets/img/6dof-right.gif
---

My senior capstone project was constructing a 6 degree-of-freedom UAV with Long Vo, Liam Berti, and Ritesh Misra. The project achieved autonomous flight and served as the proving grounds for the <a href="http://pittras.org/projects/iarc/2018/08/10/update-iarc-technical-postmortem.html#dynamic-thrust-model">Time Varient, Non-linear Thrust Modeling</a> used later in the IARC project. The project won 3rd place in ECE Pitt's Swanson School of Engineering's Design Exposition in the Spring of 2018.

A short proposal was written justify the project based on current research. <a href="/assets/pdf/6DOF_UAV_Senior_Design_Proposal_1-12-18.pdf" target="_blank">Proposal</a>.

## Demonstration Video
<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/potRCO5AENA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

## Poster
<a href="/assets/pdf/6DOF_UAV.pdf" target="_blank">Open in new tab</a>

<center>
<object data="/assets/pdf/6DOF_UAV.pdf" type="application/pdf" width="560" height="500">
    <embed src="/assets/pdf/6DOF_UAV.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="/assets/pdf/6DOF_UAV.pdf">Download PDF</a>.</p>
    </embed>
</object>
</center>

## Reports
The project included two technical reports, one containing the results of the rotor modeling and the other summarizing the project.

<a href="/assets/pdf/Senior_Design_Thrust_Model_Overview.pdf" target="_blank">Early Modeling Results Report</a> (Contains measurements supportings claims, however has spelling/grammatical errors as it was written hastily in the midst of a busy project)

<a href="/assets/pdf/6_Degree_of_Freedom_UAV_Final_Report.pdf" target="_blank">Final Report</a>

## Findings
The increased dynamics due to the side-rotor configuration was extreme as confirmed in manual test-flights. The increase in weight was not substantial and the side rotors were powerful enough to provide 0.3g of acceleration. This was designed to be higher, however budget constraints forced compromises in weight and battery performance.

To fit within a limited budget, low-cost sensors were used for optical flow and height. The noise from these sensors proved too high to take full advantage of the increase in dynamics offered by the side-rotors. This is illustrated in the poster's plot of control's performance.

The thrust modeling technique dramatically improved performance particularly in light of the sensor noise issues. An interesting side effect was the impact of the side rotor's usage on battery voltage fluctuation. The thrust model caused sharp spikes in current consumption resulting in voltage sags. Further work was proposed to model the sag in a similar way to thrust.

Overall, the project found the side rotor topology to be performant as expected and easily realizable. A <a href="http://pittras.org/projects/iarc/2018/08/10/update-iarc-technical-postmortem.html#6-degree-of-freedom-uav">larger version was built for the IARC</a>.