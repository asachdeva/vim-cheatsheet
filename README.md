# VIM CheatSheet

## Simple movements in a file
0 	move to beginning of the current line
$ 	move to end of line
H 	move to the top of the current window (high)
M 	move to the middle of the current window (middle)
L 	move to the bottom line of the current window (low)
1G 	move to the first line of the file
20G 	move to the 20th line of the file
G 	move to the last line of the file

## Using NerdCommenter
Add the below line in your init.vim
Plug 'scrooloose/nerdcommenter'                                   " code commenter

then in your init.vim -- add the below section
" Commenting blocks of code.
autocmd FileType c,cpp,java,scala let b:comment_leader = '// '
autocmd FileType sh,ruby,python   let b:comment_leader = '# '
autocmd FileType conf,fstab       let b:comment_leader = '# '
autocmd FileType tex              let b:comment_leader = '% '
autocmd FileType mail             let b:comment_leader = '> '
autocmd FileType vim              let b:comment_leader = '" '
noremap <silent> ,cc :<C-B>silent <C-E>s/^/<C-R>=escape(b:comment_leader,'/')<CR>/<CR>:nohlsearch<CR>
noremap <silent> ,cu :<C-B>silent <C-E>s/^\V<C-R>=escape(b:comment_leader,'/')<CR>//e<CR>:nohlsearch<CR>

Now you can type ,cc to comment a line and ,cu to uncomment a line (works both in normal and visual mode).
so if you want to comment next 5 lines 5,cc
and if you want to uncomment 5 lines 5,cu
