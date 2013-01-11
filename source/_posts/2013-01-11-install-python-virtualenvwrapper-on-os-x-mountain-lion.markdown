---
layout: post
title: "Install Python virtualenvwrapper on OS X Mountain Lion"
date: 2013-01-11 00:24
comments: true
categories: python, os x 
---

This seems trivial right? pip install?
Well, that's not the case if you want virtualenv or virtualenvwrapper working properly.

You could, using pip, to install those packages. But you will notice even provided `--no-site-packages`, you will still able to import from system site-packages. (If you really did so, you will have them in `/Library/Python/2.7/site-packages/`). In my case, installing in virtualenv will end up placing packages into system site-packages path. Oh my zsh.

For many reasons you need to install python from homebrew or somewhere else.
 
### Mountain Lion Python (2.7.2)

Mountain Lion Default python: 

    which python 
    /usr/bin/python 
    
Mountain Lion Defaut python Framework/Package/Library Path:

    /System/Library/Frameworks/Python.framework/Versions/2.7/
    /Library/Python/2.7/site-packages/

    
Note: Mountain lion python will cause trouble when using virtualenv/virtualenvwrapper.

### Brew installed python (2.7.3)

Simply:

    brew install python

I got:
  
    which python
    /usr/local/bin/python

Then you got pip distribute ready.
Have fun with pip install.
My site-packages path is:

    /usr/local/lib/python2.7/site-packages/
  

### virtualenvwrapper

    pip install virtualenvwrapper
  
    export WORKON_HOME=~/Envs
    mkdir -p $WORKON_HOME
    source /usr/local/share/python/virtualenvwrapper.sh
    # change above path accordingly 
    mkvirtualenv env1
  
.zshrc or .bashrc add following:

    PATH=/usr/local/share/python/:$PATH
    export WORKON_HOME=$HOME/.virtualenvs
    source /usr/local/bin/virtualenvwrapper.sh
    
There are couple of paths you might need to add, such as `/usr/local/share/python/`.(This contains some python scripts. e.g yolk, virtualenvwrapper.sh, etc)
  
#### List Installed packages

    lssitepackages   
    rmvirtualenv
    cpvirtualenv

#### Switch to a env

    workon env1
    deactivate

### With zsh


In `$WORKON_HOME/postactivate` add:

```
PS1="$_OLD_VIRTUAL_PS1"
_OLD_RPROMPT="$RPROMPT"
RPROMPT="%{${fg_bold[white]}%}(env: %{${fg[green]}%}`basename \"$VIRTUAL_ENV\"`%{${fg_bold[white]}%})%{${reset_color}%} $RPROMPT"
```
In `$WORKON_HOME/postdeactivate` add:

```
RPROMPT="$_OLD_RPROMPT"
```
