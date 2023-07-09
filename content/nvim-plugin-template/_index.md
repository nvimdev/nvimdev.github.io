---
bookCollapseSection: true
weight: 20
---

# [nvim-plugin-template](https://github.com/nvimdev/nvim-plugin-template)

neovim plugin template with ci test and auto doc gen

## Usage

1. Click `use this template` button to generate your own neovim plugin repo
2. Clone your plugin repo. Open terminal then cd into the plugin directory.
3. Run `python3 rename.py your-plugin-name` this will replace all `nvim-plugin-template` to your `pluing-name`. Then it will prompt you to input `y` or `n` to remove example codes in `init.lua` and `test/plugin_spec.lua`. If you are familiar with this repo just type y. If you are new to this template I suggest you look at them first. After these step the `rename.py` will also auto remove itself.

Now you have a clean plugin env. Enjoy!

## Format

Format use `stylua` with builtin `.stylua.toml`.

## Test

Use vusted for tests. Install by using `luarocks --lua-version=5.1 install vusted` then run `vusted test` for your test cases.

Create test case in test folder, file rule is `foo_spec.lua` with `_spec` more usage please check
[busted usage](https://lunarmodules.github.io/busted/)

## Ci

Ci support: auto generate doc from README, run integration test and lint check by `stylua`.

## More

For more usage you can take a look at my other plugins

## License MIT
