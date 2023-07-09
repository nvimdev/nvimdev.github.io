---
title: ":Lspsaga finder"
tags:
  - lspasga
weight: 10
---

## Usage

Finder is an ui interface to show lsp methods search result.

Invoke `:Lspsaga finder` and you will see the finder window. By default it shows results for `references` and `implementation`.

![image](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/1d957dda-5825-4d15-8d5a-ca5dd7ca63a9)

## Default Options

These are default options in `finder` section of the setup table.

- `max_height = 0.5`
  - max_height of the finder window
- `left_width = 0.3`
  - width of the left finder window
- `default = 'ref+imp'`
  - default search results shown, ref for `references` and imp for `implementation`
- `methods = {}`
  - key is alias of lsp methods, value is lsp methods which you want show in finder, more info below.
  - for instance, methods = { 'tyd' = 'textDocument/typeDefinition' }
- `layout = 'float'` available value is `normal` or `float`
  - normal will use normal layout window priority is lower than command layout
- `filter = {}`
  - key is lsp method value is a filter handler function parameter are `client_id` `result`

## Default Keymap

these are defaule keymaps in `finder.keys` table section.

- `shuttle = '[w'` shuttle bettween the finder layout window
- `toggle_or_open = 'o'` toggle expand or open
- `vsplit = 's'` open in vsplit
- `split = 'i'` open in split
- `tabe = 't'` open in tabe
- `tabnew = 'r'` open in new tab
- `quit = 'q'` quit the finder, only works in layout left window
- `close = '<C-c>k'` close finder

## Advanced Configuration

put the option which you want change in `setup` function parameter table. like

```lua
require('lspsaga').setup({
  finder = {
    max_height = 0.6
    keys = {
      vsplit = 'v'
    }
  }
})
```

### Change Lsp Search Options

![image](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/27541a92-9691-4df3-8d18-c4b88ec4ce5e)

You can change the `default` option like `default = 'def+ref+imp'` it will show `definition` `references` `implementation`. Or, you can specify the search options as command arguments, for instance `:Lspsaga finder def+ref` which will not show implementations. Note that command line options overrides the setup options

You can use single alias or combine alias in `finder`. The following are both correct.

```vim
:Lspsaga finder ref      same as default = 'ref'
:Lspsaga finder def+ref  same as default = 'def+ref'
```

and more with your custom `methods`. **This is the extensibility of finder now.**

**How can I add new methods which I want show in finder ?**

Simply put them in the config table. The methods table takes in a key which is method alias that you can use in command or `default` option, the value is the corresponding lsp method (usually `textDocument/foo` ). For example I want finder to show `textDocument/typeDefinition` in search results:

```lua
require('lspsaga').setup({
  finder = {
    methods = {
      'tyd' = 'textDocument/typeDefinition'
    }
  }
})
```

then you can do `:Lspsaga finder tyd` or combine other methods `:Lspsaga finder tyd+ref+def` or use in `default = 'typd+ref`
Showcase: `:Lspsaga finder tyd+ref+imp+def` (same as `default ='tyd+ref+imp+def'`)

![image](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/fcf2bb52-288f-480d-9c9e-342b4f450da7)

By default there are 3 builtin aliases: `def` -> `textDocument/definition`, `ref` -> `textDocument/references`, `imp` -> `textDocuemnt/implementation`

Notice current indent highlight is provided by `finder` and not by any third-party plugin. It will disappear when you jump to other windows. If you see the indent line provide by other indent plugin please consider add `sagafinder` filetype to that plugin's exclude list.

![Untitled](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/009990db-5ba5-455b-ab3f-d9bd25904cf0)

### Change Finder Layout

Same as the search options. You can specify the layout either in the setup function or pass in a command arg (prefix it with `++`, for instance `:Lspsaga finder ++normal`), similarly, the command line argument overrides the config table. Available values are `normal ` and `layout` .

![image](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/df566e6f-fd45-47c2-a34e-b70ab248f400)

### Filter Search Results

You can use the `filter` option to filter lsp methods result, key is method and value is a lua function with parameter `client_id` and `result`. The function should return a boolean. As an example:

```lua
require('lspsaga').setup({
  finder = {
    filter = {
      ['textDocument/references']  = function(client_id, result)
        -- your logic
        return true
      end
    }
  }
})
```

### Highlight group

- `SagaNormal` Window normal highlight for finder
- `SagaBorder` Border for the float layout of finder
