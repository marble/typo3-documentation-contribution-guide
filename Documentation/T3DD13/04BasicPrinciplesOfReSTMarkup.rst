.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.  ÄÖÜäöüß

.. include:: ../Includes.txt

==========================================
Basic principles of ReST markup
==========================================

**ReST markup** - what's that?

- In general you write plain text just as it is.

- Use UTF-8 for special characters.

- Use the line end character you want. For TYPO3 official documents
  we are using LF (linefeed, 0xA).

- A few characters have a special meaning and need to be escaped.
  Escape character ist the backslash (``\``)::

    write the   underscore     _   as   \_
                star           *   as   \*
                vertical bar   |   as   \|
                backslash      \   as   \\
                backtick       `   as   \`

- The ReST markup adds **structure** to your document. It doesn't say
  anything about final appearance in terms of **design**.

- Make lines as long or short as it seems reasonable.
  
- Whitespace is very significant. But usually it doesn't matter
  how much whitespace there is in a given place.

- **Indentation** is an important concept and makes up "blocks" of text.
  If you indent it doesn't matter *how much* you indent. Just indent
  text to the same level.
