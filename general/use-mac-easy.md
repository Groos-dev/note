# cursor

## shortcut key

- `command + \`: open new window

## plugins

### vim

#### setting

### formatter

设置

```json
    "editor.formatOnSave": true,
    "editor.formatOnPaste": true,
    "[html]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
```

### python

[ms-python.black-formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter)

### markDown

VSCode 支持安装多种扩展插件来增强 Markdown 的编辑体验。常见的插件包括：

- Markdown All in One：提供自动补全、实时预览、格式化等功能。

- Markdown Preview Enhanced：增加了更丰富的预览功能，支持图表、流程图、数学公式等。
- MarkdownLint：提供 Markdown 语法提示和修正建议，帮助你保持 Markdown 语法的整洁。

```json
    // markdownlint 配置
    "markdownlint.config": {
        "MD007": {
            "indent": 4
        }
    }
```

### React 开发插件

为了提升 React 开发体验，VSCode 提供了多种有用的插件。以下是一些推荐的 React 开发插件：

1. **ES7+ React/Redux/React-Native snippets**：
   提供 React、Redux 和 React Native 的代码片段，大大提高编码效率。

2. **ESLint**：
   JavaScript 和 JSX 的静态代码分析工具，帮助你发现并修复代码中的问题。

3. **Prettier - Code formatter**：
   自动格式化你的 JavaScript/React/JSX 代码，保持代码风格一致。

4. **Auto Import**：
   自动查找、解析并提供代码操作和代码完成。

5. **React Developer Tools**：
   React 调试工具的 VSCode 集成，方便在编辑器中调试 React 应用。

6. **vscode-styled-components**：
   为 styled-components 提供语法高亮和 IntelliSense。

7. **Debugger for Chrome**：
   在 VSCode 中直接调试运行在 Chrome 中的 JavaScript 代码。

8. **Jest**：
   如果你使用 Jest 进行测试，这个插件可以在 VSCode 中运行和调试测试。

### Theme

 • vscode-icons: 一个高度可定制的图标主题，支持文件和文件夹图标。
 • Material Icon Theme: 一个广泛使用的图标主题，支持 Material Design 风格的图标。
 • Ayu Icons: 提供简洁风格的文件和目录图标。



## install lazyvim

作用：高效配置vim，使用各种vim插件提升code效率

linke: https://www.lazyvim.org/installation

1. Make a backup of your current Neovim files:

```shell
# required
mv ~/.config/nvim{,.bak}

# optional but recommended
mv ~/.local/share/nvim{,.bak}
mv ~/.local/state/nvim{,.bak}
mv ~/.cache/nvim{,.bak}
```

2. Clone the starter

```shell
git clone https://github.com/LazyVim/starter ~/.config/nvim
```

3. Remove the `.git` folder, so you can add it to your own repo later

```shell
rm -rf ~/.config/nvim/.git
```

4. Start Neovim!

```shell
nvim
```

## vscode configuration
### setting

``` json
{


}
```



### plugins

- Name: Noctis
Id: liviuschera.noctis
Description: Noctis is a collection of light & dark themes with a well balanced blend of warm and cold colors
Version: 10.43.3
Publisher: Liviu Schera
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=liviuschera.noctis

- Name: Material Icon Theme
Id: PKief.material-icon-theme
Description: Material Design Icons for Visual Studio Code
Version: 5.12.0
Publisher: Philipp Kief
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme

- Name: Rainbow Brackets
Id: tal7aouy.rainbow-bracket
Description: A customizable extension for colorizing matching brackets and make your code amazing.
Version: 1.0.2
Publisher: Mhammed Talhaouy
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=tal7aouy.rainbow-bracket



## vscode vim

**mapkeys**

| command | effect               |
| ------- | -------------------- |
| gcc     | comment              |
| gc3j    | comment next 3 lines |
| gc}     | annotated paragph    |
|         |                      |
|         |                      |

**easymotion**

install

```shell
vim.easymotion=true //in setting.json
```

## Lazy vim

```lua

  function _G.set_terminal_keymaps()
  local opts = { buffer = 0 }
  vim.keymap.set("t", "<esc>", [[<C-\><C-n>]], opts)
  vim.keymap.set("t", "jk", [[<C-\><C-n>]], opts)
  vim.keymap.set("t", "<C-h>", [[<Cmd>wincmd h<CR>]], opts)
  vim.keymap.set("t", "<C-j>", [[<Cmd>wincmd j<CR>]], opts)
  vim.keymap.set("t", "<C-k>", [[<Cmd>wincmd k<CR>]], opts)
  vim.keymap.set("t", "<C-l>", [[<Cmd>wincmd l<CR>]], opts)
