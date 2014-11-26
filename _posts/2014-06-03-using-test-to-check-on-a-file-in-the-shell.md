---
title: Using test to check on a file in the shell
layout: post
comments: true
tags: shell bash tips Hazel
category: 
published: true
---

Do you need to check whether a file meets certain conditions? Then use the `test` command in the bash shell.

For example, I am using [Hazel](http://www.noodlesoft.com/hazel.php) to clean up my desktop, but I have a bunch of directories symlinked there that I don't want it to touch. There is no such test built into Hazel (it can check for aliases but not symlinks). So instead the following line will check `test -L myfile.ext` and returns a `0` in the variable `$?` if true, and `1` if false (just type `echo $?` afterwards to see).

The Hazel one-liner then becomes `test ! -L $1` since Hazel uses `$1` to refer to the file being examined. Note the exclamation mark `!` that negates the test so it is checking that the file is _not_ a symlink.

 