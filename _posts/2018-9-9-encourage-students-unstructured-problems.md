---
layout: post
title:  Encouraging Effective Learning in Difficult Student Projects
date:   2018-09-09
description: Pitt's Robotics and Automation Society's projects often require theory that students have not learned yet. I encouraged members to build their intuition in order to solve problems.
---

<blockquote>
I don't care much for equations myself. This is partly because it is difficult for me to write them down, but mainly because I don't have an intuitive feeling for equations.
    - Stephen Hawking
</blockquote>

## Background

As a project leader and officer in Pitt RAS for three years, I had the privilege of answering many undergraduate and graduate student's technical questions. I received questions as simple as, "How do I install Arduino?" to "How does a covariance matrix get updated in an Extended Kalman Filter?". Often, answering the question was only half the battle. RAS members, without fail, attempt projects far beyond their educational level. This is commendable, but it means that students struggle to apply engineering intuition.

By frequently answering questions, I learned two strategies to encourage student success in such projects:
<ul>
    <li>Provide an intuitive basis for understanding the problem</li>
    <li>Show how intuition can be improved through experiments</li>
</ul>

## Providing an Intuitive Basis

When someone attempts something above their educational level, the greatest tool they can have is intuition. It allows students to start searching for a solution, and it can prevent mistakes caused by mis-applied theory. Of course, mis-applied intuition is just as bad, but in my experience its often the theory without intuition that causes mistakes.

For instance, imagine you are Electrical Engineering Student and have just finished your first circuits course. You are choosing an appropriate battery for an electric motor driving a <a href="https://www.turtlebot.com">turtlebot</a>. You find the wattage rating of the motor, multiply it by the time you want to run, and look for a battery with an energy rating equal to or greater than that. So far everything aligns with the theory you have learned thus far. You start looking for batteries, but everything is larger and heavier than you expected. The student might then attempt to find the lightest batteries on the market, which results in an expensive design.

Here, the trouble is that the student applied theory, without developing an intuition of the problem. In this example, I would suggest the student imagine they are driving their car. Then I would encourage them to think about how they use the accelerator when driving. Quickly, the student realizes that they only use a fraction of their max power output when coasting in a car, and their robot is no different. Clearly, it would require more force (more watts!) when starting and less power when coasting.

With this kind of explanation, the student understands they can produce a better design and they gain an understanding important for future work.

## Improving an Intuition

Usually the intuitive explanation of a problem is enough to reason about the results and choose the correct strategy. However, in the above example, the student would understand their problem but might not know how to go about solving it. Estimating the power usage of a robot is difficult even for seasoned professionals.

The student could go find a textbook and read the details of DC motor power consumption. But, that will take significant time, and this is an extracurricular project where time is the limiting factor. Thus, I typically advise running an experiment that builds on the intuition. In this case, it is would be acceptable to connect the motor to a power supply and measure its power consumption while varying the mechanical load. From this kind of hands on experimentation, the student will develop an intuitive model for how much power is used and then they can estimate the required battery size.

For a student project, this level of precision is usually more than acceptable for a first try. It's more important that the basic principles are well understood than for every decision to be optimal.

## Conclusion

Encouraging intuition allows students to understand problems without mathmatics and theory they have not learned yet. Using such a basis, they can then make design decisions quickly and experiment to validate them. Further, as they continue in their studies, it will be much easier for them to learn the appropriate theory due to their fundamental understanding.