# wishlist
A public catalogue of Lua plugins Neovim users would really like to see exist

## Contributing
If you have an idea for a Lua plugin, or know of an existing plugin implementing one of the ideas listed here, please make a PR (adding to this README) or an issue!

## Ideas
### Git library
**What?** 
A Lua library for working with git/other VCS information in Neovim. Kind of an equivalent to https://github.com/tpope/vim-fugitive or https://github.com/mhinz/vim-signify

**Why?** 
The existing VCS solutions for Vim/Neovim are written in Vimscript and are fairly complicated and expensive to load. Additionally, interfacing with VCS is a common problem for some classes of plugin - plugin managers, statuslines, etc. A Lua library, using `vim.loop` to asynchronously run VCS software and handling things like branch detection, change counting while editing, cloning, displaying changes, making commits, and pushing/pulling (among other functionality) would reduce effort duplication and increase performance.

**Potential existing implementations**
Some rudimentary branch detection/change tracking functionality is implemented in https://github.com/wbthomason/dotfiles/blob/linux/neovim/.config/nvim/lua/git.lua. Vimscript plugins like `fugitive` and `signify` can be used as references for some of the tricker bits of working with `git`.

**Potential pitfalls**
`fugitive` and the like are complex plugins to replicate.

### A "standard library"
**What?**
A Lua library collecting useful utilities and functions for writing Lua in/for Neovim.

**Why?**
The `vim` module already provides a decent standard library for this purpose, but there's still a lot of functionality that gets commonly reimplemented by plugin authors - things like functional programming combinators (`map`, `fold`, etc.), utilities for working with paths, wrappers around `vim.loop.spawn` for working with jobs, etc. To encourage code reuse, it would be useful to have a "standard library++" including these tools.

**Potential existing implementations**
https://github.com/nvim-lua/plenary.nvim is already working toward this!

**Potential pitfalls**
What should be included/excluded to keep the library useful without bloat?
