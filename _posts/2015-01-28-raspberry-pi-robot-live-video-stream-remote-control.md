---
title: Raspberry Pi robot with Live Video Stream and Remote Control
date: 2015-01-28T16:15:32+00:00
author: theaftermath
layout: post
categories:
  - coding
  - robotics
tags:
  - c
  - python
  - raspberry pi
  - robotics
---
Recently, an old video of mine surfaced that I decided to share. It's a very basic Raspberry Pi robotics project that I built sometime during my senior year of high-school.

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/glsiogFmTEw" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe></center>

The chassis was salvaged from an old Radio Shack snap kit that was laying around the house. It was gutted except for the motors and gearing and I drove the motors with a simple quad half-H driver chip I had laying around.

Video streaming was accomplished using a Raspberry Pi standard camera. This enabled hardware encoding and sped up video streaming a lot.

Remote control was done using a python script on the Raspberry PI side. It opened a listening socket. On my PC I wrote a simple C program that opened a socket, connect to the raspberry PI and sent commands.

Overall, I learned a lot from this project. It was my first time working with WebSockets and my first attempt make an application that could send data over a network. This was a huge learning curve but, in the end, it turned out that the programming could be very simple when using standard libraries.