---
bookCollapseSection: true
weight: 20
---

<center>
<img src="/lspsaga/logo.png" width="20%" height="20%"/>
</center>

## Lspsaga

Improves the neovim built-in lsp experience.

## Install

- lazy.nvim

```lua
require('lazy').setup(
    {
    'nvimdev/lspsaga.nvim',
    config = function()
        require('lspsaga').setup({})
    end,
    dependenices = {
        'nvim-treesitter/nvim-treesitter' optional
        'nvim-tree/nvim-web-devicons'     optional
    }
    }
)
```

three ways to lazy load `lspsaga`

-  use `event = 'LspAttach'` (need latest lazy.nvim 2023-july-9)
-  use `ft = {filetype}` like `ft = {'c','cpp', 'lua', 'rust', 'go'},` 
-  as a depend on `nvim-lspconfig`

## Modules

> [Finder: UI interface for advanced lsp symbol search](/lspsaga/finder)

> [Diagnostic: Jump between diagnostic and show them in pretty floats](/lspsaga/diagnostic)

> [Peek Definition / Type Definition](/lspsaga/definition)

> [Hover: Prettier hover actions](/lspsaga/hover)

> [Rename: lsp rename and async project search & replace](/lspsaga/rename)

> [Callhierarchy Incoming / Outgoing calls](/lspsaga/callhierarchy)

> [Code Action: pretty UI for code actions with live preview](/lspsaga/codeaction)

> [LightBulb: VSC like lightbulb indicating possible code actions](/lspsaga/lightbulb)

> [Breadcrumbs: IDE like symbol outline on your winbar](/lspsaga/breadcrumbs)

> [Outline: IDE like symbols outline](/lspsaga/outline)

> [Implement: Easily see number of implementations and quickly jump to them](/lspsaga/implement)

> [Float Term: A simply float terminal](/lspsaga/floaterm)

> [Miscellaneous: Options that apply to all modules](/lspsaga/misc)

## Trouble Shooting

> [Create An Issue](https://github.com/nvimdev/lspsaga.nvim/issues/new?assignees=&labels=bug&projects=&template=bug_report.yml)

> [Feature Request](https://github.com/nvimdev/lspsaga.nvim/issues/new?assignees=&labels=enhancement&projects=&template=feature_request.md&title=)
