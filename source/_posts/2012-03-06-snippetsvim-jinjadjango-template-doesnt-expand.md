--- 
layout: post
title: "snippets.vim: jinja/django template doesn't expand"
tags: 
---
I was configuring snippets.vim, which I should have done earlier that could
save a lot of time. Then, I ran into an issue. I've been developing a web app
using Flask, and this means I use jinja2 for html template. My templates are
all with extension .html, which should work directly with default html
snippets come with snippets.vim. But it doesn't.

I didn't find a solution online. However, I found some snippets for django
template. The final solution is just append content from html.snippets to
htmldjango.snippets.

    
    cat html.snippets >> htmldjango.snippets
    

And in .vimrc add

    
    autocmd FileType html set ft=htmldjango.snippets " For SnipMate
    

