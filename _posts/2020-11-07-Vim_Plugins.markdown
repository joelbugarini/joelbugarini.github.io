---
layout: post
title:  "Vim Plugins"
date:   2020-11-07 22:45:51
categories: tutorial
---

We already have a workable environment with vim, but let's make it feel like home. Vim is popular because it is customizable through plug-ins. There are some options to install plug-ins in vim but let's stick with one for this tutorial: `vim-plug`. To install please enter the following code in the terminal:

{% highlight bash %}
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
{% endhighlight %}

Add a vim-plug section to your `~/.vimrc` through the command: 

{% highlight bash %}
vim ~/.vimrc
{% endhighlight %}


Now write the following, begin the section with 'call plug#begin()' and list the plugins with 'Plug' commands.

{% highlight vim%}
call plug#begin('~/.vim/plugged')
Plug 'dracula/vim', { 'as': 'dracula' }
call plug#end()

colorscheme dracula
{% endhighlight %}

Here, we are installing the dracula theme for testing our plugin system. Save the file and reload vim. Then use this command to install the plugin.
{% highlight bash %}
:PlugInstall
{% endhighlight %}

After restarting vim it should look like this:
\
![dracula theme]({{ site.url }}/assets/dracula.png)

Under the `call plug#end()` line we can configure our vim editor with the `set` method.

{% highlight vim%}
call plug#begin('~/.vim/plugged')
Plug 'dracula/vim', { 'as': 'dracula' }
call plug#end()

colorscheme dracula

" vim config vars

set number
set ruler

set tabstop=4
set shiftwidth=4
set smarttab
set expandtab

set laststatus=2
set cursorline
{% endhighlight %}

This configuration will add a ruler of number for the code, add an always visible status line, highlight the current cursor line, and set the tab and indentation variables.
\
![vim02]({{ site.url }}/assets/vim02.png)
