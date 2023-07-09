---
bookCollapseSection: true
weight: 20
---

# [indentmini.nvim](https://github.com/nvimdev/indentmini.nvim)

A minimal and blazing fast indentline plugin by using `nvim_set_decoration_provide` api

## Install

- Lazy.nvim

```lua
require('lazy').setup({
    'nvimdev/indentmini.nvim',
    event = 'BufEnter',
    config = function()
        require('indentmini').setup()
    end,
})
```

## Config

- char -- string type, default is `│`,
- exclude -- table type, add excluded filetype in this table

Highlight group is `IndentLine`. You can use this to link it to `Comment`

```lua
config = function()
    require("indentmini").setup({
        char = "|",
        exclude = {
            "erlang",
            "markdown",
        }
    })
    -- use comment color
    vim.cmd.highlight("default link IndentLine Comment")
end,
```

## License MIT
