--- 
layout: post 
title: wget Equivalent for Windows PowerShell 
tags: powershell,reference
---
Today I needed to install Python's 
[setup tools](https://pypi.python.org/pypi/setuptools) in a Windows
environment which comes with the recommendation to just download the 
script directly and run python against it. This works fine of course 
but if you're coming from a Linux environment you're probably looking 
for an equivalent of [wget](http://en.wikipedia.org/wiki/Wget). With 
wget the setup becomes slick like by running the following: 

```
wget https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py -O - | python
```

This can now be replicated in PowerShell V3 with the
[Invoke-WebReqest](http://go.microsoft.com/fwlink/?LinkID=217035)
cmdlet. 

```
(Invoke-WebRequest https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py).Content | python
```
Just another way to keep yourself in the shell more often than not. You
know, if you're into that sort of thing.
