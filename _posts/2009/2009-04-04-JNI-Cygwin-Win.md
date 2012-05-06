---
title: 在Windows用cygwin编写JNI程序 - 1 (Using native code in Java）
layout: post
categories:
- Tech
tags:
- CPP
- Development
---

搞了我一晚上，Faint 

* HelloWorld.java 

{% highlight java %} 
public class HelloWorld{ 
	private static native void sayHello();
	public static void main(String[] args){ 
		try { System.loadLibrary("HelloWorld"); sayHello(); 
	} catch (Exception e) {
		 e.printStackTrace(); 
	} } 
}
{% endhighlight %}

* HelloWorld.cpp 
{% highlight c++ %}
#include using namespace std;
#include "HelloWorld_jni.h"

JNIEXPORT void JNICALL Java_HelloWorld_sayHello( JNIEnv *env, jclass c ){ 
	cerr << "Hello World from C++!" <<; endl; 
}
{% endhighlight %}

* run.sh 
{% highlight bash %}
#!/bin/bash

rm -f Native.dll *.o *.h
javac HelloWorld.java
javah -classpath . -o HelloWorld_jni.h HelloWorld 
g++ -mno-cygwin -D_REENTRANT -D_GNU_SOURCE -D__int64='long long' -I"${JAVA_HOME}"/include -I"${JAVA_HOME}"/include/win32 -I. -Wl,--add-stdcall-alias -shared -o HelloWorld.dll HelloWorld.cpp
java -classpath . -Xmx256m -Djava.library.path=. HelloWorld
{% endhighlight %}

对于**-mno-cygwin** , 如果不加这个参数，生成出来的HelloWorld.dll会依赖于cygwin1.dll。当执行System.loadLibrary("HelloWorld"); 时，系统会挂起.(hang) 对于**-D__int64='long long'**， 如果不加这个参数，编译的时候会报

>'__int64' does not name a type.

原因是在Ｗindows的Ｃ编译器中有__int64的定义， 但GCC中是没有的.
