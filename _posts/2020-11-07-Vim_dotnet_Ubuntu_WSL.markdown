---
layout: post
title:  "Vim + dotnet + Ubuntu + Windows Subsystem Linux"
date:   2020-11-07 16:21:51
categories: tutorial
---
## Vim + dotnet + Ubuntu + Windows Subsystem Linux

Nowadays with the addition of WSL, it's possible to install Ubuntu directly on Windows, without emulating a virtual machine. Also, developing on unix based operating systems using the dotnet framework and C# is possible thanks to the dotnet core framework. The dotnet framework helps us to create, debug and build projects from the cli. And thanks to the integration of OmniSharper to various text editors, we can have a set of tooling that will help us to be a little more productive while coding with this framework, even in the console.

Let's set up our environment to develop using the dotnet framework with vim on Ubuntu in WSL on Windows. 

![powershell]({{ site.url }}/assets/powershell.png)

{% highlight bash %}
sudo apt-get update && sudo apt-get install -y exuberant-ctags
{% endhighlight %}

