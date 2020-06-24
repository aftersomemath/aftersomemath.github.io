---
layout: page
title: Recreation of the 1972 Magnavox Odyssey
# description: a project with a background image
img: /assets/img/odyssey-pheonix.jpg
current: false
permalink: /projects/magnavox-odyssey/
---

#### (6/23/20) Graduate school means I don't have time to complete the second revision. Thankfully, students at the <a href="http://vml.pitt.edu/">Vibrant Media Lab</a> are continuing!

The <a href="https://en.wikipedia.org/wiki/Magnavox_Odyssey">1972 Magnavox Odyssey</a> was the first home video game console. The <a href="http://vml.pitt.edu/">Vibrant Media Lab</a> under Dr. Zachary Horton is sponsoring a project to re-create the Odyssey. The recreation focuses on being true to the original with equivalent circuitry but modern components that can be easily sourced 50 years later.

## Odyssey Pheonix

I started working to recreate the Magnavox Odyssey during the Spring of 2018 along with Matthew Belding. By the spring of 2019 we had reversed engineered enough of the circuitry to recreate the entire Odyssey with new circuit boards and available common components. The new version, (named Odyssey Pheonix) increases the number of players from two to four, adds an expansion port for attatching additional circuitry, and provides a game card prototyping area. Pictured below, the design follows equivalent circuitry to the Magnavox Odyssey and has been tested with every game card made for the Odyssey. The design still needs to be updated with mistakes found during the first build. Eventually, the design files will be released as open source.

<div class="img_row">
    <img class="col one left" src="{{ site.baseurl }}/assets/img/odyssey-pheonix-demo.gif" alt="" title="CubeSat gimbal"/>
    <img class="col two left" src="{{ site.baseurl }}/assets/img/odyssey-pheonix.jpg" alt="" title="CubeSat model mounted in gimbal"/>
</div>
<div class="col three caption">
	(Left) Odyssey Pheonix being used with original controllers and original game card<br/>
	(Right) Odyssey Pheonix fully assembled, this was the first version and had to be significantally reworked<br/>
</div>

## Daughter Card Recreation

Additionally, I recreated all 10 original daughter cards used by the original Odyssey. These new cards can be used to replace broken cards in original Odysseys.

<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/odyssey-replaced-daughter-cards.jpg" alt="" title="Odyssey Daughter Cards Replaced"/>
</div>
<div class="col three caption">
    An original Odyssey with all the daughter cards replaced with the recreations.
</div>

## Extra Player Generation Circuit

I also developed the circuitry for to add two additional players to an original Magnavox Odyssey, for a total of four. The additional player 3 and 4 behave as if they are players 1 and 2 as far as any game logic is concerned.

<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/odyssey-extra-player-gen-brd.jpg" alt="" title="Odyssey Extra Player Generator"/>
</div>
<div class="col three caption">
    This circuit adds two additional players (for a total of 4) to the Odyssey console. This has been built and tested.
</div>

<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/odyssey-extra-player-brd-installed.jpg" alt="" title="Odyssey Extra Player Generator Board Installed"/>
</div>
<div class="col three caption">
    The extra player board installed in an Odyssey. This Odyssey includes other experimental functionality such as an Arduino Mega with a custom shield for sound effects in  the battery compartment.
</div>

<div class="img_row">
    <img class="col three left" src="{{ site.baseurl }}/assets/img/odyssey-4-player.jpg" alt="" title="4 player Odyssey"/>
</div>
<div class="col three caption">
    Recent testing showing 4 players and the ball. The extra-large players are the ones created by additional circuitry (they can be resized).
</div>

## Original 1972 Odyssey Schematic
<a href="/assets/pdf/odyssey-schematic.pdf" target="_blank">Open in new tab</a>
<center>
<object data="/assets/pdf/odyssey-schematic.pdf" type="application/pdf" width="560" height="400">
    <embed src="/assets/pdf/odyssey-schematic.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="/assets/pdf/odyssey-schematic.pdf">Download PDF</a>.</p>
    </embed>
</object>
</center>

<br/>
I will update this page with more information as I have time. If you are a Pitt student interested in this please contact me or Dr. Zachary Horton. If you are an Odyssey Enthusiast interested in pcb templates or general Odyssey technical information send me an email!
