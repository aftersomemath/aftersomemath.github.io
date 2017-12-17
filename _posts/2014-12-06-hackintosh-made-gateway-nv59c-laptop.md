---
title: Hackintosh made out of a Gateway NV59C laptop
date: 2014-12-06T13:21:23+00:00
author: theaftermath
layout: post
categories:
  - coding
tags:
  - hackintosh
  - IOS
  - Mac
---
Recently, I have done some android programming which culminated in my release of Super Block on the Google Play Store. Of course, I also want to target IOS users but to do so Apple requires me to purchase a Macintosh computer. Being a poor college student means there's no way I can do that.

So, I decided to try my hand at turning an old laptop I had into a Hackintosh.

![]({{ "/assets/images/posts/2014-12-06-hackintosh-made-gateway-nv59c-laptop/IMG_20141206_121229.jpg" | absolute_url }})

The specs:

  * i3-330M
  * Intel HD graphics (Iron Lake)
  * BCM57780 ethernet
  * RTL8292se WiFi &#8211; not working

There are two main ways to install OSx86 on a non-mac computer. Either create your own installation disk using <a href="http://www.tonymacx86.com/445-unibeast-install-os-x-yosemite-any-supported-intel-based-pc.html" target="_blank">Unibeast</a> or using a distro.

A distro is a hacked copy of the Mac OS. I ended up using <a href="http://hackintosh.zone/hackintosh/articles/yosemite-hackintosh-installation-instructions-guide-and-videos-for-amd-amdfx-intel-haswell-hp-laptops-common-pc/" target="_blank">Niresh's yosemite distribution</a> because it includes support for many hardware configurations. The only change I had to make was to tell the installer to include the Intel graphics kexts. After I did that the installation went extremely smoothly.

Unfortunately, the Intel graphics kexts provided by Niresh's installer were not quite right for my integrated card. I had to use some kexts provided by <a href="http://www.insanelymac.com/forum/topic/286092-guide-1st-generation-intel-hd-graphics-qeci/" target="_blank">GhostRaider</a> on the Insanely Mac forums. In the end I was able to enjoy graphics hardware acceleration and native resolution.

Finally, I was able to get my ethernet card to work using the <a href="http://hackintosh.zone/hackintosh/articles/macpois0n-r68/" target="_blank">MacPois0n utility</a>. MacPois0n only comes with one kext for Broadcom and it wasn't supposed to be for my card. However, it still worked for me.

![Yosemite running]({{ "/assets/images/posts/2014-12-06-hackintosh-made-gateway-nv59c-laptop/IMG_20141206_121100.jpg" | absolute_url }})

![Specs]({{ "/assets/images/posts/2014-12-06-hackintosh-made-gateway-nv59c-laptop/IMG_20141206_121142.jpg" | absolute_url }})

In the end, I now have a working hackintosh and can make IOS apps.