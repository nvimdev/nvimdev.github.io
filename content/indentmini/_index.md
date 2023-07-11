---
bookCollapseSection: true
weight: 20
---

# [indentmini.nvim](https://github.com/nvimdev/indentmini.nvim)

A minimal and blazing fast indent line plugin by using `nvim_set_decoration_provide` API.

## Installation 

### lazy.nvim 

```lua
require('lazy').setup({
    'nvimdev/indentmini.nvim',
    event = 'BufEnter',
    config = function()
        require('indentmini').setup()
    end,
})
```

## Configuration

- `char` -- string type. Default is `│`
- `exclude` -- table type. Add excluded file types in this table

Highlight group is `IndentLine`. You can use this to link it to `Comment`.

```lua
config = function()
    require('indentmini').setup({
        char = '|',
        exclude = {
            'erlang',
            'markdown',
        }
    })
    -- use comment color
    vim.cmd.highlight('default link IndentLine Comment')
end,
```

## License

Licensed under the [MIT](https://github.com/nvimdev/indentmini.nvim/blob/main/LICENSE) license.
