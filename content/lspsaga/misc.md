---
title: "Breadcrumbs"
tags:
  - lspsaga
weight: 10
---

## Generic UI Options

Generic options for the lspsaga UI

- `border = 'single'`
  - border type, see `:help nvim_open_win`
- `devicon = true`
  - whether to use nvim-web-devicon
- `title = true`
  - show title in some float window
- `expand = '⊞'`
  - expand icon
- `collapse = '⊟'`
  - collapse icon
- `code_action = '💡'`
  - code action icon
- `actionfix = ' '`
  - action fix icon
- `lines = { '┗', '┣', '┃', '━', '┏' }`
  - symbols used in virtual text connect
- `kind = {}`
  - lsp kind custom table
- `imp_sign = '󰳛 '`
  - implement icon

## Beacon

In lspsaga some commands jump around in buffer(s). With beacon enabled it will show a beacon to tell you where the cursor is.

- `enable = true`
- `frequency = 7`

## Scrolling keymap

Default keymap of `scroll_preview`. For some commands you can use these to scroll within the preview window.

- `scroll_down = '<C-f>'`
- `scroll_up = '<C-b>'`
