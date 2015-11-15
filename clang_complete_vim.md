<!--
Title:"C++ code completion in Vim using clang",
Date:"2014-03-09T08:48+0200",
Tags:"C++, Vim",
-->
The clang_complete plugin uses clang instead of ctags.  In order to find all header files in a project which is nothing but trivial we need to create a .clang_complete file in the project's directory containing the inlcude pathes relevant for the project's sources.  

Because i don't want to setup this file by hand for each of my projects im glad that the clang complete plugin comes with a litle helper tool for that:

just call: 
```bash
make CXX='~/.vim/bin/cc_args.py g++' -B
```

(this requires that your make file uses CXX as compiler variable)

Plugin:
https://github.com/Rip-Rip/clang_complete

Vimrc snip:
```
"clang completion
"plugin from https://github.com/Rip-Rip/clang_complete
"package libclang-dev has to be installed

"don''t show the preview window becaue it is not informative at all
:set completeopt-=preview

"automatically select the first entry in the popup menu
let g:clang_auto_select = 1
"open quickfix window
let g:clang_complete_copen = 1
"periodic update
let g:clang_periodic_quickfix = 1
"insert argument placeholders when calling a memberfunction 
"(Use tab to jump to the next parameter)
let g:clang_snippets = 1
```
