---
title: "Quickbits"
permalink: /python/quickbits/
excerpt: "Quick Python snippets for doing various things"
toc: true
---

---

## Accessing Different Versions of Python
While Python 2.7 may have reached the end of it’s life, it will be a while before everything is upgraded to 3.7 or 3.8. As such you may still have two or more versions of Python in your system.

In your system interpreter or repl, you can point to initialize a specific version of Python. For Python 2.7:

{% highlight python linenos %}
py -2.7
 
Python 2.7.17 (v2.7.17:c2f86d86e6, Oct 19 2019, 21:01:17) [MSC v.1500 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
{% endhighlight %}


For Python 3.7:

{% highlight python linenos %}
py -3.7
Python 3.7.7 (tags/v3.7.7:d7c567b08f, Mar 10 2020, 10:41:24) [MSC v.1900 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
{% endhighlight %}

The increment version can be left out if you have only one version of Python 3 or 2 installed. Otherwise it would default to the highest priority incremental version as defined in your system environment variables.

{% highlight python linenos %}
py -3
Python 3.7.7 (tags/v3.7.7:d7c567b08f, Mar 10 2020, 10:41:24) [MSC v.1900 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
{% endhighlight %}

This is also a good way to target pip installs on specific versions of Python:

{% highlight python linenos %}
py -3.7 -m pip install <package name>
{% endhighlight %}

## Querying Python Version through sys.version
You can find out what version of Python is currently running and some info about that version through the sys module.

{% highlight python linenos %}
import sys
print (sys.version)
{% endhighlight %}

## Querying Python Paths
The sys module also has a method for querying Python paths for currently loaded modules:

{% highlight python linenos %}
import sys
 
for p in sys.path:
    print (p)
{% endhighlight %}

## Displaying Info, Warnings & Errors with OpenMaya
The OpenMaya API has 3 useful functions for displaying message to the status bar.

General Info:
{% highlight python linenos %}
import maya.OpenMaya as om
# This is an info alert
om.MGlobal.displayInfo('This is an info')
{% endhighlight %}

Warnings:
{% highlight python linenos %}
import maya.OpenMaya as om
# Warning: This is a warning
om.MGlobal.displayWarning('This is a warning')
{% endhighlight %}

Errors:
{% highlight python linenos %}
port maya.OpenMaya as om
# Error: This is an error
om.MGlobal.displayError('This is an info')
{% endhighlight %}
