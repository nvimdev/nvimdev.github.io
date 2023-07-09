---
title: "Hover"
tags:
  - lspasga
weight: 10
---

## Usage

Run `:Lspsaga hover_doc`. If a hover window is opened then the command would close it.

![image](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/eb370389-ba84-4dbc-b08b-adbee358aedb)

Use `:Lspsaga hover_doc ++keep` when you want keep the hover window, it will pin the hover window to the top right of your buffer.

![image](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/cb25b8ea-6437-44a1-9864-57d118c7457f)

Keymap example:

```lua
vim.keymap.set('n', 'K', '<cmd>Lspsaga hover_doc')
```

## Prerequisite

You need to install the Treesitter `markdown` and `markdown_inline` parser. If you are not sure if you have them run `:checkhealth` .
Why? Unlike the built-in hover `vim.lsp.buf.hover`, which uses regex syntax to render markdown, Lspsaga uses treesitter.

## Default Options

default options in `hover` section.

- `max_width = 0.9` defines float window width
- `max_height = 0.8` defines float window height
- `open_link = 'gx'` key for opening links
- `open_cmd = '!chrome'` cmd for opening links

## Advanced Configuration

Lspsaga hover supports opening external links in hover window. The default keybinding is `gx`. The default command is `!open` on mac, `!explorer` on windows, `!wslview` on wsl, `!xdg-open` on linux. If these commands are not found Lspsaga will use `open_cmd`.

![Untitled](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/30adcdcd-cbda-4442-ab23-e4ff37e42b7e)

workflow in gif:

- Press `K` to open lspsaga hover
- Press k twice to jump into the hover window and view the doc
- Press gx

### Highlight Groups

- `HoverNormal` Hover window normal highlight.
- `HoverBorder ` Hover window border highlight.
