# VIM CheatSheet

## Simple movements in a file
|Command  | Description                                             |
| ------- | -------------------------------------------------       |
| 0       | move to beginning of the current line                   |
| $ 	    | move to end of line                                     |
| H 	    | move to the top of the current window (high)            |
| gg      | move to the beginning of the file                       | 
| :$      | move to the end of the file                             |
| M 	    | move to the middle of the current window (middle)       |
| L 	    | move to the bottom line of the current window (low)     |
| 1G 	    | move to the first line of the file                      |
| 20G 	  | move to the 20th line of the file                       |
| G 	    | move to the last line of the file                       |

## Copy and Paste
1. Position the cursor where you want to begin cutting.
2. Press v to select characters (or uppercase V to select whole lines).
3. Move the cursor to the end of what you want to cut.
4. Press d to cut (or y to copy).
5. Move to where you would like to paste.
6. Press P to paste before the cursor, or p to paste after.

## Using NerdCommenter
Add the below line in your init.vim<br>
```Plug 'scrooloose/nerdcommenter'                                   " code commenter<br>```

then in your init.vim -- add the below section<br>
```" Commenting blocks of code. <br>
autocmd FileType c,cpp,java,scala let b:comment_leader = '// ' <br>
autocmd FileType sh,ruby,python   let b:comment_leader = '# ' <br>
autocmd FileType conf,fstab       let b:comment_leader = '# ' <br>
autocmd FileType tex              let b:comment_leader = '% '<br>
autocmd FileType mail             let b:comment_leader = '> '<br>
autocmd FileType vim              let b:comment_leader = '" '<br>
noremap <silent> ,cc :<C-B>silent <C-E>s/^/<C-R>=escape(b:comment_leader,'/')<CR>/<CR>:nohlsearch<CR><br>
noremap <silent> ,cu :<C-B>silent <C-E>s/^\V<C-R>=escape(b:comment_leader,'/')<CR>//e<CR>:nohlsearch<CR><br>
```

Now you can type ,cc to comment a line and ,cu to uncomment a line (works both in normal and visual mode).<br>
so if you want to comment next 5 lines 5,cc<br>
and if you want to uncomment 5 lines 5,cu<br>

