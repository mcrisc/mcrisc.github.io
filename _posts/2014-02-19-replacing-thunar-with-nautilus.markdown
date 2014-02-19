---
layout: post
title:  "Replacing Thunar with Nautilus on Ubuntu + XFCE (Xubuntu)"
date:  2014-02-19 13:34:00 
categories: ubuntu xfce
---

It's very easy to make Nautilus the default file browser on Ubuntu when you find your way around. Thanks to [this post][post-solution], here is how to do it.

Edit the file `~/.config/xfce4/helpers.rc` and add the line:

`FileManager=nautilus`


That's it!

[post-solution]: http://forum.xfce.org/viewtopic.php?pid=26782#p26782
