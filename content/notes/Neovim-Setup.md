---
title: My Neovim Setup
date: 2022-06-02 17:39:00
tags:
    - Editor
    - NeoVim
    - NvChad
category: tech
keywords:
    - Windows
    - Neovim
    - ricing
    - dotfiles
---


# Welcome

I'd wasted a huge amount of time and nerves while installing **neovim** in Windows 10. I'd decided to share step by step algorithm with others to save their time.
## Remarks:
-   **If you don't need any plugins, it's enough to make only 2 first steps**
-   **Python is required by many plugins, if you don't need it you can skip 8th and 9th steps**
-   **There several other options to manage plugins. I use Plug. If you don't need them make only first 2 steps**

I recommend downloading cmder terminal to have linux commands on windows.

## Here's the algorithm:
1.  Download nvim and unpack it to `C:\Program Files\`
2.  Add env variable linking to that folder. `C:\Program Files\Neovim\bin\`
3.  Create `.config` folder in `~/`
4.  Create `nvim` folder in `~/.config/`
5.  Create `init.vim` file in `~/.config/nvim/`
6.  Create `autoload` folder in `~/.config/nvim/`
7.  Download `plug.vim` to `~/.config/nvim/autoload/`
8.  Install `python >= 2.7` or `py3`
9.  Install neovim package via python - `pip install neovim`
10.  Add plugins to `~/.config/nvim/init.vim`
11.  Open nvim `nvim`
12.  Run `:PlugInstall`