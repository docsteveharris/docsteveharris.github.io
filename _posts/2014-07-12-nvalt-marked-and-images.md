---
title: nvAlt, Marked (the app), and images
layout: post
tags: apps tips code
category: setup
published: true
---

A very quick post and memo on how I have been using nvAlt for taking notes, and the workarounds needed to preview images within these notes. There are easier ways to do this such as using [Voodoo Pad](https://plausible.coop/voodoopad/), or the amazing [OneNote](http://onenote.com/), but I am determined to stick with plain text. I have been burnt too many times in the past when I software became extinct, and my notes died with it. Most recently was the 7 year period between switching to a Mac and there being support for OneNote on anything other than Windows.

So currently all my notes go into [nvAlt](brettterpstra.com/projects/nvalt/), which is just a very good front end for a directory of plain text files. When I need to, then I write everything in Markdown, which in turn lets me add images into the text using the `![image caption](path/to/image.jpg)` format. It is [possible to set nvAlt](http://brettterpstra.com/2012/09/27/quick-tip-images-in-nvalt/) up to look for these without specifying the full path each time. I think it is worth doing this because it keeps my text clean whereby I don't either have to type or read the `path/to` bit each time.

The custom preview function in nValt handles this perfectly because you just tell it the base url or folder in which it should expect to find the image file.

e.g. `<base href="file:///Users/username/path/to/folder/">`

However, using the nicer and more flexible previews via [Marked](http://marked2app.com/) fails because it doesn't have the same information. So this is a long winded way of saying I have fixed that my learning how to write a little preprocessor script.

If you want to do the same thing, then save the script to your computer and run `chmod +x nvalt_preprocess4marked.py` as usual.

<script src="https://gist.github.com/docsteveharris/e8f56833a532c04860df.js"></script>

In line 23, you will need to replace `users/steve/pictures/nvalt-img/` with the path to the folder containing your images.

Then add open up the preferences in Marked, and switch the preprocessor on, and enter the path to the script:

![Switch the preprocessor on in Marked preferences](/assets/media/nvalt-marked-preprocessor.png)

I think that is it.

Obviously room for improvement, but it's currently working for me.



