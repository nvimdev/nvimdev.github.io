---
title: "Ui Beacon"
tags:
  - lspsaga
weight: 10
---

## Generic UI Options

Generic options for the Lspsaga UI:

- `border = 'single'`
  - Border type, see `:help nvim_open_win`
- `devicon = true`
  - Whether to use nvim-web-devicons
- `title = true`
  - Show title in some float window
- `expand = '⊞'`
  - Expand icon
- `collapse = '⊟'`
  - Collapse icon
- `code_action = '💡'`
  - Code action icon
- `actionfix = ' '`
  - Action fix icon
- `lines = { '┗', '┣', '┃', '━', '┏' }`
  - Symbols used in virtual text connect
- `kind = {}`
  - LSP kind custom table
- `imp_sign = '󰳛 '`
  - Implement icon

## Beacon

In Lspsaga, some commands jump around in buffer(s). With beacon enabled, it will show a beacon to tell you where the cursor is.

- `enable = true`
- `frequency = 7`

## Scrolling Keymaps

Default keymap of `scroll_preview`. For some commands you can use these to scroll within the preview window.

- `scroll_down = '<C-f>'`
- `scroll_up = '<C-b>'`
