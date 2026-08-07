Introduction
============

.. image:: images/uniphinx-logo.png

   UniPhinx — documentation for Unicon

*uniphinx* is a prose/book documentation generator for Unicon. It reads
a small RST-like markup, builds a doctree, resolves cross-chapter
references, and writes HTML — in the same general niche as
`Sphinx <https://www.sphinx-doc.org/>`_, but implemented in Unicon and
aimed at Unicon documentation and books.

This manual is the user guide for uniphinx itself. Sources live under
``doc/uniphinx/`` in the unicon tree and are built *with* uniphinx.

What uniphinx is for
--------------------

- Multi-chapter books and manuals (ordered by a manifest file)
- HTML output with sidebar navigation, search, and selectable themes
- Unicon code samples with syntax highlighting
- Images and simple admonitions

It is **not** a full Sphinx or docutils replacement. The markup subset
is intentionally small; extend the parser as real documents need more.

A taste of Unicon highlighting
------------------------------

Mark listings with ``.. code-block:: unicon`` (also ``icon`` or
``icn``). In HTML they are highlighted client-side:

.. code-block:: unicon

   procedure greet(who)
      write("Hello, ", \who | "world", "!")
   end

   procedure main()
      greet("uniphinx")
      greet()
   end

See :ref:`Markup Reference` for the full dialect and
:ref:`Quick Start` to generate a tiny book.

Relation to unidoc
------------------

`uni/unidoc/` extracts API docs from Unicon source comments.
*uniphinx* is a separate tool for authored prose. They can coexist; a
future ``.. api::`` bridge may connect them.

How to read this guide
----------------------

- :ref:`Installation` — build and install the ``uniphinx`` binary
- :ref:`Quick Start` — generate HTML from a tiny book
- :ref:`Markup Reference` — headings, lists, inline markup, directives
- :ref:`Themes` — basic, classic, dark, and the in-page switcher
- :ref:`Command Line` — CLI options
- :ref:`uniphinx and Sphinx` — what maps to what if you know Sphinx
