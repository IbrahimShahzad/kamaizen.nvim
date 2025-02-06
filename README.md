# KamaiZen-nvim

Neovim plugin to integrate the [KamaiZen Language Server](https://github.com/IbrahimShahzad/KamaiZen) for Kamailio configuration files.

## Installation

with [lazy.nvim](https://github.com/folke/lazy.nvim):
```lua
    {
      'batoaqaa/kamaizen.nvim' -- replace this with your {user_name}/{repo_name}
      dependencies = {
        { 'IbrahimShahzad/KamaiZen', build = 'go build' },
      },
      opts = {
        settings = {
          kamaizen = {
            enableDeprecatedCommentHint = false, -- to enable hints for '#' comments
            KamailioSourcePath = vim.fn.getcwd(),
            loglevel = 3,
          },
        },
      },
    }
```
