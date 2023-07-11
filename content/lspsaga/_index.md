---
bookCollapseSection: true
weight: 20
---

<center>
<img src="/lspsaga/logo.png" width="20%" height="20%"/>
</center>

# [lspsaga.nvim](https://github.com/nvimdev/lspsaga.nvim)

Improves the Neovim built-in LSP experience.

## Installation  

### lazy.nvim

```lua
require('lazy').setup({
    'nvimdev/lspsaga.nvim',
    config = function()
        require('lspsaga').setup({})
    end,
    dependencies = {
        'nvim-treesitter/nvim-treesitter' -- optional
        'nvim-tree/nvim-web-devicons'     -- optional
    }
})
```

Three ways to lazy load `lspsaga`:

- Use `event = 'LspAttach'` (need latest lazy.nvim 2023-July-9)
- Use `ft = {filetype}` like `ft = {'c','cpp', 'lua', 'rust', 'go'},` 
- As a depend on `nvim-lspconfig`

### packer.nvim

```lua
use ({
    'nvimdev/lspsaga.nvim',
    after = 'nvim-lspconfig',
    config = function()
        require('lspsaga').setup({})
    end,
})
```

## Modules

> [Finder: UI for advanced LSP symbol search](/lspsaga/finder)

> [Diagnostic: Jump between diagnostic and show them in pretty floats](/lspsaga/diagnostic)

> [Peek Definition / Type Definition](/lspsaga/definition)

> [Hover: Prettier hover actions](/lspsaga/hover)

> [Rename: LSP rename and async project search & replace](/lspsaga/rename)

> [Callhierarchy Incoming / Outgoing calls](/lspsaga/callhierarchy)

> [Code Action: Pretty UI for code actions with live preview](/lspsaga/codeaction)

> [LightBulb: VSCode like lightbulb indicating possible code actions](/lspsaga/lightbulb)

> [Breadcrumbs: IDE like symbol outline on your winbar](/lspsaga/breadcrumbs)

> [Outline: IDE like symbols outline](/lspsaga/outline)

> [Implement: Easily see number of implementations and quickly jump to them](/lspsaga/implement)

> [Float Term: A simple float terminal](/lspsaga/floaterm)

> [Miscellaneous: Options that apply to all modules](/lspsaga/misc)

## Troubleshooting 

> [Create an issue](https://github.com/nvimdev/lspsaga.nvim/issues/new?assignees=&labels=bug&projects=&template=bug_report.yml)

> [Feature request](https://github.com/nvimdev/lspsaga.nvim/issues/new?assignees=&labels=enhancement&projects=&template=feature_request.md&title=)
