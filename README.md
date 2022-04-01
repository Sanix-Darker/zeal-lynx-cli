
# About

A small script to show Zeal (https://zealdocs.org/) pages
in terminal -- in the Lynx web browser.

# Requirements

- python3 with argparse, zdg, sqlite3, pathlib and BeautifulSoup (bs4)
- Zeal (install the desired documentation sets from its GUI)
- Lynx web browser

# Usage

To show a list of all available pages in a docset:

    zeal-cli DOCSET_NAME

To show a particular page in a docset:

    zeal-cli DOCSET_NAME PAGE

See the documentation in the `zeal-cli` file for more.

# Usage with FZF from the shell

If you want to fuzzy search for documentation from shell,
you can use FZF (https://github.com/junegunn/fzf/) with zeal-cli
in a manner similar to this (though you should probably write a
proper function that handles cancelling FZF):

    zeal-cli cpp | fzf --height=50% --preview='zeal-cli --lynx-dump=true cpp {}' | xargs -d '\n' zeal-cli cpp


# Installation

Copy `zeal-cli` somewhere in your `$PATH` and `chmod +x` it.

# Screenshot

When used in Neovim + Telescope:

![zeal](https://gitlab.com/manning-fpcpp-book/zeal-lynx-cli/-/wikis/uploads/af9817577bf8f696201489913e7a1a16/zeal.jpeg)

# License

GPL 2 or later
