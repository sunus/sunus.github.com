---
title: Connect to Windows 7 from Ubuntu 11 using RDP
layout: post
categories:
- Tech
tags:
- Ubuntu
- RDP
---

It seems that the RDP setting for Windows 7 by default will enable 'Network Level Authentication'. The out of box RDP tool Remote Desktop Viewer or Remmina Remote Desktop Client on Ubuntu does not support it. So to connect to the Windows 7, you have to change the RDP setting to disable the 'Network Level Authentication' like the following picture shows.

![Windows 7 RDP](/images/posts/Win7_RDP.png)

I found that there are some RDP clients on linux which support NLA [here](http://serverfault.com/questions/155629/remote-desktop-from-linux-to-computer-that-requires-network-level-authentication) . If you do really need this feature, you can give it a try.


