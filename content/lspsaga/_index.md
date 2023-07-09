---
bookCollapseSection: true
weight: 20
---

## Lspsaga

Improves the neovim built-in lsp experience.

## Install

- lazy.nvim

```lua
require('lazy').setup(
    {
    'nvimdev/lspsaga.nvim',
    ft = {filetypes}, -- or you can make it an dependency of lspconfig
    config = function()
        require('lspsaga').setup({})
    end
    }
)
```

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

> [Miscellaneous: Options that apply to all modules](/lspsaga/misc)

## Trouble Shooting

> [Create An Issue](https://github.com/nvimdev/lspsaga.nvim/issues/new?assignees=&labels=bug&projects=&template=bug_report.yml)

> [Feature Request](https://github.com/nvimdev/lspsaga.nvim/issues/new?assignees=&labels=enhancement&projects=&template=feature_request.md&title=)
