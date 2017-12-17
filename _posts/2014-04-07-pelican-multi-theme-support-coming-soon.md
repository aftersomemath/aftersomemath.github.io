---
title: Pelican Multi-Theme Support Coming Soon!
date: 2014-04-07T00:00:07+00:00
author: theaftermath
layout: post
categories:
  - coding
tags:
  - bug-fixing
  - pelican
  - python
---
## The Beginnings of Multi-Theme Support for Pelican

When I first started this project it was supposed to just allow pelican to have a configurable base theme. Currently pelican allows you to create your own theme and then inherit from the base theme. This is somewhat limiting because to make a new theme, you have to fork the old one. It is also difficult to use portions from other themes as building blocks.

I finished adding this setting not long ago as you can see [here](https://github.com/getpelican/pelican/pull/1297).

However, ametaireau [commented](https://github.com/getpelican/pelican/issues/1092#issuecomment-39289051) in another related issue that he would like to see pelican use any number of themes. If he had suggested that just a few weeks ago I would have thought it was impossible. However, over the past couple weeks I have learned a lot about object oriented programming from working on an android app. I decided to give it another shot today.

## Early Results

Before I could start, I needed to learn more about how python handles arrays.

It didnt take long to discover that python doesn't call array's arrays. Instead they are called lists. This is because there a lot of built in functions to help manipulate 

[lists](https://docs.python.org/2/tutorial/datastructures.html#more-on-lists). This was very suprising to me, and I think it is very conveniant, if not somewhat bloated.

Then I discovered python [dictionaries](https://docs.python.org/2/tutorial/datastructures.html#dictionaries). Dictionaries are a powerful tool that allow key-value pairs to be assigned easily in a very high level fashion. In pelican a dictionary is used to define the settings.

I chose to use the list datatype to make a 'THEME' setting. 'THEME' is then stored in the dictionary that holds all of pelicans settings.

Once I had that established I was able to make a lot of progress in just a couple hours. Currently the feature allows you to specify any number of subthemes. As long as the theme you want to inherit from is included in the 'THEME' setting you can do this:

'extends "!theme_name/foo.html"'

And the theme code will be extended.

## TODO

Currently there's bits and pieces of things that need to be fixed. Autoreload doesn't work on the themes specified in 'THEMES'; and I'm sure there's other things I'm forgetting. I need to grep through the code looking for all the things that usually happen to the 'THEME' setting and make sure they are applied to 'THEME'. However, I already had to do that when I added the 'BASE_THEME' setting so this shouldn't be too hard.
