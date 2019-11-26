# VIM CheatSheet

## Simple movements in a file
0 	move to beginning of the current line<br>
$ 	move to end of line<br>
H 	move to the top of the current window (high)<br>
M 	move to the middle of the current window (middle)<br>
L 	move to the bottom line of the current window (low)<br>
1G 	move to the first line of the file<br>
20G 	move to the 20th line of the file<br>
G 	move to the last line of the file<br>

## Using NerdCommenter
Add the below line in your init.vim<br>
Plug 'scrooloose/nerdcommenter'                                   " code commenter<br>

then in your init.vim -- add the below section<br>
" Commenting blocks of code. <br>
autocmd FileType c,cpp,java,scala let b:comment_leader = '// ' <br>
autocmd FileType sh,ruby,python   let b:comment_leader = '# ' <br>
autocmd FileType conf,fstab       let b:comment_leader = '# ' <br>
autocmd FileType tex              let b:comment_leader = '% '<br>
autocmd FileType mail             let b:comment_leader = '> '<br>
autocmd FileType vim              let b:comment_leader = '" '<br>
noremap <silent> ,cc :<C-B>silent <C-E>s/^/<C-R>=escape(b:comment_leader,'/')<CR>/<CR>:nohlsearch<CR><br>
noremap <silent> ,cu :<C-B>silent <C-E>s/^\V<C-R>=escape(b:comment_leader,'/')<CR>//e<CR>:nohlsearch<CR><br>

Now you can type ,cc to comment a line and ,cu to uncomment a line (works both in normal and visual mode).<br>
so if you want to comment next 5 lines 5,cc<br>
and if you want to uncomment 5 lines 5,cu<br>

