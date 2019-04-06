## VIM
vim .vimrc

```
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim

call vundle#begin()
Plugin 'VundleVim/Vundle.vim'
Plugin 'maksimr/vim-jsbeautify'
Plugin 'moll/vim-node'
Plugin 'terryma/vim-multiple-cursors'
Plugin '907th/vim-auto-save'
Plugin 'chrisbra/csv.vim'
Plugin 'Townk/vim-autoclose'
Plugin 'flazz/vim-colorschemes'
Plugin 'leafgarland/typescript-vim'
Plugin 'Quramy/tsuquyomi'
Plugin 'Shougo/vimproc.vim'
Plugin 'itchyny/lightline.vim'
Plugin 'Valloric/YouCompleteMe'
call vundle#end()

filetype plugin indent on
syntax on
set number
set expandtab
set tabstop=2
set shiftwidth=2
set cursorline
set laststatus=2 

nnoremap <C-h> <C-W><C-W> 
let mapleader="g" 
inoremap <leader>g <C-x><C-o>   
inoremap ff <Esc> 
inoremap ( ()<Left>
inoremap ' ''<Left>
inoremap " ""<Left>
map Q :qa<CR>
map W :Vex<CR> 
map E <C-f>  
map R <C-b>
map df :bd<cr>
map B :vert term<CR>
map T <C-z>
map S :s/\<\>//g<left><left><left><left><left>
map ; :normal A; <cr>:normal o<cr> 
map  cc :s/^/\/\/ /g<CR>:let @/ = ""<CR>
map  vv :s/^\/\/ //g<CR>:let @/ = ""<CR> 

let g:netrw_banner = 0
let g:netrw_liststyle = 3
let g:netrw_browse_split = 4
let g:netrw_winsize = 25
let g:netrw_altv = 1
let g:auto_save = 1
let g:auto_save_silent = 1
let g:auto_save_events = ["InsertLeave","TextChanged","TextChangedI"]
let g:tsuquyomi_disable_quickfix = 1

colorscheme molokai
hi EndOfBuffer ctermfg=black
ru macros/justify.vim
set noshowmode
" set colorcolumn=92
```
## INSTALL VIMPROC
After you save the .vimrc file, you must go out and then go back in and then run :PluginInstall. Then go out and run the following: cd ~/.vim/bundle/vimproc.vim && sudo make && cd ~

## INSTALL YOUCOMPLETEME
- After you save the .vimrc file, you must go out and then go back in and then run :PluginInstall. Then go out and run the following: cd ~/.vim/bundle/YouCompleteMe && python3 install.py --all && cd ~
- You may have to run :PluginUpdate afterwords before it activates. 
- There is an error that comes out at the end but it does not affect how it works if you are just programming in Node and JS. If you need to program in C or C++ you need to follow the instructions here: https://github.com/Valloric/YouCompleteMe#linux-64-bit

## KEYBOARD COMBOS FOR VIM
```
IN EDIT MODE      
a = start adding text AFTER cursor (use instead of i)      
alt j or alt k will escape edit mode
ctrl p is autocomplete. 
ctrl xn specific autocomplete.  
ctrl xk dictionary. 
ctrl xf search and add files after /. 
ctrl f next page.  
ctrl b previous page.  

IN NON-EDIT MODE
:Vex file browswer
    I have this mapped to shift W
ctrl h will switch back and forth from the editor    
shift ZZ to close the file browser
:vs path/to/file.txt to open a file directly

TERMINAL
pause Vim with Ctrl + Z, (I have mapped this to shift T)
play in the terminal,
then return to exactly where you left with Vim by just typing the command fg.

or

:vert term (opens terminal on the side)
finish working, then write exit in terminal 
:bd + enter to close the buffer (I have this mapped to df + enter)


v = select lines

dd = delete the line where the cursor is at.  
number + dd will delete that many lines. 
dd and then move to another spot and then p to paste the line deleted.  
x = delete a letter at a time. 
dw = delete a word. 
d$ = to delete to end of line. 
shift d = delete all from cursor to end of line. 

u = undo what you just did 
ctrl r = redo things
shift u = undo what was done to the line

gg  or  H = beginning
G or L  = end
number plus G will take you to that line

0 = beginning of line
$ = end of line

j = move down one line
k = move up one line
number before j or k will move that many lines in that direccion

e = jumps forward
w = jumps forward by words
b = jumps backwards by words

{ = jumps up by sections or paragraphs
} = jumps down by sections or paragraphs

Ctrl-D  move half-page down
Ctrl-U  move half-page up

% jumps from one bracket to another

TO COPY AND PASTE
To select a line first shift v, then y, then move to the new line, and then p
If you want just letters, just use v instead of shift v

TO COPY AND PASTE BETWEEN DOCUMENTS
select the text with visual
"*y (or "+y) to copy the text
"*p (or "+p) to paste the text

TO SEARCH AND REPLACE:
select the lines first
:s/changefrom/changeto/g

TO FIND WORDS
put the cursor on the word you want to find and then type the * 
and then it will bring you to those words in the text, or to just find something, 
in non-edit mode put  / and the word, and then press the letter n to keep searching

NEW COMMANDS CREATED WITH VIMRC FILE
in edit mode
ff to escape
in normal mode
Shift Q to save and close
Shift E to go down a page
Shift R to go up a page
Shift B to open vertical terminal
Shift S to advanced search
Shift T to suspend vim and go to terminal
fg to return to vim
Shift W to open vertical file explorer
df to :bd<cr> to close vertical explorer
cc to comment out lines
vv to uncomment lines
; to add a semicolon at the end of a line
( to put () and the cursor in the middle
' to put '' and the cursor in the middle
" to put "" and the cursor in the middle
```


## INSTALL GOOGLE DRIVE IN VIM
1. In APIs, Install Drive API in project and Create Credentials (OAuth client ID)
2. Choose "Other" and put product name, e.g "My OCAMLDrive".
3. Click "Create". You will get a Client ID, a Client Secret.
4. google-drive-ocamlfuse -headless -label me -id "ID" -secret "ID"
5. mkdir ~/gdrive && google-drive-ocamlfuse -label me ~/gdrive



## SET UP GIT

1. git config --global user.email "EMAIL" && git config --global user.name "NAME"
2. git clone https://github.com/USERNAME/REPOSITORY.git 
3. git config --global credential.helper store && git push https://github.com/USERNAME/REPOSITORY.git
// It will ask for your username and password. If you have 2 step verification, you will have to create a token under developer settings.

ALL IN ONE
git config --global user.email "EMAIL" && git config --global user.name "NAME" && git clone https://github.com/USERNAME/REPOSITORY.git && cd ieducando && git config --global credential.helper store && git push https://github.com/USERNAME/REPOSITORY.git && cd ~

TO UPDATE GIT
git add -A && git commit -m "updated" && git push -u origin master
//For the first time
git add -A && git commit -m "updated" && git push
//For all other times