---
title: "Finder"
tags:
  - lspasga
weight: 10
---

## Usage

Finder is an UI to show LSP methods search result.

Invoke `:Lspsaga finder` and you will see the finder window.
By default it shows results for `references` and `implementation`.

![image](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/e897f717-e2e1-4d28-a4d6-1d12afd707e3)

## Default Options

These are default options in `finder` section:

- `max_height = 0.5`
  - `max_height` of the finder window (float layout)
- `left_width = 0.3`
  - Width of the left finder window (float layout)
- `right_width = 0.3`
  - Width of the right finder window (float layout)
- `default = 'ref+imp'`
  - Default search results shown, `ref` for "references" and `imp` for "implementation"
- `methods = {}`
  - Keys are alias of LSP methods. Values are LSP methods, which you want show in finder. More info below
  - For instance, `methods = { 'tyd' = 'textDocument/typeDefinition' }`
- `layout = 'float'` available value is `normal` and `float`
  - `normal` will use the normal layout window priority is lower than command layout
- `filter = {}`
  - Keys are LSP methods. Values are a filter handler. Function parameter are `client_id` and `result`
- `silent = false`
  - If it's `true`, it will disable show the no response message

## Default Keymaps

These are default keymaps in `finder.keys` table section:

- `shuttle = '[w'` shuttle bettween the finder layout window
- `toggle_or_open = 'o'` toggle expand or open
- `vsplit = 's'` open in vsplit
- `split = 'i'` open in split
- `tabe = 't'` open in tabe
- `tabnew = 'r'` open in new tab
- `quit = 'q'` quit the finder, only works in layout left window
- `close = '<C-c>k'` close finder

## Advanced Configuration

Put the option, which you want change in `setup` function parameter table like config below:

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

### Change LSP Search Options

![LSP search option](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/27541a92-9691-4df3-8d18-c4b88ec4ce5e)

You can change the `default` option like `default = 'def+ref+imp'`. It will show "definition",
"references", and "implementation". Or, you can specify the search options as command arguments,
for instance `:Lspsaga finder def+ref` which will not show implementations.
Note that command line options overrides the setup options.

You can use single alias or combine alias in `finder`. The following are both correct:

```vim
:Lspsaga finder ref      " same as default = 'ref'
:Lspsaga finder def+ref  " same as default = 'def+ref'
```

And more with your custom `methods`. **This is the extensibility of finder now**.

### How Can I Add New Methods Which I Want Show in Finder?

Simply put them in the config table. The methods table takes in a key which is method alias
that you can use in command or `default` option. The value is the corresponding LSP method (usually `textDocument/foo`).
For example, I want finder to show `textDocument/typeDefinition` in search results:

```lua
require('lspsaga').setup({
  finder = {
    methods = {
      'tyd' = 'textDocument/typeDefinition'
    }
  }
})
```

Then you can do `:Lspsaga finder tyd` or combine other methods such as `:Lspsaga finder tyd+ref+def` or use in `default = 'typd+ref'`.

Showcase: `:Lspsaga finder tyd+ref+imp+def` (same as `default ='tyd+ref+imp+def'`)

![Finder showcase](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/fcf2bb52-288f-480d-9c9e-342b4f450da7)

By default, there are 3 built-in aliases: `def` -> `textDocument/definition`, `ref` -> `textDocument/references`,
and `imp` -> `textDocuemnt/implementation`.

Notice current indent highlight is provided by `finder` and not by any third-party plugin.
It will disappear when you jump to other windows. If you see the indent line provide by other indent plugin,
please consider add `sagafinder` filetype to that plugin's exclude list.

![Finder highlight](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/009990db-5ba5-455b-ab3f-d9bd25904cf0)

### Change Finder Layout

Same as the search options, you can specify the layout either in the setup function or pass in a command arg
(prefix it with `++`, for instance `:Lspsaga finder ++normal`). Similarly, the command line argument overrides the config table. 
Available values are `normal` and `layout`.

![Finder layout](https://github.com/nvimdev/lspsaga.nvim/assets/41671631/df566e6f-fd45-47c2-a34e-b70ab248f400)

### Jump In Layout

The right window also is `peek`. That means, you can do edit on right window.

You can use the `keys.shuttle` to jump between the window, jump to right, or jump to left. Suggest workflow is:

- `keys.shuttle` default is `[w` to right. Do some edit, `:w` save file
- `keys.shuttle` to left or use `keys.close` to close layout window in right

**keys.close** can both work on left or right of layout windows.

### Filter Search Result

You can use the `filter` option to filter LSP methods result. The keys are method, 
and values are Lua function with `client_id` and `result` parameter.
The function should return a boolean. As an example:

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

### Vsplit/Split in an exist window

when you have multiple window which create by split or vsplit and you want open file in these window
by using `vsplit` `split` keymap in finder . you can use `++inexist` flag in command .like

```
:Lspsaga finder ++inexist
```

### Highlight Group

- `SagaNormal` window normal highlight for finder
- `SagaBorder` border for the float layout of finder
