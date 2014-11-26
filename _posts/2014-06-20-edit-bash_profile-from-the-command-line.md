---
title: Edit .bash_profile from the command line
layout: post
comments: true
tags: terminal bash quicktip
category: 
published: true
---

It's a pain to have to change my system preferences to show `.bash_profile`, then navigate, and open it for editing.

`subl .bash_profile` 

does this directly from the command line.


Make sure you have symlinked to your Sublime Text installtion first.


`ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl`



