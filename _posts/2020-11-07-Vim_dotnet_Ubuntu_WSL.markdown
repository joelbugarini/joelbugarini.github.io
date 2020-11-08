---
layout: post
title:  "Vim + dotnet + Ubuntu + Windows Subsystem Linux"
date:   2020-11-07 16:21:51
categories: tutorial
---
Nowadays with the addition of WSL, it's possible to install Ubuntu directly on Windows, without emulating a virtual machine. Also, developing on unix based operating systems using the dotnet framework and C# is possible thanks to the dotnet core framework. The dotnet framework helps us to create, debug and build projects from the cli. And thanks to the integration of OmniSharper to various text editors, we can have a set of tooling that will help us to be a little more productive while coding with this framework, even in the console.

Let's set up our environment to develop using the dotnet framework with vim on Ubuntu in WSL on Windows. Yes I know that this sounds crazy, but believe me we will learn a lot from this experience. 

First of all we need to install Ubuntu on Windows subsystem Linux,  for this we will need to enable the subsystem feature of windows with the help of Powershell, so let's open Powershell as an administrator. 

![powershell]({{ site.url }}/assets/powershell.png)

Once it's open write the next line of code:

{% highlight powershell %}
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
{% endhighlight %}

It might ask you to restart your computer, and after that we will be able to install Ubuntu through the Microsoft Store. 

![msstore]({{ site.url }}/assets/msstore.png)

Open Ubuntu once it is installed, It will prompt you to write the password for the super user and to initialize the system.

The first thing we will need to do in Ubuntu is to update our apt-get sources with the next command: 

{% highlight bash %}
sudo apt-get update
{% endhighlight %}

Now that's installed the darknet core SDK. Remember that eat only can be installed Ubuntu 20.04, 18.04 and 16.04. These are the supported distributions. We will be using the 20.04 distribution for the example, if you intend to install other version, please refere to this link: ![https://docs.microsoft.com/en-us/dotnet/core/install/linux-ubuntu](https://docs.microsoft.com/en-us/dotnet/core/install/linux-ubuntu). 

In the terminal write the following:
{% highlight bash %}
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
{% endhighlight %}
This will download the Packers from the Microsoft site, to install the SDK run the following command:

{% highlight bash %}
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-3.1
{% endhighlight %}

Text editor is already installed in our system, we just need to add some packages to make it better.


{% highlight bash %} sudo apt-get update && sudo apt-get install -y exuberant-ctags {% endhighlight %}


