---
title: "LightBulb"
tags:
  - lspasga
weight: 10
---

## Usage

Automatically show lightbulbs when the current line has available code actions.

![lightbulb](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/080e8595-1cfa-460b-9573-a3ae6c144282)

## Default Options

- `enable = true` enable
- `sign = true` show sign in status column
- `virtual_text = true` show virtual text at the end of line
- `debounce = 10` timer debounce
- `sign_priority = 40` sign priority

## How to Change the Sign

The sign uses `ui.code_action` (see [misc.md](/lspsaga/misc)):

```lua
require('lspsaga').setup({
    ui = {
        code_action = 'your icon'
    }
})
```
