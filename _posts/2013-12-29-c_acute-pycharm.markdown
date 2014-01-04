---
layout: post
title:  "IPython and PyCharm: c acute instead of cedilla on Ubuntu"
date:   2013-12-29 14:47:00
categories: python pycharm ubuntu
---

On Ubuntu 13.04, [PyCharm][pycharm] and [IPython QT console][qt-console] generate a c acute (ć) instead of a cedilla (ç) 
when you type `acute(') + c` in a keyboard configured as US International w/ deadkeys.

There's a [bug report][bug-report] about this issue on Launchpad where I could find a [simple solution][bug-comment28] for that problem.
 PyCharm and IPython QT console are working perfectly now.


[pycharm]: http://www.jetbrains.com/pycharm/
[qt-console]: http://ipython.org/ipython-doc/dev/install/install.html#dependencies-for-the-ipython-qt-console
[bug-comment28]: https://bugs.launchpad.net/ubuntu/+bug/518056/comments/28
[bug-report]: https://bugs.launchpad.net/ubuntu/+bug/518056/
