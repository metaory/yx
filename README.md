YX
==

Clipboard-centric command executor

USAGE
-----

```sh
yx X|Y [STR...]    # exec|yank args (case insensitive)
[CMD...] | yx x|y  # exec|yank pipe
```

EXAMPLES
--------

```sh
# basic usage
yx y hi           → hi
echo hi | yx y    → hi

# with args
yx X date         → Sun Feb 25 00:00:00 AM +00 2024
date | yx Y now:  → Sun Feb 25 00:00:00 AM +00 2024 now:

# command output
echo ls | yx x    → file1 file2 file3
echo date | yx X +%s → 1708796381
```

INSTALL
-------

```sh
# requires xsel
git clone https://github.com/metaory/yx.git && cd yx && chmod +x yx && ln -sfv $PWD/yx ~/.local/bin/
```

SHELL
-----

```sh
alias -g YY='| yx y'  # pipe→yank
alias -g YX='| yx x'  # pipe→exec
alias yy='yx y'       # args→yank
alias yx='yx x'       # args→exec
```

ENV
---

`YX_SILENT=1` suppress output

SEE
---

[`yank`] [`xsel`] [`xset`] [`xclipboard`] [`wiki.archlinux/Clipboard`]

[MIT](LICENSE)

[`yank`]: https://man.archlinux.org/man/yank.1
[`xsel`]: https://man.archlinux.org/man/xsel.1
[`xset`]: https://man.archlinux.org/man/xset.1
[`xclipboard`]: https://man.archlinux.org/man/xclipboard.1
[`wiki.archlinux/Clipboard`]: https://wiki.archlinux.org/title/Clipboard
