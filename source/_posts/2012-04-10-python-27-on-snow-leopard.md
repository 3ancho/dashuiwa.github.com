--- 
layout: post
title: Python 2.7 on Snow Leopard
tags: 
---
Use the default easy_install, packages will be installed under python2.6.

  1. Download from python.org And make sure python --version is 2.7

  2. Install pip curl -O [http://python-distribute.org/distribute_setup.py](http://python-distribute.org/distribute_setup.py) python distribute_setup.py easy_install pip

  3. Get Virtualenv working pip install virtualenvwrapper export WORKON_HOME=~/Envs mkdir -p $WORKON_HOME source /usr/local/bin/virtualenvwrapper.sh

