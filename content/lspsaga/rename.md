---
title: "Rename"
tags:
  - lspasga
weight: 10
---

## Usage

Run `:Lspsaga rename`. Other than opening the float input window it will also highlight the references in this buffer.

![Rename](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/bb81149a-d24e-4f14-a8b5-ddf0cc1d9908)

## Default Options

Default options in `rename` section:

- `in_select = true`
  - Default is `true`. Whether the name is selected when the float opens
  - In some situation, just like want to change one or less characters, `in_select` is not so useful. You can tell the Lspsaga to start in normal mode using an extra argument like `:Lspsaga lsp_rename mode=n`
- `auto_save = false`
  - Auto save file when the rename is done
- `project_max_width = 0.5`
  - Width for the `project_replace` float window
- `project_max_height = 0.5`
  - Height for the `project_replace` float window

## Default Keymaps

Default keymap in `rename.keys` section:

- `quit = '<C-k>'` quit rename window or `project_replace` window
- `exec = '<CR>'` execute rename in `rename` window or execute replace in `project_replace` window
- `select = 'x'` select or cancel select item in `project_replace` float window

## Project-wide Replace

LSP rename can only rename language symbols. Lspsaga provide async project level search and replace by using `rg`,
so make sure it's installed if you want to use this feature.

Run `:Lspsaga project_replace old_name new_name`. It will search the whole project to find `old_name` and show if in a float window.

![Project-wide replace](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/5afdbf13-f88a-4adc-8f79-5fd48da61743)

- use `rename.keys.select` to select item to rename
- use `rename.keys.exec` to execute `new_name` replace

## LSP Integration

Use `++project` flag for the `lsp_rename` command (`:Lspsaga lsp_rename ++project`)

After the LSP rename is done, and if the name still exists somewhere within the project, the `project_replace` window would pop out.
