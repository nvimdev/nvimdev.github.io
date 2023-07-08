---
bookCollapseSection: true
weight: 20
---

## What is the Lspsaga

Improve neovim built-in lsp experiences. 

## Install

- lazy.nvim

```lua
require('lazy').setup(
    {
    'nvimdev/lspsaga.nvim',
    ft = {filetypes}, -- or as lspconfig dependencies for lazyload
    config = function()
        require('lspsaga').setup({})
    end
    }
)
```


## Features

> [Finder an Ui interface show lsp methods result](/lspsaga/finder)

> [Diagnostic Jump / Show](/lspsaga/diagnostic)

> [Peek Definition / Type Definition](/lspsaga/definition)

> [Hover](/lspsaga/hover)

> [Rename](/lspsaga/rename)

> [Callhierarchy Icoming /Outgoing calls](/lspsaga/callhierarchy)

> [Code Action](/lspsaga/codeaction)

> [LightBulb](/lspsaga/lightbulb)

> [Symbols In Winbar](/lspsaga/symbolswinbar)

> [Outline](/lspsaga/outline)

> [Implement](/lspsaga/implement)

## Trouble Shooting

> [Create An Issue](https://github.com/nvimdev/lspsaga.nvim/issues/new?assignees=&labels=bug&projects=&template=bug_report.yml)

> [Feature Request](https://github.com/nvimdev/lspsaga.nvim/issues/new?assignees=&labels=enhancement&projects=&template=feature_request.md&title=)
