uniphinx and Sphinx
===================

If you already know Sphinx, this chapter maps familiar ideas onto
uniphinx. It is not a claim of compatibility.

Conceptual map
--------------

- **Sphinx ``toctree``** → uniphinx **manifest** (``.manifest`` file
  listing chapter paths in order)
- **Sphinx ``conf.py`` / ``html_theme``** → ``--theme`` / ``--themePath``
  plus the in-page theme dropdown
- **Sphinx builders (html, latex, …)** → ``--format=html|latex|pdf``
  (``HtmlOutputter`` / ``LatexOutputter``); PDF runs a TeX engine on
  the generated ``book.tex``
- **Sphinx / Pygments highlighting** → client-side
  ``highlight-unicon.js`` for Unicon listings
- **Sphinx search** → ``searchindex.js`` + ``search.html`` (simple
  substring search, not Sphinx's stemmer index)
- **Sphinx domains / autodoc** → not present; use ``unidoc`` for API
  extraction from Unicon sources

Markup
------

uniphinx understands a **subset** of RST: underline headings, bullets,
a few directives, and light inline markup. It does not run docutils.
Sphinx-only roles, domains, and extensions will not work unchanged.

Project layout
--------------

Sphinx::

   docs/
     conf.py
     index.rst
     ...

uniphinx::

   mybook/
     book.manifest
     intro.rst
     ...
     images/
     Makefile   # optional; see doc/uniphinx/

When to use which
-----------------

- Prefer **Sphinx** for large multi-language sites, rich LaTeX themes,
  and the extension ecosystem.
- Prefer **uniphinx** for Unicon-native books and manuals that should
  build with the Unicon toolchain, with first-class Unicon listings and
  no Python doc stack. PDF is available via ``--format=pdf`` when a
  TeX engine is installed.

This user guide is itself a uniphinx project: the tool documents and
drives itself.
