--- 
layout: post
title: "Vim spell check "
tags: 
---
I just found vim have built-in spell check. Never to late for me.

    
    :set spell spelllang=en_us    # enable
    :set nospell    # disable
    

When highlighting the misspelled word:

    
    zg    # will add this to your own word list
    z=    # find suggestion 
    ]s    # move to next misspelled word
    

