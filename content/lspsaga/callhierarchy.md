---
title: "Callhierarchy"
tags:
  - lspsaga
weight: 10
---

## Usage

The callhierarchy module has two commands, `:Lspsaga incoming_calls` and `:Lspsaga outgoing_calls`.

![Callhierarchy](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/20d4001f-57a2-4ad5-87a8-514171c011c1)

## Default Options

Default options in `callhierarchy` section:

- `layout = 'float'` 
  - Layout `normal` and `float`
  - Or you can pass in an extra argument like `:Lspsaga incoming_calls ++normal`, which overrides this option

## Default Keymaps

Default keymaps in `callhierarchy.keys`:

- `edit = 'e'` edit (open) file
- `vsplit = 's'` vsplit
- `split = 'i'` split
- `tabe = 't'` open in new tab
- `quit = 'q'` quit layout
- `shuttle = '[w'` shuttle bettween the layout left and right
- `toggle_or_req = 'u'` toggle or do request
- `close = '<C-c>k'` close layout

## Suggest Workflow

Same as finder, use `keys.shuttle` to jump between the layout windows.
