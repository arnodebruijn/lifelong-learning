Vim
===


Normal mode
-----------


Insert mode
-----------
enter insert mode with `i` to insert at cursor
enter insert mode with `I` to insert at beginning of line
enter insert mode with `a` to append after cursor
enter insert mode with `A` to append at end of line


Visual mode
-----------
enter visual mode with `:`


Command-line mode
-----------------
enter command-line mode with `:`

### Commands
:[range]d [x]                             delete lines [into register x]
:[range]y [x]                             yank lines [into register x]
:[range]s/{pattern}/{string}/[flags]      substitute
:[range]normal {commands}                 execute normal mode commands on each specified line
:[range]t {address}                       copy lines to address
:[range]m {address}                       move lines to address


### Marks
$   end of the file
%   all lines in current file
.   the current line
'<  first line of visual selection
'>  last line of visual selection

#### Ranges
18            line number
18,25         line numbers
'<,'>         visual selection
/{pattern}    first line containing pattern


Todo
----
- add diacritics
- macro vs commandline mode selection with normal command

qq          start recording macro named q;
A;<ESC>j    manipulations
q           stop recording
@@          repeat macro

[visual selection]
A;          manipulation on one line
:'<,'>n .   repeat manipulation on visual selection


:lcd %:p:h  set working directory to the directory of the currently open file
