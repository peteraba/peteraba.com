Movements
=========

### Basic motions

 - **Left:** h
 - **Down:** k
 - **Up:** k
 - **Right:** l

#### Examples

 - *Left 4 characters:* 4h
 - *Down 2 rows:* 2k
 - *Up 3 rows:* 3k
 - *Right 6 characters:* 6l

### Word movements

 - **Next normal-word:** w
 - **Previous normal-word:** b
 - **Next whole-word:** W
 - **Previous whole-word:** B
 - **End of the current word:** e

#### Examples

 - *Next 2 normal-words:* 2w
 - *Previous 2 normal-words:* 4b
 - *Next 2 whole-words:* 3W
 - *Previous 3 whole-words:* 3B

### Fast movements

 - **Beginning of the file:** gg
 - **End of the file:** G
 - **Jump to line number:** {Line number}G; {Line number}gg
 - **Next paragraph:** }
 - **Previous paragraph:** {

#### Examples

 - *Jump to line number #123:* 123G
 - *Jump to line number #123:* 123gg
 - *Next 3rd paragraph:* 3}
 - *Previous 3rd paragraph:* 3{

### Inline Search

 - **Jump to next character in line:** f
 - **Jump to previous character in line:** F
 - **Jump to next character in line, cursor 1 char before occurrence:** t
 - **Jump to previous character in line, cursor 1 char after occurrence:** T
 - **Repeat last jump to character (f):** ;
 - **Repeat last jump to character (f) backward:** ,

#### Examples

 - *Search the 2nd 'p' forward in line:* f2p
 - *Search the 2nd 'p' backwards in line:* F2p

### Visual mode

 - **Toggle going between first and last characters of selection in visual mode:** o
 - **Toggle going between first and last characters of selection on current line in visual mode:** O

### Advanced


Editing
=======

Basics
------

 - **Insert:** i
 - **Append:** a
 - **Delete:** x{Motion}
 - **Undo changes:** u
 - **Change:** c{Motion}
 - **Paste after:** p
 - **Paste before:** P
 - **Yanking:** y{Motion}

#### Examples

 - *Delete word:* dw
 - *Delete word backwards:* db
 - *Delete 2 lines:* 2dd
 - *Delete closest tag:* di<
 - *Change 3 lines:* 3dd
 - *Change text within closest double quotes in line:* ci"
 - **Yanking 1 char:** yl
 - **Yanking 3 chars:** 3yl
 - **Yanking 1 line:** Y
 - **Yanking 2 lines:** 2Y

Advanced stuff
--------------

 - **Insert something at the end of the current line:** A


Search and Replace
==================

Search
------

 - **Simple search:** /
 - **Simple search backwards:** ?
 - **Jump to next occurence of word under cursor:** *
 - **Jump to previous occurence of word under cursor:** #
 - **Jump to matching curly brace, parantheses or bracket under the cursor:** %

#### Examples

 - *Regular expressions search for finding any character followed by a vowel:* //.[aeiou]
 - *Delete everything up to a search 'fire' term:* d/fire

Replace
-------

 - **Replace first 'Amber' with 'Ember' in line:** :s/Amber/Ember
 - **Replace all 'Amber' with 'Ember' in line:** :s/Amber/Ember/g
 - **Replace all 'Amber' with 'Ember' in file:** :%s/Amber/Ember/g
 - **Replace a character:** r
 - **Enable replace mode:** R

#### Examples

 - *Replace all 'router' with 'dispatcher' in method in visual mode with confirmation:* v%:*'<, >'*s/router/dispatcher/gc
 - *Replace using last search:* :%s//replaceText/g
 - *Searching for text starting with a non-space, but the non-space excluded:* /[^ ]\zs(

Delete
------

 - **Delete first line that matches expression:** : :s/expression/d

#### Examples

 - **Delete all lines except that matches expression**: :g!/expression/d
 - **Delete all lines except that matches expression (with shortcut)**: :v/expression/d


Advanced stuff
--------------

 - **Very magic mode (Most usual expression engine):** \v


Macros 
======

 - **Record empty command list into macro into register a:** qaq
 - *Record macro into register a, delete tag around text in line and go to next line:* qadf>f<d$jq
 - **Replay macro from register a:** @a
 - *Replaying last macro 240 times:* 240@a



Advanced movements
==================

Jumping to positions
--------------------

 - **Jump half a screen down:** <c-d>
 - **Jump half a screen up:** <c-u>
 - **Jump full screen forward:** <c-f>
 - **Jump full screen backwards:** <c-b>
 - **Jump top of the current screen:** H
 - **Jump middle of the current screen:** M
 - **Jump last line of the current screen:** L

Moving the screen
-----------------

 - **Move current line to top of the screen:** zt
 - **Move current line to bottom of the screen:** zb
 - **Move current line to middle of the screen:** zz

Navigating wrapped lines
------------------------

 - **Go down a visual line (in wrapped lines):** gj
 - **Go to the beginning of the current visual line (in wrapped lines):** g0

Markers
-------

 - **Mark a line into register B:** mb
 - **Go to registered marker B:** 'b
 - **Go back to point where you jumped to marker from:* ''


Command line
============

 - *List files from current directory* :!ls
 - *Write date into current file:* :read !date
 - *Using selection of Visual mode as input for script: (-c: compile, -s: standard input, -p: in place)* :*'<,'>*!coffee -c -s -p



Buffers
=======

 - **List buffers:** :ls
 - **Next buffer:** :bn
 - **Previous buffer:** :bp
 - **Go to buffer #12:** :b12
 - **Delete current buffer:** :bd
 - **Delete buffer #12:** :bd12

New comment on the top of our 4 buffers
---------------------------------------

 - *Create macro in register A:* qa
 - *Jump to top of the file:* G
 - *Add new line at top:* O
 - *Add comment:* # My first comment
 - *Save file:* :w
 - *Next buffer:* :bn
 - *Run macro:* @a
 - *Run macro 2 more times:* 2@



Windows and Tabs
================

Windows
-------

### Split Windows

 - **Open (file in) horizontal split** :split [filename]; :sp [filename]
 - **Open (file in) vertial split:** :vpspit [filename]; :vsp [filename]
 - **Open buffer in horizontal split window:** :sb3
 - **Open buffer in vertical split window:** :vert sb3

### Moving around

 - **Navigate to window to the left:** <c-w>h
 - **Navigate to window to the bottom:** <c-w>j
 - **Navigate to window to the top:** <c-w>k
 - **Navigate to window to the right:** <c-w>l
 - **Move to window to the left:** <c-w>H
 - **Move to window to the bottom:** <c-w>J
 - **Move to window to the top:** <c-w>K
 - **Move to window to the right:** <c-w>L

### Resizing

 - **1 rows higher:** <c-w>+
 - **1 rows shorter:** <c-w>-
 - **1 columns wider:** <c-w>>
 - **1 columns narrower:** <c-w><
 - *5 rows higher:* <c-w>5+
 - *5 rows shorter:* <c-w>5-
 - *5 columns wider:* <c-w>5>
 - *5 columns narrower:* <c-w>5<
 - **Make windows as equal as possible:* <c-w>=

Tabs
----

 - **Open file on new tab:** tabedit filename; :tabe filename
 - **Next tab:** gt
 - **Previous tab:** gT



Indents and Folds
=================

Indents
-------

 - **Indent current line:** >>
 - **Unindent current line:** <<
 - **Indent current lines:** 3>>
 - **Unndent current lines:** 3<<
 - **Indent in insert mode:** <c-T>
 - **Unindent in insert mode:** <c-D>
 - **Indent selected lines in visual mode 6 times:** 6>
 - **Unindent selected lines in visual mode 6 times:** 6<



Mappings
========

### Basics

Creating a new mapping:

    :map ,rs :!bundle exec rspec<CR>

,rs will execute !bundle exec rspec now.



Text Objects
============

Object types
------------

 - **Words:** w
 - **Paragraph:** p
 - **Sentence:** s
 - **Tag:** t
 - **Curly braces:** {
 - **Brackets:** [
 - **Parantheses:** (
 - **Double quotes:** "
 - **Quotes:** '
 - **Backticks:** `

Selecting types
---------------

 - **Inside:* i
 - **Around** a

#### Examples

 - *Change content of first Double quotes on line:* ci"
 - *Delete current paragraph plus the following empyt lines:* dap


Registers
=========

 - **List registers:** :registers; :reg
 - **Delete text, but save it to register A:** "add
 - **Paste the contents of register A:** "ap
 - **Paste last yanked text:** "0p



Actions in Insert Mode
======================

 - **Vim-style backspace:** <c-h>
 - **Deleting word backwards:** <c-w>
 - **Delete line backwards from current position:** <c-u>
 - **Insert literal character:** <c-u>
 - **Insert unicode character:** <c-u><Unicode Character Id>
 - **Leaving insert mode for one command:** <c-o>
 - **Insert stuff from register A:** <c-r>A
 - **Using the expression register:** <c-r>=r{Expression}
 - **Insert something at the beginning of the current line:** I


Random actions and motions
==========================

 - **Perform the last action again:** .
 - **Open a file under the cursor:** gf
 - **Join current line with the following one by a space:** J
 - **Look up manual for command/program under the cursor:** K
 - **Increment number under cursor:** <c-a>
 - **Decrement number under cursor:** <c-x>

#### Examples

 - *Increment all the itemnum attributes in an XML file*: :g/itemnum/normal 20^A
