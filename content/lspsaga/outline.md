---
title: "Outline"
tags:
  - lspasga
weight: 10
---

## Usage

Run `:Lspsaga outline`

![image](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/a6c81350-3282-4e3a-b373-5e6216f1d83f)

### In Float Window

![image](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/4932adf6-a717-496d-8b13-227300aa8442)

## Default Options

Enable the breadcrumbs feature `symbols_in_winbar.enable = true` or this module would not work
default options of `outline` section.

- `win_position = 'right'` window position
- `win_width = 30` window width
- `auto_preview = true` auto preview when cursor moved in outline window
- `detail = true` show detail
- `auto_close = true` auto close itself when outline window is last window
- `close_after_jump = false` close after jump
- `layout = 'normal'`  float or normal default is normal when is float above options will ignored
- `max_height = 0.5`   height of outline float layout
- `left_width = 0.3`   width of outline float layout left window

## Default keymaps

Default keymaps in `outline.keys` section.

- `toggle_or_jump = 'o'` toggle or jump
- `quit = 'q'` quit outline window
- `jump = 'e'` jump to pos even on a expand/collapse node
