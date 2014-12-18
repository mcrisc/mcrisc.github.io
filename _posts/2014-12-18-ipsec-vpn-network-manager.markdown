---
layout: post
title:  "Connecting to IPSec VPN with Network Manager"
date:   2014-12-18 14:59:00
categories: ubuntu linux vpn
---

Connecting to an IPSec VPN in Ubuntu Linux is easy, but it may take a while until you find your way around [Network Manager][nm], which does not bring the `vpnc` plugin by default. To install it, simply run:

```
sudo apt-get install network-manager-vpnc
```

After that you can add a connection of type `Cisco Compatible VPN (vpnc)` and your IPSec VPN will just work.


### Reference
1. [Network Manager][nm] - Ubuntu Documentation


[nm]: https://help.ubuntu.com/community/NetworkManager
