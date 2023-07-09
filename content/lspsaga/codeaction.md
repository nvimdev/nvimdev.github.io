---
title: "Code Action"
tags:
  - lspsaga
weight: 10
---

## Usage

Use `:Lspsaga code_action` to invoke

![image](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/5327de84-9239-451d-89d2-3dd5a9585c06)

tips

- if you know the action do just press the action number
- if you don't know what the action do move to it, take a look at the action preview, then press `CR`

## Default Options

default options in `code_action` section.

- `num_shortcut = true` whether number shortcut for code actions are enabled
- `show_server_name = false` show language server name
- `extend_gitsigns = false` extend gitsigns plugin diff action

## Default keymaps

defualt keymap in `code_action.keys` section.

- `quit = 'q'` quit the float window
- `exec = '<CR>'` execuate action

## Why does Lspsaga show different code actions from neovim's builtin one?

Neovim's builtin code action uses line diagnostic to request for code action. Lspsaga uses cursor diagnostic, which removes potential noise from other places in the line.
