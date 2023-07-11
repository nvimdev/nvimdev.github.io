---
title: "Code Action"
tags:
  - lspsaga
weight: 10
---

## Usage

Use `:Lspsaga code_action` to invoke.

![Code action](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/5327de84-9239-451d-89d2-3dd5a9585c06)

### Tips

- If you know the action do, just press the action number.
- If you don't know what the action do, move to it. Take a look at the action preview, then press `<CR>`.

## Default Options

Default options in `code_action` section:

- `num_shortcut = true` whether number shortcut for code actions are enabled
- `show_server_name = false` show language server name
- `extend_gitsigns = false` extend gitsigns plugin diff action

## Default Keymaps

Default keymaps in `code_action.keys` section:

- `quit = 'q'` quit the float window
- `exec = '<CR>'` execute action

## Why Does Lspsaga Show Different Code Action from Neovim Built-in?

Neovim built-in code action uses line diagnostic to request for code action.
Lspsaga uses cursor diagnostic, which removes potential noise from other places in the line.
