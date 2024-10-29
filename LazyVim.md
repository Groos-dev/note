# LazyVim

## Plugins

### nvim-cpm

提升作用，提示源有buffer，lsp，snippt

https://github.com/hrsh7th/cmp-buffer

依赖插件

- cmp-buffer
- cmp-emoji
- cmp-nvim-lsp
- cmp-path
- nvim-snippets

### bufferline.nvim

显示table标签

### nui.nvim

https://github.com/MunifTanjim/nui.nvim

用来定制窗口，弹出选项框的样式，文字

### dracula.nvim

一个主题配色

https://github.com/Mofiqul/dracula.nvim

### dashboard-nvim

定制nvim启动界面 

依赖插件

- nvim-tree/nvim-web-devicons

使用

```lua
return {
  "nvimdev/dashboard-nvim",
  event = "VimEnter",
  config = function()
    require("dashboard").setup({
      theme = "hyper",
      config = {
        week_header = {
          enable = true,
        },
        shortcut = {
          { desc = "󰊳 Update", group = "@property", action = "Lazy update", key = "u" },
          {
            icon = " ",
            icon_hl = "@variable",
            desc = "Files",
            group = "Label",
            action = "Telescope find_files",
            key = "f",
          },
          {
            desc = " Apps",
            group = "DiagnosticHint",
            action = "Telescope app",
            key = "a",
          },
          {
            desc = " dotfiles",
            group = "Number",
            action = "Telescope dotfiles",
            key = "d",
          },
        },
      },
      -- config
    })
  end,
  dependencies = { { "nvim-tree/nvim-web-devicons" } },
}

```

