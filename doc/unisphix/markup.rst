Markup Reference
================

uniphinx accepts a **restricted RST-like** dialect. Unknown constructs
are either ignored, treated as plain text, or left as raw directives.

Headings
--------

.. code-block:: unicon

   Chapter Title
   =============

   Section
   -------

   Subsection
   ~~~~~~~~~~

Characters ``= - ~ ^`` are recognized as underline styles. Heading
level follows the underline character. The underline length must be
greater than or equal to the title length.

Paragraphs and lists
--------------------

Blank lines separate paragraphs. Bullet lists use ``-`` or ``*`` with
a following space. Indented continuation lines belong to the current
item.

Inline markup
-------------

- single asterisks for emphasis
- double asterisks for strong
- backticks for inline literals
- a ref role pointing at a section title (same text as the heading)
- a doc role is parsed; full resolution is still limited

For cross-chapter links, write a ref role whose label matches the
target heading exactly (see the links in :ref:`Introduction`).

Directives
----------

Recognized forms:

.. code-block:: unicon

   .. note::

      Body lines, indented.

   .. warning::

      Careful.

   .. tip::

      Hint.

   .. code-block:: unicon

      # source lines, indented
      procedure main()
         write("ok")
      end

   .. image:: images/diagram.svg

      Optional alt text on an indented line

``code-block`` languages ``unicon``, ``icon``, and ``icn`` get Unicon
syntax highlighting in HTML. Other languages are emitted as plain
``<pre><code class="language-…">`` without highlighting.

A line ending in ``::`` (RST literal-block introducer) followed by an
indented block is also treated as a code listing. ``Sphinx::`` becomes
the label ``Sphinx:`` plus the indented tree; a lone ``::`` introduces
a block with no label.

Unknown ``.. name::`` directives become HTML comments so content is
not silently dropped.

Cross-references
----------------

Pass 1 collects every section title (slugified) across all chapters.
Pass 2 turns pending ref roles into links of the form
``chapter.html#anchor``. Prefer unique section titles.

See also :ref:`Quick Start` and :ref:`Command Line`.
