# monkey-vim

Read this in other languages: [简体中文](README.zh-CN.md)

## Introduction

The project monkey-vim, aims to make a powerful, fast and cross platform IDE.

## Screenshot

- **xterm vim**

![xterm vim](https://raw.githubusercontent.com/QMonkey/monkey-vim/master/pictures/xterm_vim.png "xterm vim")

- **gvim**

![gvim](https://raw.githubusercontent.com/QMonkey/monkey-vim/master/pictures/gvim.png "gvim")

## Requirements

- vim 8.0+

## Installation

### 1. Git clone

```bash
git clone https://github.com/QMonkey/monkey-vim.git
```

### 2. Install dependences

#### 2.1 Dependent tools

```bash
# Ubuntu
sudo apt-get install ctags
sudo apt-get install cmake
sudo apt-get install silversearcher-ag or sudo apt-get install ack-grep
sudo apt-get install wmctrl

# OpenSUSE
sudo zypper install ctags
sudo zypper install cmake
sudo zypper install the_silver_searcher or sudo zypper install ack
sudo zypper install wmctrl

# CentOS
sudo yum install ctags
sudo yum install cmake
sudo yum install the_silver_searcher or sudo yum install ack
sudo yum install wmctrl

# Mac
brew install ctags
brew install cmake
brew install the_silver_searcher or brew install ack

# Windows
Visual Studio with C++ component
7-zip
ctags
cmake
ag
```

#### 2.2 Fonts

- [Hack](https://github.com/chrissimpkins/Hack)

#### 2.3 Docset

- [Dash](https://kapeli.com/dash/)
- [Zeal](https://zealdocs.org/)

#### 2.4 C/C++

```bash
# Ubuntu
sudo apt-get install gcc
sudo apt-get install g++
# "x" depends on your clang version
sudo apt-get install clang-3.x

# OpenSUSE
sudo zypper install gcc
sudo zypper install gcc-c++
sudo zypper install llvm-clang

# CentOS
sudo yum install gcc
sudo yum install gcc-c++
sudo yum install clang

# Mac
brew install clang

# Windows
gcc
g++
clang
```

#### 2.5 Javascript

```bash
sudo npm install -g jslint
sudo npm install -g js-beautify
sudo npm install -g tern
```

#### 2.6 JSON

```bash
sudo npm install -g jsonlint
```

#### 2.7 Python

```bash
sudo pip install jedi
sudo pip install autopep8 or sudo pip install yapf
sudo pip install pyflakes
sudo pip install pycodestyle
```

#### 2.8 Golang

```bash
# Please install the lastest version of go

# Other golang dependences
# Execute vim command below after successfully install monkey-vim
:GoInstallBinaries
```

#### 2.9 Java

```bash
# Please install oracle jdk

# Ubuntu
sudo apt-get install astyle

# OpenSUSE
sudo zypper install astyle

# CentOS
sudo yum install astyle

# Mac
brew install astyle

# Windows
astyle
```

#### 2.10 Lua

```bash
# Ubuntu
sudo apt-get install lua

# OpenSUSE
sudo zypper install lua

# CentOS
sudo yum install lua

# Mac
brew install lua

# Windows
lua
```

#### 2.11 Ruby

```bash
sudo gem install ruby-beautify
```

#### 2.12 PHP

```bash
# Ubuntu
sudo apt-get install php

# CentOS
sudo yum install php

# OpenSUSE
sudo zypper install php

# Mac
brew install php

# Windows
php
```

#### 2.13 Shell

```bash
# Ubuntu
sudo apt-get install devscripts

# OpenSUSE
sudo zypper install checkbashisms

# CentOS
sudo yum install rpmdevtools

# Mac
brew install checkbashisms
```

#### 2.14 Markdown

```bash
sudo npm install -g instant-markdown-d
sudo npm install -g remark-cli
sudo gem install mdl
```

### 3. Install monkey-vim

- Linux and Mac

```bash
cd monkey-vim
ln -s $(pwd)/.vimrc ~/.vimrc
vim
```

- Windows

```bash
cd monkey-vim
mklink %HOMEDRIVE%%HOMEPATH%\.vimrc %CD%\.vimrc
vim
```

## Update project

```bash
cd monkey-vim
git pull
```

```vim
:PlugInstall
:PlugUpdate
:PlugClean
```

## Keyboard shortcut

```
The "Leader" key below means comma key.
```

### 1. Normal mode

#### 1.1 Remap

```
s       Replace a motion/text object with clipboard content
S       Replace the text from cursor position to the end of the line with clipboard content
Y       Copy from the cursor position to the end of the line, same as y$
H       To the first non-blank character of the line, same as ^
L       To the last non-blank character of the line, same as $
U       Redo, same as Ctrl-r
;       Enter command line mode, same as :
q       Quit current window, same as :q
Q       Quit vim, same as :qa
t       Recording, same as origin q
```

#### 1.2 F2 ~ F10

```
F2      Toggle NERDTree
F3      Toggle Tagbar
F7      Run current project asynchronously. You can use ":FocusDispatch" command to override the default command. For example, :FocusDispatch gcc % -o a.out
F8      Toggle output window of F7
F9      Run current file
F10     Markdown preview in browser
F11     Toggle fullscreen, only available in GUI mode
```

#### 1.3 Buffer

```
Leader+o    Open a new buffer with given file path in current window
[+b         Jump to previous buffer
]+b         Jump to next buffer

-           Open file directory in current window
~           Open project root or file directory in current window
```

#### 1.4 Split

```
Leader+s    Open a horizontal split with given file path in current window
Leader+v    Open a vertical split with given file path in current window

Ctrl+h      Jump to the left split
Ctrl+j      Jump to the below split
Ctrl+k      Jump to the above split
Ctrl+l      Jump to the right split

up          Stretch the window vertically
down        Shrink the window vertically
left        Stretch the window horizontally
right       Shrink the window horizontally
Leader+z    Toggle zoom
```

#### 1.5 Tab

```
Leader+t    Open a tab with given file path in current window

[+t         Jump to previous tab
]+t         Jump to next tab
Leader+1~9  Jump to the 1~9 tab
Leader+[    Jump to first tab
Leader+]    Jump to last tab
```

#### 1.6 Search

```
#       Search current word forward
*       Search current word backward
```

#### 1.7 Replace

```
# '\r' standard for newline

Leader+R    Replace current word. Not whole word, and don't need to confirm
Leader+rw   Same as "Leader+R", but search for whole world
Leader+rc   Same as "Leader+R", but need to confirm
Leader+rcw  Same as "Leader+R", but search for whole world and need to confirm
```

#### 1.8 Programming language

```
K                   Refer current word in doc
Leader+Leader+z     Refer doc in dash or zeal

gd              Go to definition
Leader+gr       Go to references. Only support golang, python and javascript

# Golang
Leader+gb       GoBuild, build current package
Leader+gi       GoInstall, build and install current package
Leader+gt       GoTest, execute go test for current go source
Leader+gf       GoTestFunc, execute go test for current go test function
Leader+ga       GoAlternate, alternate between implementation and test code

# Java, TODO
nmap <leader>jI <Plug>(JavaComplete-Imports-AddMissing)
nmap <leader>jR <Plug>(JavaComplete-Imports-RemoveUnused)
nmap <leader>ji <Plug>(JavaComplete-Imports-AddSmart)
nmap <leader>jii <Plug>(JavaComplete-Imports-Add)

imap <C-j>I <Plug>(JavaComplete-Imports-AddMissing)
imap <C-j>R <Plug>(JavaComplete-Imports-RemoveUnused)
imap <C-j>i <Plug>(JavaComplete-Imports-AddSmart)
imap <C-j>ii <Plug>(JavaComplete-Imports-Add)

nmap <leader>jM <Plug>(JavaComplete-Generate-AbstractMethods)

imap <C-j>jM <Plug>(JavaComplete-Generate-AbstractMethods)

nmap <leader>jA <Plug>(JavaComplete-Generate-Accessors)
nmap <leader>js <Plug>(JavaComplete-Generate-AccessorSetter)
nmap <leader>jg <Plug>(JavaComplete-Generate-AccessorGetter)
nmap <leader>ja <Plug>(JavaComplete-Generate-AccessorSetterGetter)
nmap <leader>jts <Plug>(JavaComplete-Generate-ToString)
nmap <leader>jeq <Plug>(JavaComplete-Generate-EqualsAndHashCode)
nmap <leader>jc <Plug>(JavaComplete-Generate-Constructor)
nmap <leader>jcc <Plug>(JavaComplete-Generate-DefaultConstructor)

imap <C-j>s <Plug>(JavaComplete-Generate-AccessorSetter)
imap <C-j>g <Plug>(JavaComplete-Generate-AccessorGetter)
imap <C-j>a <Plug>(JavaComplete-Generate-AccessorSetterGetter)

vmap <leader>js <Plug>(JavaComplete-Generate-AccessorSetter)
vmap <leader>jg <Plug>(JavaComplete-Generate-AccessorGetter)
vmap <leader>ja <Plug>(JavaComplete-Generate-AccessorSetterGetter)
```

#### 1.9 Ctags

```
Ctrl+]  Jump to the definition of the keyword under the cursor
g]      Like "Ctrl+]", but need to choose one tag to jump
```

#### 1.10 Fold

```
za      When on a closed fold, open it. When on an open fold, close it and set 'foldenable'
zc      Close one fold under the cursor
zo      Open one fold under the cursor
zR      Open all folds
zM      Close all folds
```

#### 1.11 Marks

```
m[a-zA-Z]   Toggle mark and display it in the leftmost column
m,          Place the next available mark
m.          If no mark on line, place the next available mark. Otherwise, remove (first) existing mark

dm[a-zA-Z]  Delete mark[a-zA-Z]
m-          Delete all marks in current line
m<Space>    Delete all marks in current buffer

'[a-zA-Z]   Jump to the mark
]`          Jump to next mark
[`          Jump to prev mark
`]          Jump by alphabetical order to next mark
`[          Jump by alphabetical order to prev mark
m/          View all marks in Location List

m[0-9]      Toggle the corresponding marker !@#$%^&*()

m<S-[0-9]>  Remove all markers of the same type
m<BS>       Remove all markers

]-          Jump to next line having a marker of the same type
[-          Jump to prev line having a marker of the same type
]=          Jump to next line having a marker of any type
[=          Jump to prev line having a marker of any type
m?          Open location list and display markers from current buffer
```

#### 1.12 Code-completion engine: [YouCompleteMe](https://github.com/Valloric/YouCompleteMe)

```
gd          Go to definition
Leader+jd   Go to declaration
Leader+jt   Go to header file, definition or declaration
```

#### 1.13 Syntax checking plugin: [syntastic](https://github.com/scrooloose/syntastic)

```
Leader+e    Toggle error window
```

#### 1.14 Motions on speed: [vim-sneak](https://github.com/justinmk/vim-sneak)

```
f       Search two character and jump to specific word
F       Same as f, but in reverse direction
```

#### 1.15 Switch buffer and tab. Save or restore workspace: [vim-ctrlspace](https://github.com/vim-ctrlspace/vim-ctrlspace)

```
Ctrl+Space  Open CtrlSpace

Leader+bs   Backup workspace
Leader+rs   Restore workspace
```

#### 1.16 Full path fuzzy file, buffer, mru, tag, ... finder: [ctrlp.vim](https://github.com/ctrlpvim/ctrlp.vim)

```
Ctrl+p      Search files
Ctrl+t      Search buffer tags
Ctrl+n      Search project tags
```

#### 1.17 Code searcher for project: [ack.vim](https://github.com/mileszs/ack.vim)

```
Leader+a        Search current word in current directory
```

#### 1.18 Commenter: [nerdcommenter](https://github.com/scrooloose/nerdcommenter)

```
Leader+cl       Comment out the current line
Leader+cu       Uncomments the current line
```

#### 1.19 Change surround easier: [vim-surround](https://github.com/tpope/vim-surround)

```
ys+textobj+surroundA        Add surround A for the region of textobj
yss+surroundA               Add surround A for current line
ds+surroundA                Delete surround A
cs+surroundA+surroundB      Change surround A to B
```

#### 1.20 Run code: [vim-quickrun](https://github.com/thinca/vim-quickrun)

```
Leader+ru       Run current file
```

#### 1.21 Others

```
'.              Jump to last changes
''              To the position before the latest jump, or where the last "m'" or "m`" command was given
Ctrl+o          Go to [count] Older cursor position in jump list
Ctrl+i          Go to [count] newer cursor position in jump list
Leader+f        Show current file in NERDTree
cod             Toggle diff
cop             Toggle paste
col             Toggle list
[+<Space>       Add [count] blank lines above the cursor
]+<Space>       Add [count] blank lines below the cursor
Leader+cd       Change project root
Leader+/        No highlight search
Leader+space    Strip whitespace
Leader+q        Toggle quickfix
Leader+l        Toggle location list
```

### 2. Insert mode

#### 2.1 Remap

```
t       Recording, same as origin q
Ctrl+d  Delete current row
Ctrl+k  Delete from cursor to the end of the line
```

### 3. Visual mode

#### 3.1 Remap

```
s       Replace selected text with clipboard content
;       Enter command line mode, same as :
```

#### 3.2 Search

```
#       Search selected text forward
*       Search selected text backward
```

#### 3.3 Replace

```
# '\r' standard for newline

Leader+R    Replace selected text
Leader+rc   Same as "Leader+R", but need to confirm
```

#### 3.4 Programming language

```
K       Refer selected text in doc
```

#### 3.5 Motions on speed: [vim-sneak](https://github.com/justinmk/vim-sneak)

```
f       Search two character and jump to specific word
F       Same as f, but in reverse direction
```

#### 3.6 Code searcher for project: [ack.vim](https://github.com/mileszs/ack.vim)

```
Leader+a        Search selected text in current directory
```

#### 3.7 Commenter: [nerdcommenter](https://github.com/scrooloose/nerdcommenter)

```
Leader+cl       Comment out the selected text
Leader+cu       Uncomments the selected line(s)
```

#### 3.8 Change surround easier: [vim-surround](https://github.com/tpope/vim-surround)

```
S+surroundA     Add surround A for selected text
```

#### 3.9 Run code: [vim-quickrun](https://github.com/thinca/vim-quickrun)

```
Leader+ru    Run selected code
```

### 4. Command line mode

```
Ctrl+j  Next command
Ctrl+k  Previous command
Ctrl+a  Jump to the begin of the command line
Ctrl+e  Jump to the end of the command line
```

## Useful command

### 1. W

```vim
" Save file with root permission
:W
```

### 2. Ack

```vim
" Search recursively in current directory for the pattern, and then open the quickfix for you.
" Jump to the first result unless ! is given.
:Ack[!] {pattern}

" Same as :Ack, but load the result into location list
:LAck[!] {pattern}
```

### 3. UpdateTags

```vim
" Generate tags for current file
:UpdateTags

" Generate tags for current project
:UpdateTags -R
```

### 4. YcmGenerateConfig

```vim
" Generate ".ycm_extra_conf.py" file for current project
:YcmGenerateConfig
```

### 5. Locate

```vim
" Run 'locate' and load the results into the quickfix. Jump to the first result unless ! is given.
:Locate[!] {args}
```

## Use git in vim

### 1. git for vim: [vim-fugitive](https://github.com/tpope/vim-fugitive)

```vim
" Run an arbitrary git command. Similar to :!git [args] but chdir to the repository tree first.
:Git [args]

" Bring up the output of git-status in the preview window. "g?" command for more help
:Gstatus

" A wrapper around git-commit.  If there is nothing to commit, :Gstatus is called instead.
:Gcommit [args]

" Calls git-merge and loads errors and conflicted files into the quickfix
:Gmerge [args]

" Like :Gmerge, but for git-pull
:Gpull [args]

" Like :Gpush, but for git-fetch
:Gfetch [args]

" Invoke git-push, load the results into the quickfix
:Gpush [args]

" Same as git grep
:Ggrep [args]

" Empty the buffer and :read a fugitive-revision. When the argument is omitted, this is similar to git-checkout on a work tree file or git-add on a stage file, but without writing anything to disk
:Gread [path]

" You can give :Gwrite an explicit path of where in the work tree to write
:Gwrite [path]

" Wrapper around git-mv that renames the buffer afterward
:Gmove {destination}

" Wrapper around git-rm that deletes the buffer afterward
:Gremove

" Perform a vimdiff against the current file in the given revision
:Gdiff [args]

" Load all previous revisions of the current file into the quickfix.  Additional git-log arguments can be given (for example, --reverse).
" If "--" appears as an argument, no file specific filtering is done, and previous commits rather than previous file revisions are loaded
:Glog [args]

" Like |:Glog|, but use the location list instead of the quickfix
:Gllog [args]

" Use git-log -L to load previous revisions of the given range of the current file into the quickfix
:{range}Glog [args]

" Run git-blame on the file and open the results in a scroll bound vertical split. "g?" command for more help
:Gblame [flags]

" Run git-blame on the given range
:{range}Gblame [flags]

" More help, please refer the video
https://github.com/tpope/vim-fugitive#screencasts

" or the official doc
:h fugitive.txt
```

### 2. gitk for vim: [gitv](https://github.com/gregsexton/gitv)

```vim
" Invoking this command on a buffer that belongs to a git repository causes the gitv browser to open. '!' causes gitv to open in file mode rather than browser mode.
" Any [args] supplied are passed on to the gitv viewer and can be used to narrow the commits that are shown.
" If this command is run on a buffer not belonging to a git repository a message stating 'Not a git repository.' is displayed
:Gitv! [args]

" In file mode it narrows the commits shown to only those affecting lines in the range
:{range}Gitv! [args]

" Like :Gitv!, but open in browser mode
:Gitv [args]

" Please refer the official doc for more help
:h gitv.txt
```

## Precautions

- I perfer 8 size indentation, and use hard tab instead of space. Therefore, monkey-vim uses 8 size tab. If you perfer 4 size indentation, and use space instead of tab. You can change the config below

```vim
set tabstop=8
set softtabstop=8
set shiftwidth=8
set noexpandtab
```

to

```vim
set tabstop=4
set softtabstop=4
set shiftwidth=4
set expandtab
```

## FAQ

[FAQ](https://github.com/QMonkey/monkey-vim/wiki/FAQ)

## Recommended settings

- [Build vim from source](https://github.com/QMonkey/monkey-vim/wiki/Build-Vim-from-source)

- Use vim to view man doc in shell, please put it in your "~/.bashrc" file

```bash
export MANPAGER="env MAN_PN=1 vim -R +MANPAGER -"
```

- Remap Caps Lock key to Ctrl

```bash
# Linux
# Please put this in the 10-caps2ctrl.conf file under /etc/X11/xorg.conf.d/
Section "InputClass"
        Identifier             "keyboard-layout"
        MatchIsKeyboard        "on"
        Option "XkbOptions"    "ctrl:nocaps"
EndSection

# Mac
# Go to System Preferences -> Keyboard -> Keyboard Tab -> Modifier Keys and select Control for Caps Lock

# Windows
# Please install keytweak
```

## Configuration

If you have any problem or suggestion with monkey-vim, welcome to give me an [issue](https://github.com/QMonkey/monkey-vim/issues)
