---
title: "Breadcrumbs"
tags:
  - lspsaga
weight: 10
---

## Usage

Dynamically render breadcrumb symbols in your winbar, similar to IDEs

![breadcrumb](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/2541c09d-9b5b-4b14-9e4b-d66095e07ba0)

**Important**

This module is the prerequisite for the `outline` and the `implement` module.

## Default Options

Default options in `symbol_in_winbar` section:

- `enable = true`
  - Enable
- `separator = ' › '`
  - Separator symbol
- `hide_keyword = false` when true some symbols like `if` and `for`
  - Will be ignored (need treesitter)
- `show_file = true`
  - Show file name before symbols
- `folder_level = 1`
  - Show how many folder layers before the file name
- `color_mode = true`
  - `true` mean the symbol name and icon have same color. Otherwise, symbol name is light-white
- `delay = 300` 
  - Dynamic render delay

## Use in Custom Statusline or Winbar

There's an API that you can use to get the `stl` format symbol string that you can use in statusline.

```lua
require(lspsaga.symbol.winbar).get_bar()
```
