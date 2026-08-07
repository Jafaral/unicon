Quick Start
===========

A uniphinx project is a directory of chapter ``.rst`` files plus a
manifest that lists them in reading order.

1. Create a manifest
--------------------

``book.idx`` (name is conventional; any path works):

.. code-block:: unicon

   # comments and blank lines are ignored
   preface.rst
   chapter1.rst
   chapter2.rst

2. Write chapters
-----------------

Underline-style headings, paragraphs, lists, and directives. Example
``chapter1.rst``:

.. code-block:: unicon

   First Chapter
   =============

   Hello from uniphinx. See :ref:`Second Chapter` later.

   Second Section
   --------------

   - alpha
   - beta

   .. note::

      Indented body of a note.

   .. code-block:: unicon

      procedure main()
         write("hi")
      end

**Underline rule:** the underline must be at least as long as the
title. Shorter underlines are not treated as headings.

3. Build HTML
-------------

.. code-block:: unicon

   # shell
   uniphinx --manifest=book.idx \
            --title="My Book" \
            --targetDir=./out \
            --theme=basic \
            --themePath=/path/to/uni/uniphinx/themes

Or from a project ``Makefile`` patterned on ``doc/unisphix/Makefile``.

Open ``out/index.html``. Use the sidebar for chapters, search, and
theme switching.

4. Build PDF (optional)
-----------------------

Install a TeX engine first — see the *TeX / PDF dependencies by
platform* section under :ref:`Installation`. Then:

.. code-block:: unicon

   # shell
   uniphinx --format=pdf --manifest=book.idx \
            --title="My Book" --targetDir=./out

Or ``make pdf``. Output is ``out/book.pdf`` (and ``out/book.tex``).
SVG figures are not embedded; convert them to PDF or PNG for TeX.

Where files go
--------------

- ``*.rst`` — chapter sources
- ``*.idx`` — manifest (chapter order)
- ``images/`` — figures (copied into ``out/images/``)
- ``out/`` — generated HTML and/or ``book.tex`` / ``book.pdf``
- ``themes/`` — built-in skins shared across projects (HTML)
