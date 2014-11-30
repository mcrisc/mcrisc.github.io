---
layout: post
title:  "Fixing c_acute in Ubuntu 14.04 LTS"
date:   2014-11-30 19:10:00
categories: ubuntu c_acute
---

On Ubuntu 14.04, a c acute (ć) is generated instead of a cedilla (ç)
every time you type `'` + `c` in a keyboard configured with layout
US International w/ deadkeys.

Although a [bug report][bug-report] has been filled about the problem, no
official solution is available yet. However, one of the comments in the bug
report shows a [simple solution][solution] for the problem.


[solution]: https://bugs.launchpad.net/ubuntu/+bug/518056/comments/39
[bug-report]: https://bugs.launchpad.net/ubuntu/+bug/518056/
