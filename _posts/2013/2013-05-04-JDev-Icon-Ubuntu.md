---
title: JDeveloper Icon in Ubuntu
layout: post
categories:
- Tech
tags:
- IDE
---

It is a shame that I spent so much time on JDeveloper itself. But the default icon for JDeveloper make me crazy. Here is how it looks like after I make it as the icon for Ubuntu launcher.

![Default JDeveloper Icon](/images/posts/default_jdev_icon.png)

Fortunately Oracle has a nice icon for JDeveloper in its official [twitter account](https://twitter.com/JDeveloper). It looks much better, isn't it? :)

![JDeveloper Icon](/images/posts/jdev_icon.png) 

Well, I thought everything was done and I can continue my work with JDeveloper. Then I found the icon in sidebar is not correct. It use the icon of Java. Shit.

![JDev Sidebar Issue](/images/posts/jdev_sidebar_issue.png)

Thanks to Google, I found the solution for this is to set *StartupWMClass* in the desktop file to tell unity it is a different application from other java applications. *StartupWMClass* can be found through command *xprop|grep WM_CLASS*. For JDevloper, it is *oracle-ide-osgi-boot-JDeveloper*. In a word, you can solve the problem by attaching the following line to your desktop file. 
	StartupWMClass=oracle-ide-osgi-boot-JDeveloper

![JDev Sidebar Fixed](/images/posts/jdev_icon_fixed.png)

That's all. And that's how programers waste their lives. :)




