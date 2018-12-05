# What is it ?

Fork from [skywind3000/gutentags_plus](https://github.com/skywind3000/gutentags_plus)，support [jsfaint/gen_tags.vim](https://github.com/jsfaint/gen_tags.vim)

# Installation

vim-plug:

```VimL
Plug 'hanxi/gen_tags_plus'
```

vundle:

```VimL
Plugin 'hanxi/gen_tags_plus'
```

# Configuration

```VimL
Plug 'jsfaint/gen_tags.vim'
Plug 'hanxi/gen_tags_plus'

```

Only usefull for my is the quickfix window.


# Command

```VimL
:GscopeFind {querytype} {name}
```

Perform a cscope search and take care of database switching before searching. 

`{querytype}` corresponds to the actual cscope line interface numbers as well as default nvi commands:

```text
0 or s: Find this symbol
1 or g: Find this definition
2 or d: Find functions called by this function
3 or c: Find functions calling this function
4 or t: Find this text string
6 or e: Find this egrep pattern
7 or f: Find this file
8 or i: Find files #including this file
9 or a: Find places where this symbol is assigned a value
```

# Keymaps

| keymap | desc |
|--------|------|
| `<leader>cs` | Find symbol (reference) under cursor |
| `<leader>cg` | Find symbol definition under cursor |
| `<leader>cd` | Functions called by this function |
| `<leader>cc` | Functions calling this function |
| `<leader>ct` | Find text string under cursor |
| `<leader>ce` | Find egrep pattern under cursor |
| `<leader>cf` | Find file name under cursor |
| `<leader>ci` | Find files #including the file name under cursor |
| `<leader>ca` | Find places where current symbol is assigned |

You can disable the default keymaps by:

```VimL
let g:gutentags_plus_nomap = 1
```

and define your new maps like:

```VimL
noremap <silent> <leader>gs :GscopeFind s <C-R><C-W><cr>
noremap <silent> <leader>gg :GscopeFind g <C-R><C-W><cr>
noremap <silent> <leader>gc :GscopeFind c <C-R><C-W><cr>
noremap <silent> <leader>gt :GscopeFind t <C-R><C-W><cr>
noremap <silent> <leader>ge :GscopeFind e <C-R><C-W><cr>
noremap <silent> <leader>gf :GscopeFind f <C-R>=expand("<cfile>")<cr><cr>
noremap <silent> <leader>gi :GscopeFind i <C-R>=expand("<cfile>")<cr><cr>
noremap <silent> <leader>gd :GscopeFind d <C-R><C-W><cr>
noremap <silent> <leader>ga :GscopeFind a <C-R><C-W><cr>
```

# Credits

You may be interested in the [vim-preview](https://github.com/skywind3000/vim-preview) plugin, it can preview results from quickfix window when you press `p`.

