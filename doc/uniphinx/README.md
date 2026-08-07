# uniphinx documentation under doc/

This directory holds the **uniphinx User Guide**, built with uniphinx
(Unicon’s Sphinx-like book generator in `uni/uniphinx/`).

```sh
# from the unicon tree
make -C uni/uniphinx          # build the uniphinx tool
make -C doc/uniphinx          # build this guide → out/index.html
```

Themes: `make basic`, `make classic`, or `make dark` in this directory.
Also `make latex` / `make pdf` when a TeX engine is installed.

This folder is the tool’s own manual in the top-level `doc/` tree
alongside `book/`, `ib/`, and `utr/`.