end

-- if you only want these mappings for toggle term use term://*toggleterm#* instead
vim.cmd("autocmd! TermOpen term://* lua set_terminal_keymaps()")

```

```lua
-- Keymaps are automatically loaded on the VeryLazy event
-- Default keymaps that are always set: https://github.com/LazyLazyVim/blob/main/lua/lazyvim/config/keymaps.lua
-- Add any additional keymaps here
local keymap = vim.keymap

keymap.set("i", "jk", "<Esc>")
keymap.set("n", "<leader>sv", "<C-W>v")
keymap.set("n", "<leader>tt", "<cmd>ToggleTerm<cr>")
keymap.set("n", "<C-j>", "<cmd>TmuxNavigateDown<cr>")
keymap.set("n", "<C-k>", "<cmd>TmuxNavigateUp<cr>")

-- tab nav
keymap.set("n", "<leader>tn", "<cmd>tabnext<cr>")
keymap.set("n", "<leader>tp", "<cmd>tabprev<cr>")
keymap.set("n", "<leader>tl", "<cmd>tablast<cr>")
keymap.set("n", "<leader>tf", "<cmd>tabfirst<cr>")

-- telescope general
keymap.set("n", "<leader>lds", "<cmd>Telescope lsp_document_symbols<cr>")
keymap.set("n", "<leader>tgf", "<cmd>Telescope lsp_references<cr>")
keymap.set("n", "<leader>cbf", "<cmd>Telescope current_buffer_fuzzy_find<cr>")
-- telescope git commands
keymap.set("n", "<leader>gc", "<cmd>Telescope git_commits<cr>") -- list all git commits (use <cr> to checkout) ["gc" for git commits]
keymap.set("n", "<leader>gfc", "<cmd>Telescope git_bcommits<cr>") -- list git commits for current file/buffer (use <cr> to checkout) ["gfc" for git file commits]
keymap.set("n", "<leader>gb", "<cmd>Telescope git_branches<cr>") -- list git branches (use <cr> to checkout) ["gb" for git branch]
keymap.set("n", "<leader>gs", "<cmd>Telescope git_status<cr>") -- list current changes per file with diff preview ["gs" for git status]

-- rust-tools
keymap.set("n", "<leader>ha", "<cmd>RustHoverActions<cr>") -- list current changes per file with diff preview ["gs" for git status]

-- lsp saga
keymap.set("n", "gp", "<cmd>Lspsaga peek_definition<CR>")
keymap.set("n", "<leader>ca", "<cmd>Lspsaga code_action<CR>")
keymap.set("n", "[d", "<cmd>Lspsaga diagnostic_jump_prev<CR>") -- jump to previous diagnostic in buffer
keymap.set("n", "]d", "<cmd>Lspsaga diagnostic_jump_next<CR>")

-- keymap
keymap.set("n", "<leader>hw", ":HopWord<cr>")
keymap.set("n", "<leader>hww", ":HopWordMW<cr>")
keymap.set("n", "<leader>hc", ":HopChar1<cr>")
keymap.set("n", "<leader>hcw", ":HopChar1MW<cr>")

