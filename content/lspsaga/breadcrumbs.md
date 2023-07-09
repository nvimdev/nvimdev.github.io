---
title: "Breadcrumbs"
tags:
  - lspsaga
weight: 10
---

## Usage

Dynamically render breadcrumb symbols in your winbar, similar to gui IDEs

![Untitled](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/2541c09d-9b5b-4b14-9e4b-d66095e07ba0)

**Important**

This module is the prerequisite for the `outline` and the `implement` module.

## Default Options

Default options in `symbol_in_winbar` section

- `enable = true`
  - enable
- `separator = ' › '`
  - separator symbol
- `hide_keyword = false` when true some symbols like `if` and `for`
  - will be ignored (needs treesitter)
- `show_file = true`
  - show file name before symbols
- `folder_level = 1`
  - show how many folder layers before the file name
- `color_mode = true`
  - true mean the symbol name and icon have same color otherwise symbol name is light-white
- `delay = 300` dynamic render delay

## Use In Custom Statusline or winbar

there has an api that you can use to get a `stl` format symbol string that you can use in statusline

`require(lspsaga.symbol.winbar).get_bar()`
