---
bookCollapseSection: true
weight: 20
---

# [nvim-plugin-template](https://github.com/nvimdev/nvim-plugin-template)

Neovim plugin template with CI test and docs publish.

## Usage

1. Click `use this template` button to generate your own Neovim plugin repository.
2. Clone your plugin repository. Open terminal then `cd` into the plugin directory.
3. Run `python3 rename.py your-plugin-name`, this will replace all `nvim-plugin-template` to your `plugin-name`. Then it will prompt you to input `y` or `n` to remove example codes in `init.lua` and `test/plugin_spec.lua`. If you are familiar with this repository, just type `y`. If you are new to this template, I suggest you look at them first. After these step, the `rename.py` will also auto remove itself.

Now you have a clean plugin environment. Enjoy!

## Format

Format use `stylua` with built-in `.stylua.toml`.

## Test

Use vusted for test. Install by using `luarocks --lua-version=5.1 install vusted` then run `vusted test` for your test cases.

Create test case in `test` directory. File rule is `foo_spec.lua` with `_spec`.

More usage please check [busted usage](https://lunarmodules.github.io/busted/).

## CI

CI support: auto generate documentation from README. Run integration test and lint check by `stylua`.

## More

For more usage, you can take a look at my other plugins.

## License

Licensed under the [MIT](https://github.com/nvimdev/nvim-plugin-template/blob/main/LICENSE) license.
