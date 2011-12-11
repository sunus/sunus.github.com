---
title: 用Eclipse CDT和Cygwin搭建Windows下C++开发环境
layout: post
---

1. 下载Cygwin的在线[安装程序](http://www.cygwin.com/setup.exe), 安装过过程中选中gcc, g++, make. 
2. 下载[Eclipse IDE for C/C++ Developers](http://www.eclipse.org/downloads/). 
3. 设置环境变量， Path=%Path%；%Cygwin_Path%/bin，LIBRARY_PATH=%Cygwin_Path%/lib, C_INCLUDE_PATH=%Cygwin_Path%/usr/include 然后重启机器. 
4. 打开Eclipse， 在preferences-&gt;C/C++-&gt;New CDT project wizard-&gt;Makefile project 下面的Binary Parser选择Cygwin PE parser. 大功告成。 比 较搞怪的是第三步，一般设置环境变量是不需要重启的。 但我没重启，编译的时候就一直有"Error launching external scanner info generator" 这个错。Google下，发现有前辈遇到过一样的[问题](http://dev.eclipse.org/newslists/news.eclipse.tools.cdt/msg13627.html)，重启机器，搞定。
