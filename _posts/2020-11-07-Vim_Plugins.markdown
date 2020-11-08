---
layout: post
title:  "Vim Plugins"
date:   2020-11-07 22:45:51
categories: tutorial
---

We already have a workable environment with vim, now let's make it feel like home. Vim is popular because it is customizable through plug-ins. There are some options to install plug-ins in vim but let's stick with one for this tutorial: `vim-plug`.

{% highlight bash %}
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
{% endhighlight %}

Add a vim-plug section to your `~/.vimrc` through the command: 

{% highlight bash %}
vim ~/.vimrc
{% endhighlight %}


Now write the following:

{% highlight vim%}
call plug#begin('~/.vim/plugged')
Plug 'dracula/vim', { 'as': 'dracula' }
call plug#end()
{% endhighlight %}

Here, we are installing the dracula theme for testing our plugin system. Save the file and reload vim. Then use this command to install the plugin.
{% highlight bash %}
:PlugInstall
{% endhighlight %}
