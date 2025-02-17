# kamaizen-nvim

Neovim plugin to integrate the [KamaiZen Language Server](https://github.com/IbrahimShahzad/KamaiZen) and tree-sitter grammar for Kamailio configuration files.

## Installation

> [!IMPORTANT]  
> Make sure to have golang installed on the system
 
with [lazy.nvim](https://github.com/folke/lazy.nvim):
```lua
    {
      'IbrahimShahzad/kamaizen.nvim',
      dependencies = {
        {
            'IbrahimShahzad/KamaiZen',
            build = = function()
                if vim.fn.executable("go") == 0 then
                    vim.notify("Golang is required to build KamaiZen. Please install Golang.", vim.log.levels.ERROR)
                    return
                end
                vim.fn.system("go build -o KamaiZen")
            end,
            -- Optionally, only load if Go is installed
            cond = function()
                return vim.fn.executable("go") == 1
            end,
        },
      },
      opts = {
        settings = {
          kamaizen = {
            enableDeprecatedCommentHint = false, -- to enable hints for '#' comments
            -- update path to a kamailio source folder if the config is
            -- in a different directory
            KamailioSourcePath = vim.fn.getcwd(),
            loglevel = 3,
          },
        },
      },
    }
```

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.
