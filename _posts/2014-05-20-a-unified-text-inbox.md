---
title: A unified text inbox
layout: post
tags: gtd
category: gtd
published: false
---

I seem to be struggling to keep track of notes and information, and part of the problem is that I feel mental inertia when I come to choose where to save a note. I am therefore trying a solution whereby I save *all* text notes in a single folder. On my Mac, this folder is the one tracked by nvAlt. It is therefore trivial to start a note. On the web and in iOS, this folder is the one tracked again by SimpleNote (the sync with simplenote is handled by nvAlt). Again it is trivial to add or find a note.

I then use a prefix system to file the note, but any file without a prefix gets a date prefix. This avoids problems with future file modifications and dates and provides a simple sorting system for files. All other prefixes start with 'q', and then have a 2 letter code.

Currently, this looks something like this

  qtx: _archive-taskpaper
  qtp: taskpaper-projects
  qtt: taskpaper
  qpx: _archive-readme-projects
  qpp: readme-projects
  qww: clinical
  qrr: running
  qll: listacular
  qbb: blog
  qcf: config

I then use Brett Terpstra's [folderize](http://brettterpstra.com/2014/05/04/folderize-sync-nvalt-notes-to-nested-folders/) script to translate theses codes into a folder hierarchy. There is one extra level of complication. For taskpaper/todo lists and readme-project files the first word of the file name then assigns that file to an area of responsibility, and the remainder of the name then defines the project to which it belongs. Again, though, if these are not assigned then the todo list or readme simple lives in the 'taskpaper' or 'readme-projects' folder. I can always go back and add the relevant area of responsibility or project keyword later.

My current list of these includes

    academic: academic AoR
    analysis: academic AoR
    paper: academic AoR
    family:
    homeAdmin:
    workAdmin:
    me: me AoR
    gtd: me AoR
    training: 
    
    
The last step of sorting depends on Hazel watching the folder containing the readme's and todo's and then creating aliases, and sorting those aliases appropriately.

Something strange us happening



