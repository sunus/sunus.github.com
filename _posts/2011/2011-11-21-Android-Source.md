---
title: Download the sources of android
layout: post
categories:
- Tech
tags:
- Android
- Git
---

Well, you can follow the instructions [here](http://source.android.com/source/downloading.html) to download the whole repository of android. I did it yesterday. It took me about 10 - 12 hours to download all sources which are about 10G. Then I was wondering maybe a lot of people don’t need to download such a huge repository and then find the wayto do it as follows.

* Setup **repo** command by following the instructions in this [page](http://source.android.com/source/downloading.html).
* Execute {% highlight bash %} repo init -u https://android.googlesource.com/platform/manifest {% endhighlight %}
* Go into **.repo** folder and open **manifest.xml**. You will find all information of all sub projects.
* Download the subprojects using {% highlight bash %} repo sync project0 project1 project2 {% endhighlight %}

You can also download the sub projects using git clone if you like.




