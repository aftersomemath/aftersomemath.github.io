---
title: My First Time Fixing an Open Source Bug
date: 2014-01-08T19:57:35+00:00
author: theaftermath
layout: post
categories:
  - coding
tags:
  - bug-fixing
  - pelican
  - python
  - work
---
## My First Experience Fixing an Open Source Bug

On the 22nd of December I received a message from "mitchtbaum" in response to my Jobs4bitcoins on reddit. He asked me to fix bug #1165 in the [Pelican](http://blog.getpelican.com/) project. I was

Pelican is an open-source static website generator. It can take input from a variety of formats such as reStructuredText, Markdown, or AsciiDoc and produce a beautiful and elegant website. Typically blogs.

The [bug](https://github.com/getpelican/pelican/issues/1165#issuecomment-31307840) I had to find involved the TAG\_SAVE\_AS , CATEGORY\_SAVE\_AS , and AUTHOR\_SAVE\_AS settings being ignored. These settings define the filenames that Pelican uses to save certain pars of the website. Any extension defined in these settings was simply being ignored and replaced with ".html".

## Goals

I needed to:

  * Setup a development environment
  * Learn/Understand Pelicans code structure
  * Find the bug
  * Understand the bug
  * Fix the bug

Unfortunately at the beginning of the project I did not have those goals so well thought out.

## First Mistakes

At first I thought I could just clone the repository and dig right into the code. I was wrong. It took a little while for me to realize I needed a little more than just the code to develop Pelican. It didn't take me long to access their [wiki](http://docs.getpelican.com/en/3.3.0/) and set up the recommended developers [environment](http://docs.getpelican.com/en/3.3.0/contribute.html#setting-up-the-development-environment).

Once I had a decent environment where I could edit the python code and run it, I was ready to work.

## Bug Finding

I decided to begin at the beggining, otherwise known as:

```python
def main():
```

Pelican is rather simple program and the code is very object orientated making it easy to read. From main() I could easily see which parts of the code were being run. I decided to start with the output generator code becuase it seemed the easiest way for an extension to be corrupted. Using gedit's built in string search function I manually found the lines where the file name was being changed. I was also able to eliminate potential lines of code Using 'print' statements to see what was happening to the file name. After a little while I realized that the file name was being changed in the pagination part of Pelican.

## Bug Comprehension

I began examining the pagination code and quickly began to be frustrated. I could not determine where the problem was. It was late at night though so I decided to take a break and come back the next day. It turned to be one of the best decisions I made during the project.

When I came back I realized that I had been looking over a line of code. My brain had been dismissing it as unimportant.

```python
name_root = os.path.splitext(name)[0]
```

"What is this?", I asked myself. I had never encountered that function before. A quick search into the python [documentation](http://docs.python.org/2/library/os.path.html#os.path.splitext) revealed that os.path.splitext actually splits a file name into its path and etension and returns an array containting the two strings.

Quickly I realized that the pagination code in Pelican was actually stripping the extension applied previously by the TAG\_SAVE\_AS , CATEGORY\_SAVE\_AS , and AUTHOR\_SAVE\_AS settings. Not only was it stripping the extension it wasn't even saving it for later. I looked into the Pelican documentation and I realized that pagination has its own settings that include settings for file names and extensions.

So this was a case of conflicting and settings that needed to be fixed.

## Bug Squashing

At first I thought the way to fix the bug was the simplest way. Pagination should have control of the NAMES of the file it outputs. But not the extensions.

So just like the extension was being stripped from the TAG\_SAVE\_AS , CATEGORY\_SAVE\_AS , and AUTHOR\_SAVE\_AS settings I was going to strip the extension applied by the pagination code. Then I could apply the original extension.

So in psuedo form:

```
Strip original extension
Save original extension

Call pagination code

Strip paginations extension
Apply original extension
```

However, the Pelican team told me, in a very freindly way, that this was basically a hack and did not address the actual problem. They were correct.

The actual problem was that the settings for pagination had a hard coded extension. I removed that hard-coded extension and added a way for the pagination to use the original extension passed to it through that setting. This removes the conflicting default settings and enables more user customization. A win-win situation!

## Conclusion

If I learned anything from this project it is that documenation exists for a reason, it helps both users AND developers.

For future projects I fully plan on reading the documentation first. It will greatly help to understand where the original developers where coming from and how the code works. In addition documentation contains a little of hidden information that you will not find in the code.

In terms of technique, I learned that in order to bugfix you need to look over every single line of code involved. You cannot just skip a line and consider it unimportant.

**If all else fails, READ THE INSTRUCTIONS!**