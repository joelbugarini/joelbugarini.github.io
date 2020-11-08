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

" Vim config vars

colorscheme dracula

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

# Other Plugins

There are plenty of plugins to add to your vim, here I suggest some of them.

* [vim-airline](https://github.com/vim-airline/vim-airline)
* [NERDTree](https://github.com/preservim/nerdtree)
* [Tagbar](https://github.com/preservim/tagbar)
* [vim-autoclose](https://github.com/Townk/vim-autoclose)

Note: tagbar has a dependency that need to be installled through apt-get: `exuberant-ctags`. To install this dependency:

{% highlight bash %} sudo apt-get update && sudo apt-get install -y exuberant-ctags {% endhighlight %}

Now, this is the complete `.vimrc` config file:

{% highlight vim%}
call plug#begin('~/.vim/plugged')
    Plug 'dracula/vim', { 'as': 'dracula' }
    Plug 'vim-airline/vim-airline'
    Plug 'vim-airline/vim-airline-themes'
    Plug 'scrooloose/nerdtree'
    Plug 'majutsushi/tagbar'
    Plug 'Townk/vim-autoclose'
call plug#end()

" vim config vars

colorscheme dracula

set number
set ruler

set tabstop=4
set shiftwidth=4
set smarttab
set expandtab

set laststatus=2
set cursorline

" Plugins cofig vars
" Airline
let g:airline#extensions#tabline#enabled = 1
let g:airline_powerline_fonts = 1 
let g:airline_theme='hybrid'
let g:hybrid_custom_term_colors = 1
let g:hybrid_reduced_contrast = 1 

" NERDTree
map <C-n> :NERDTreeToggle<CR>
map <C-m> :TagbarToggle<CR>

autocmd VimEnter * NERDTree
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif

{% endhighlight %}

Let's see how it looks like in a project. Return to the project previously created and type `vim .`

![vim03]({{ site.url }}/assets/vim03.png)

That's it, in the next post we will be adding OmniSharper to the mix.
