---
title: "Diagnostic"
tags:
  - lspsaga
weight: 10
---

## Usage

Invoke `:Lspsaga diangostic_jump_next` and `:Lspsaga diagnostic_jump_prev` to jump around diagnostics.
When the current cursor position has a diagnostic available, the commands will show the diagnostic in a nice float.

![Diagnostic](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/d88f9d9f-fae1-47ca-94d2-8ef536e4eb7f)

You can use `scroll_preview` to preview code action in the diagnostic window. Default keybind is `<C-f>` and `<C-b>`.

![Scroll preview](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/91d9c0a0-ee1e-4f70-9d6b-08e32fad8b98)

Workflow shown in the GIF set `jump_num_shortcut` to true.

1. `[e` was bind to `diagnostic_jump_next` with `vim.keymap.set('n', '[e', '<cmd>Lspsaga diagnostic_jump_next')`
2. The current position has diagnostic, so a diagnostic window is opened in place.
3. Uses `<C-f>` and `<C-b>` to preview code action.
4. Presses `2` to execute code action number 2.

Sometimes when trying to copy the diagnostic message, one would want to jump to diagnostic jump window.
You can use `<C-w>w` and use `keys.quit` to quit the window or move to code action then press `o` to execute code action.

![Action preview](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/ac085c8e-dd6b-4995-8201-c474966abb61)

Change the `Actions` icon by using `ui.actionfix='your icon'`

## Default Options

Default options for the diagnostic module.

- `show_code_action = true`
  - Show code action in diagnostic jump window. It's useful. Suggested to set to `true`
- `jump_num_shortcut = true`
  - Enable number shortcuts to execute code action quickly
- `max_width = 0.8`
  - Diagnostic jump window max width
- `max_height = 0.6`
  - Diagnostic jump window max height
- `text_hl_follow = true`
  - Diagnostic jump window text highlight follow diagnostic type
- `border_follow = true `
  - Diagnostic jump window border follow diagnostic type
- `extend_relatedInformation = false`
  - When have `relatedInformation`, diagnostic message is extended to show it
- `show_layout = 'float'`
  - Config layout of diagnostic window not jump window
- `show_normal_height = 10`
  - Show window height when diagnostic show window layout is normal
- `max_show_width = 0.9`
  - Show window max width when layout is float
- `max_show_height = 0.6`
  - Show window max height when layout is float
- `diagnostic_only_current = false`
  - Only show diagnostic virtual text on the current line

## Default Keymaps

These are default keymaps in `diagnostic.keys` section:

- `exec_action = 'o'` execute action (in jump window)
- `quit = 'q'` quit key for the jump window
- `toggle_or_jump = '<CR>'` toggle or jump to position when in `diagnostic_show` window
- `quit_in_show = { 'q', '<ESC>' }` quit key for the `diagnostic_show window`

## Advanced Configuration

Change options in the diagnostic part of the setup table like config below:

```lua
require('lspsaga').setup({
    diagnostic = {
        max_height = 0.8,
        keys = {
            quit = {'q', '<ESC>'}
        }
    },
})
```

### Diagnostic Jump Filter

If you only want to jump over error with specific severity diagnostic, set your keymap like config below:

```lua
keymap("n", "[E", function()
  require("lspsaga.diagnostic"):goto_prev({ severity = vim.diagnostic.severity.ERROR })
end)
```

### Control the Diagnostic Shown

Lspsaga support showing `cursor`, `line`, `buffer`, and `workspace` diagnostic.

![Diagnostic shown](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/e8e2e3cd-715b-41d4-a526-aa934fe10a80)

You can use `keys.toggle_or_jump` to expand or collapse some file or jump to the diagnostic position.

### Change Diagnostic Window Layout

Specify in command or in setup option `show_layout`, command option has higher priority.
`:Lspsaga show_workspace_diagnostics ++normal` or `:Lspsaga show_workspace_diagnostics ++float`.

![Diagnostic window layout](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/4ab7dba7-58d3-4d5f-9af9-bba7fd61db95)

### Unfocus the Diagnostic Show Float Window

If `++unfocus` was passed in as argument (for instance, `:Lspsaga show_buf_diagnostics ++unfocus`),
The cursor will not jump to the diagnostic show window, and show window will be deleted automatically
when these autocmd events triggers `'CursorMoved', 'CursorMovedI', 'InsertEnter', 'BufDelete', and 'WinScrolled'`.

### Remove Redundant Virtual Text

When you enable Neovim default diagnostic virtual text, it will add diagnostic virtual text whenever possible.
You can set `diagnostic_only_current = true` to show the diagnostic virtual text only in current line.

Note that you need to disable Neovim default diagnostic virtual text by using:

```lua
vim.diagnostic.config({
    virtual_text = false
})
```

![Virtual text](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/2a40e1cc-908d-4576-a32d-afcb27800101)