keymap.set("n", "<leader>ge", "<cmd>ChatGPTEditWithInstructions<cr>")
```

### hop

- Leader + h + w (hop + word)
- Leader + h + l (hop + l)

### lsp

```lua
eturn {
  "neovim/nvim-lspconfig",
  init = function()
    local keys = require("lazyvim.plugins.lsp.keymaps").get()
    keys[#keys + 1] = { "<leader>ca", false }
    keys[#keys + 1] = { "]d", false }
    keys[#keys + 1] = { "[d]", false }
  end,
  opts = function(_, opts)
    opts.autoformat = false
  end,
}
```

### neotree

```lua
return {
  "nvim-neo-tree/neo-tree.nvim",
  opts = function(_, opts)
    opts.window.mappings.o = "open"
    opts.window.width = 27
  end,
}
```

## lazyvim 快捷键

- <space>ff 项目中搜索文件
- <space>ds 当前buffer搜索符号，如对象或者方法
- gr : references
- gR File references
- gd 查看定义
- gD go to sourceFile
- gh 查看类的情况
- gI Goto Implemetation
- <leader> cr 修改符号

### window 相关

| **模式** |   快捷键    |       说明       | 所属插件 |
| :------: | :---------: | :--------------: | -------- |
|    n     | <leader> wd |     关闭窗口     | neotree  |
|    n     | <C-h/j/k/l  | 选择上下左右窗口 | neotree  |
|          |             |                  |          |

### neotree

| **模式** |   快捷键    |       说明       |
| :------: | :---------: | :--------------: |
|    n     | <leader> wd |     关闭窗口     |
|    n     | <C-h/j/k/l  | 选择上下左右窗口 |
|          |             |                  |

###

## Idea

### plugin

### IdeaVim

config

```shell
" .ideavimrc is a configuration file for IdeaVim plugin. It uses
"   the same commands as the original .vimrc configuration.
" You can find a list of commands here: https://jb.gg/h38q75
" Find more examples here: https://jb.gg/share-ideavimrc

" set number relativenumer
let mapleader = " "


"" -- Suggested options --
" Show a few lines of context around the cursor. Note that this makes the
" text scroll if you mouse-click near the start or end of the window.
set scrolloff=5

" Do incremental searching.
set incsearch

" Don't use Ex mode, use Q for formatting.
map Q gq
nmap <C-o> :action Back<CR>
nmap <C-i> :action Forward<CR>
nmap <Leader>cr :action RenameElement<CR>
" 映射快捷键：<Leader>gi 跳转到函数实现
nmap <Leader>gi :action GotoImplementation<CR>
nmap <Leader>gr :action GotoReference<CR>
" nnoremap <silent> <Leader>gi :action GotoImplementation<CR>
inoremap jk <ESC>
nmap <Leader>w :action AceAction<CR>
" nnoremap <Leader><Leader> :NERDTreeFind<CR>
nnoremap <Leader>e :NERDTreeToggle<CR>
nnoremap <Leader>sv :NERDTreeMirror<CR>  " 使用水平分割打开
nnoremap <S-l> :tabn<CR>
nnoremap <S-h> :tabp<CR>
nnoremap <Leader>bd :tabclose<CR>
noremap <Leader>wd :action CloseAllEditors<CR>

nnoremap <C-h> <C-w>h
nnoremap <C-l> <C-w>l
nnoremap <C-k> <C-w>k
nnoremap <C-j> <C-w>j
" 使用 <Leader>- 进行水平分割
noremap <Leader>- :action SplitHorizontally<CR>

" 使用 <Leader>| 进行垂直分割
noremap <Leader>\ :action SplitVertically<CR>

" --- Enable IdeaVim plugins https://jb.gg/ideavim-plugins


" Highlight copied text
Plug 'machakann/vim-highlightedyank'
" Commentary plugin
Plug 'tpope/vim-commentary'
" easymotion
Pugin 'easymotion/vim-easymotion'
Plug 'https://github.com/easymotion/vim-easymotion'
Plug 'vim-easymotion'
set easymotion
" nerdtree
Plugin 'preservim/nerdtree'
Plug 'https://github.com/preservim/nerdtree'
Plug 'nerdtree'
set NERDTree

"" -- Map IDE actions to IdeaVim -- https://jb.gg/abva4t
"" Map \r to the Reformat Code action
"map \r <Action>(ReformatCode)

"" Map <leader>d to start debug
"map <leader>d <Action>(Debug)

"" Map \b to toggle the breakpoint on the current line
"map \b <Action>(ToggleLineBreakpoint)

set clipboard=unnamedplus
" 启用忽略大小写
set ignorecase
" 启用智能区分大小写
set smartcase
set which-key

```

#### Idea-vim-plugin

https://github.com/JetBrains/ideavim/wiki/IdeaVim%20Plugins#easymotion

- NERDTree
- 
