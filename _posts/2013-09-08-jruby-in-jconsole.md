---
layout: post
title: "JRuby in yr JConsole"
description: ""
category: 
tags: [jruby, java, jconsole]
---
[Getting a JRuby REPL in my JConsole](https://blogs.oracle.com/jmxetc/entry/how_to_retrieve_jvm_information) sounded cool, but the instructions are way out of date.

The demos dir referenced doesn't come with Oracle's JDK7; you've got to [download it separately](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html) and copy the demo directory to your JDK home.

The script engine stuff is now included in the JDK, so once you have that set up it's easy as pie:

{% highlight bash %}
mkdir jrconsole
cd jrconsole
#get the latest jruby-complete.jar http://www.jruby.org/download
wget http://jruby.org.s3.amazonaws.com/downloads/1.7.4/jruby-complete-1.7.4.jar
export JAVA_HOME=`/usr/libexec/java_home` 
jconsole -J-Djava.class.path=$JAVA_HOME/lib/jconsole.jar:$JAVA_HOME/lib/tools.jar:jruby-complete-1.7.4.jar \
    -J-Dcom.sun.demo.jconsole.console.language=jruby  \
    -pluginpath $JAVA_HOME/lib/jconsole.jar:$JAVA_HOME/demo/scripting/jconsole-plugin/jconsole-plugin.jar
{% endhighlight %}

...and the Script Shell tab should show up and you can proceed with the tutorial. 

Other than that **include_class** is deprecated in favor of **java_import** these days, anyway. And this is fine to screw around with, but the [jmx4r gem](https://github.com/jmesnil/jmx4r) is the way to go for any actual JMX automation.

