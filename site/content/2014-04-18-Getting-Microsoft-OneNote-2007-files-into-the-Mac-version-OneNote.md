---
title: Getting Microsoft OneNote 2007 files into the Mac version of OneNote
layout: post
categories: blog
excerpt:
tags: [howto]
image:
  feature:
published: True
---

So I have just spent an entire evening extracting the data from my old Microsoft OneNote 2007 files. This was quite a task so I thought I would document my notes here. If I had had access to a Windows 8 machine then it would have been easier. As I understand it, OneNote 2013 on a Windows machine will simply open a OneNote 2007 file. That file can then be uploaded to Microsoft Onedrive, and then ‘hey presto’, I would have had access to it back on my Mac.

Instead I have Windows XP and OneNote 2007 running inside a VMware Fusion (version 4) virtual machine. I could also have bought Windows 8 and upgraded VMware Fusion to version 6, and saved myself all the trouble. With an academic discount, and upgrade pricing, that would still have cost me £85. It would possibly have been worth it had I needed Windows for anything else, but for now I don’t.

Instead, I found a copy of Office 2010 after a lot of googling. Most of these are illegal and come with keygens and cracks, but you can avoid problems if you just use it for the 29 day trial period. I installed this on the Windows XP virtual machine (after upgrading to Service Pack 3). I then opened my old OneNote 2007 folders one by one, and by clicking on the properties menu item, selected the option to upgrade them to the 2010 file format.

These 2010 version files can now be opened and edited by [Outline](http://outline.ws/) (a Mac version of OneNote). The 2007 files were read only.

I could have stopped there, but Outline also connects to Onedrive so I copied the sections of the notebooks over to empty new notebooks I had created on Onedrive. These are now available to the Mac version of OneNote.

About six hours of work. Not really sure that it wouldn’t have been better to have spent the £80.

## Quick list of thing's I learnt

- Neither Outline nor Mac OneNote can be searched by Spotlight (as of 18 Apr 2014)
- Only the text content of a table is copied to the clipboard when working with Outline. Mac OneNote gets this right
- You can't rename OneNote notebooks in Outline (at least those that are saved on Onedrive)