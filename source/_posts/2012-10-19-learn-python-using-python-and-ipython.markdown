---
layout: post
title: "Learn python using python and iPython"
date: 2012-10-18 00:38
comments: true
categories: python
---

Doesn't the title sound awesome?

Expanded version:
Learn python(the language) using python(source code and test cases) and ipython(a python module)

So:

1. In order to understand python(source code and test cases), you need knowledge of python(language) and ipython(to use the source!)
2. In order to use ipython, you need to play with python(language) in ipython 


The pseudo source code for the title:

```
learn(python):
    use = python, ipython
    for item in use:
        if understand(item): return True
        else: return learn(item)
```

Ok, I know that's stupid. Here is my thought.

I had never read the python source code before. Then, I noticed (finally) the path printed while doing `logging?`. (Question mark `?` after an item will show the detail of that item.)


```
Type:       module
String Form:<module 'logging' from '/System/Library/Frameworks/Python.framework/Versions/2.7/lib/python2.7/logging/__init__.pyc'>
File:       /System/Library/Frameworks/Python.framework/Versions/2.7/lib/python2.7/logging/__init__.py
```

Fortunately, I went to that path and viewed the files, finding those system standard modules/libraries very, very, very well documented.

I found many design patterns that I would like to learn, but had not clue about where to look at before.

In words, ipython is very useful for checking documentation for anything you want to play with. Plus the tab completion helps you to list submodules, functions, or variables. This makes exploring a module as easy as traversing a file directory. 

As a result, I felt I was not using/learning python in a pythonic way. But now I (think I) do.
