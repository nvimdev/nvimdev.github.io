---
title: "Definition"
tags:
  - lspasga
weight: 10
---

## Usage

Invoke by running `:Lspsaga peek_definition` and `:Lspsaga peek_type_definition`.
Layout is `drawer` and is currently the only one available.
If you want to go to the definition, use `:Lspsaga goto_definition` and `:Lspsaga goto_type_definition`.

![Definition](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/b4f1b724-7d6a-49cc-9b4b-6c95b49abae7)

## Default Options

Default options in `definition` section:

- `width = 0.6` defines float window width
- `height = 0.5` defines float window height

## Default Keymaps

- `edit = '<C-c>o'`
- `vsplit = '<C-c>v'`
- `split = '<C-c>i'`
- `tabe = '<C-c>t'`
- `quit = 'q'`
- `close = '<C-c>k'`

### Why the Keymaps Are Not a Single Character?

It calls `peek_definition`, meaning you can edit and save in drawer window. The buffer is just a normal buffer.
To avoid keymap conflict, a prefix `<C-c>` was used. If you are sure you won't do any editing in the `peek_definition` window, 
you can tell Lspsaga to use a single character keymaps like config below:

```lua
require('lspsaga').setup({
    definition = {
        keys = {
            edit = 'o'
        }
    }
})
```

> Maybe support for multiple keymap layout is a good way? Like `:Lspsaga peek_definition key_1`? IDK
