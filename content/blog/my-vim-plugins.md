+++
draft = false
section = "blog"
title = "My Vim Plugins"
description = "Vim is awesome out of the box, with plugins it's unbelievable"
pubdate = "2015-03-22T19:48:31+01:00"
date = "2015-03-22T19:48:31+01:00"
keywords = ["vim"]
tags = ["vim"]
thumbnail = ""
disqus_url = "https://peteraba.com/post/my-vim-plugins"
disqus_identifier = "my-vim-plugins"
disqus_title = "My Vim Plugins"
has_code = true
+++

My cheat sheet for my vim bundles.

<!--more-->

sensible.vim
------------

A universal set of defaults that (hopefully) everyone can agree on.

 - If you're new to Vim, you can install this as a starting point, rather than copying some random vimrc you found.
 - If you're pair programming and you can't agree on whose vimrc to use, this can be your neutral territory.
 - If you're administrating a server with an account that's not exclusively yours, you can scp this up to make things a bit more tolerable.
 - If you're troubleshooting a plugin and need to rule out interference from your vimrc, having this installed will ensure you still have some basic amenities.

**Homepage:** https://github.com/tpope/vim-sensible



surround.vim
------------

Surround.vim is all about "surroundings": parentheses, brackets, quotes, XML tags, and more. This plugin provides mappings to easily delete, change and add such surroundings in pairs.

**Homepage:** https://github.com/tpope/vim-surround

