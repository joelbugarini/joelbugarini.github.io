---
layout: post
title:  "OmniSharp in Vim"
date:   2020-11-08 22:45:51
categories: tutorial
---

At this point we have a very good understanding how plugins work in vim, also we set up some customization for our environment. Now we are going to integrate OmniSharp in Vim. OmniSharp is a set of tools that enhance the experience of developing for .NET, things like intellisense or document format are even possible with it.

I’m going to leave a set of instructions for fastly install it ourselves, but if you are interested in diving deep or have any trouble in the installation process, you can refer to the `omnisharp-vim` github pages: [https://github.com/OmniSharp/omnisharp-vim](https://github.com/OmniSharp/omnisharp-vim)


Open up our `.vimrc` file with the following command:

{% highlight bash %}
vim ~/.vimrc
{% endhighlight %}

Then, under the `call plug#begin('~/.vim/plugged')` line, add:
{% highlight bash %}
   Plug 'OmniSharp/omnisharp-vim'
{% endhighlight %}

Save the file and restart Vim, install the plugin with the `:PlugInstall` command.

# OmniSharp Server
This plugin is depends on the OmniSharp Server that we have not installed yet, to doing so, run the command on vim:

{% highlight bash %}
:OmniSharpInstall v1.35.2
{% endhighlight %}
