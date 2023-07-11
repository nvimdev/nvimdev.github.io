---
title: "Hover"
tags:
  - lspasga
weight: 10
---

## Usage

Run `:Lspsaga hover_doc`. If a hover window is opened, then the command would close it.

![Hover doc](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/eb370389-ba84-4dbc-b08b-adbee358aedb)

Use `:Lspsaga hover_doc ++keep` if you want to keep the hover window. It will pin the hover window to the top right of your buffer.

![Keep hover doc window](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/cb25b8ea-6437-44a1-9864-57d118c7457f)

Keymap example:

```lua
vim.keymap.set('n', 'K', '<cmd>Lspsaga hover_doc')
```

## Prerequisite

You need to install the Treesitter `markdown` and `markdown_inline` parser. If you are not sure if you have them, run `:checkhealth`.

Why? Unlike the built-in hover, `vim.lsp.buf.hover`, which uses regex syntax to render markdown, Lspsaga uses treesitter.

## Default Options

Default options in `hover` section:

- `max_width = 0.9` defines float window width
- `max_height = 0.8` defines float window height
- `open_link = 'gx'` key for opening links
- `open_cmd = '!chrome'` cmd for opening links

## Advanced Configuration

Lspsaga hover support opening external links in hover window. The default keybinding is `gx`.
The default command is `!open` on Mac, `!explorer` on Windows, `!wslview` on WSL, and `!xdg-open` on Linux.
If these commands are not found, Lspsaga will use `open_cmd`.

![Open links in hover window](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/30adcdcd-cbda-4442-ab23-e4ff37e42b7e)

Workflow in GIF:

- Press `K` to open Lspsaga hover
- Press `k` twice to jump into the hover window and view the doc
- Press `gx`

### Highlight Group

- `HoverNormal` hover window normal highlight
- `HoverBorder` hover window border highlight