### Surrounding

 - Adding quotes around the word under cursor: **ysiw"**
 - Changing brackets to parentheses around the expression under the cursor: **cs[(**
 - Deleting tags around the current paragraph: **dst**



unimpaired.vim
--------------

Some complementary pairs of mappings.

 - There are mappings which are simply short normal mode aliases for commonly used ex commands.
 - There are line-wise mappings.
 - There are mappings for toggling options.
 - There are mappings for encoding and decoding.
 - There is a miscellaneous category.

**Homepage:** https://github.com/tpope/vim-unimpaired

### Line-wise mappings

 - Add a new line above current: **[\<Space\>**
 - Add a new line below current: **]\<Space\>**
 - Exchange current line with the one above: **[e**
 - Exchange current line with the one below: **]e**

### Encoding and decoding

 - Encode XML/HTML: **[x**
 - Decode XML/HTML: **]x**
 - Encode XML/HTML: **[x**
 - Decode XML/HTML: **]x**

### Option shortcuts

 - Enable spelling: **[os**
 - Disable spelling: **]os**
 - Toggle spelling: **cos**
 - Enable lists: **[ol**
 - Disable lists: **]ol**
 - Toggle lists: **col**
 - Enable numbers: **[on**
 - Disable numbers: **]on**
 - Toggle numbers: **con**

### Miscellaneous

 - Go to next file in the directory: **[f**
 - Go to previous file in the directory: **]f**



speeddating.vim
---------------

Increments and decrements dates and roman numbers as expected.

**Homepage:** https://github.com/tpope/vim-speeddating

### Commands

 - Increase date: **\<c\-a\>**
 - Decrease date: **\<c\-x\>**



abolish.vim
-----------

Three superficially unrelated plugins in one that share a common theme: working with variants of a word.

**Homepage:** https://github.com/tpope/vim-abolish

### Abbreviation

 - Add all insert abbreviations of separation and deseration: **:Abolish {despa,sepe}rat{e,es,ed,ing,ely,ion,ions,or}  {despe,sepa}rat{}**

### Substitution

 - Substitute variants of English words properly **:%Subvert/facilit{y,ies}/building{,s}/g**

### Coercion

 - Coerce to snake case: **crs**
 - Coerce to mixed case: **crm**
 - Coerce to camel case: **crc**
 - Coerce to upper case: **cru**



commentary.vim
--------------

Comment stuff out.

**Homepage:** https://github.com/tpope/vim-commentary

### Commands

 - Comment out a line: **gcc**
 - Comment out a paragraph: **gcap**
 - Comment out selected lines: **gc**
 - Comment out lines as command: **:7,17Commentary**
 - Comment out found text: **:g/TODO/Commentary**

#### Examples

 - Comment out 3 lines: **3gcc**



repeat.vim
----------

Repeat.vim remaps . in a way that plugins can tap into it.

**Homepage:** https://github.com/tpope/vim-repeat

Supports (among others):

 - surround.vim
 - speeddating.vim
 - abolish.vim
 - unimpaired.vim
 - commentary.vim
 - vim-easyclip (https://github.com/svermeulen/vim-easyclip)



Tabular
-------

Vim script for text filtering and alignment.

**Homepage:** https://github.com/godlygeek/tabular

### Tabularizing

 - Tabularizing selected text by equal size: **:*'<,'>*Tabularize /=**
 - Tabularizing all text by equal size: **:Tabularize /=**

#### Examples

 - Tabularize javascript array by colons: **Vi}:Tab /:**
 - Tabularize javascript array by colons in a way that colons stay with the identifiers: **Vi}:Tab /:\zs**
 - Tabularize markdown table: **:Tab \|**

### Shortcuts

 - Tabularize by equals sign: **\<leader\>a=**
 - Tabularize by colon sign: **\<leader\>a:/zs**



CtrlP
-----

Full path fuzzy file, buffer, mru, tag, ... finder for Vim.

**Homepage:** https://github.com/kien/ctrlp.vim

### Finding files

 - Find files in project: **\<c\-p\>**



Vim-Ultisnips
-------------

The ultimate snippet solution for Vim.

**Homepage:** https://github.com/SirVer/ultisnips

### Snippets

 - Editing available snippets: **:UltiSnipsEdit**

### My shortcuts

 - Insert snippet: **\<c\-e\>**
 - Jump to next variable: **\<c\-b\>**
 - Jump to previous variable: **\<c\-z\>**



Vim-Snippets
------------

A repository of snippets files for various programming languages.

**Homepage:** https://github.com/honza/vim-snippets



Tagbar
------

Tagbar is a Vim plugin that provides an easy way to browse the tags of the current file and get an overview of its structure. It does this by creating a sidebar that displays the ctags-generated tags of the current file, ordered by their scope. This means that for example methods in C++ are displayed under the class they are defined in.

**Homepage:** https://github.com/majutsushi/tagbar

### My shortcuts

 - Toggle Tagbar: **F8**



Vim-Fugitive
------------

Git tools for Vim.

**Homepage:** https://github.com/tpope/vim-fugitive



Vim-GitGutter
-------------

A Vim plugin which shows a git diff in the 'gutter' (sign column). It shows whether each line has been added, modified, and where lines have been removed. You can also stage and revert individual hunks.

**Homepage:** https://github.com/airblade/vim-gitgutter

### Gutting git

 - Jump to next hunk: **]c**
 - Jump to previous hunk: **[c**
 - Stage hunk: **\<leader\>hs**
 - Revert hunk: **\<leader\>hr**
 - Preview hunk: **\<leader\>hp**



Syntastic
---------

Syntastic is a syntax checking plugin for Vim that runs files through external syntax checkers and displays any resulting errors to the user.

**Homepage:** https://github.com/scrooloose/syntastic



YouCompleteMe
-------------

A code-completion engine for Vim.

**Homepage:** https://github.com/Valloric/YouCompleteMe



Vim-Go
------

Go (golang) support for Vim. It comes with pre-defined sensible settings (like auto gofmt on save), has autocomplete, snippet support, improved syntax highlighting, go toolchain commands, etc...

**Homepage:** https://github.com/fatih/vim-go

### General

 - Autocompletion via YouCompleteMe: **\<c\-x\>\<c\-o\>**


### Run Go commands

 - Go Run: **\<leader\>r**
 - Go Build: **\<leader\>b**
 - Go Test: **\<leader\>t**
 - Go Coverage: **\<leader\>c**
 - Show a list of interfaces which is implemented by the type under your cursor: **\<leader\>s**


### Identifiers

 - Open identifier in current view: **\<leader\>gd**
 - Open identifier in a horizontal split: **\<leader\>gd**
 - Open identifier in a vertical split: **\<leader\>gd**
 - Open identifier in a new tab: **\<leader\>gd**


### Go Docs

 - Open docs in current view: **\<leader\>gd**
 - Open docs in a vertical split: **\<leader\>gv**
 - Open docs in a browser: **\<leader\>gb**

### Miscellaneous

 - Show a list of interfaces which is implemented by the type under your cursor: **\<leader\>s**
 - Show type info for the word under your cursor: **\<leader\>i**
 - Rename the identifier under the cursor to a new name: **\<leader\>e**



Emmet-vim
---------

[Emmet](http://emmet.io) for Vim.

**Homepage:** https://github.com/mattn/emmet-vim

