.. ==================================================
.. FOR YOUR INFORMATION 
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.  Check: ÄÖÜäöüß

.. include:: ../Includes.txt

=========================
Questions & Answers
=========================

Questions & Answers
===================





.. _qa-2013-04-14-what-aboutReST-for-extensions:

Q: What about ReST for Extensions?
----------------------------------

**2013-04-14**

"Hey, that new `TYPO3 Documentation Starter 
<http://docs.typo3.org/typo3cms/drafts/github/marble/DocumentationStarter/Quickstart/Index.html>`_
is tempting me. Should the documentation of all of my extensions move to
ReST *right now*?"

Answer:
~~~~~~~

I depends!

Pro
   ReST ist the future. Add a :file:`YOUR_EXT/Documentation/Index.rst`
   file and you're on the right track.
   
Contra
   At the moment any documentation in that folder 
   :file:`./Documentation` of extensions is NOWHERE rendered automatically.
   This means that it will neither appear on 
   http://typo3.org nor on http://docs.typo3.org. This is a pity but we
   can't help it at the moment because of lack of manpower.
   The day will come when this changes. I suspect it will happen in the
   middle of this year 2013. Of course it doesn't hurt if you already
   put your ReST documentation there.

   I would go like this: **If** I had a nice documentation for my extension
   in an OpenOffice file (:file:`manual.sxw`) I would keep it that way
   at the moment.
   **If** I'd be planning to start a new documentation or to do a major
   rework or if I'd be feeling that I simply don't
   want to continue with OpenOffice stuff I wouldn't hesitate to
   switch to ReST.
   
   A clever solution for the time being could be: Use Github in the
   way it's described `here <http://docs.typo3.org/typo3cms/drafts/github/marble/DocumentationStarter/Quickstart/Index.html>`_.
   Additionally keep a minimal OpenOffice manual (:file:`manual.sxw`) 
   and direct people from there to the place where the manual is 
   currently being rendered.
   
.. tip::

   If your extension already has an OpenOffice documentation see if
   you can find it on the `extension's page 
   <http://docs.typo3.org/typo3cms/extensions/>`_.

   Take `simulatefe <http://docs.typo3.org/typo3cms/extensions/simulatefe/1.0.1/>`_
   as an example. Note the link to the 
   `manual.rst
   <http://docs.typo3.org/typo3cms/extensions/simulatefe/1.0.1/manual.rst>`_
   file. This means that a first translation from OpenOffice to ReST
   is already available and at your hands.
   
Once the documentation build chain on the docs server is ready you can
easily move your documentation into the :file:`./Documentation` folder.
   
   

.. _qa-2013-03-25-highlighting-for-typoscript:

Q: No highlighting for TypoScript?
----------------------------------

**2013-03-25**

"I have TypoScript in a codeblock and I'm indicating it with 
``.. code-block:: ts``. But it doesn't work. Why?" 

Answer:
~~~~~~~

Sorry, unfortunately Pygments, which is the syntax highlighter
that's being used by Sphinx, doesn't know TypoScript yet.
We need a volunteer to add the necessary `lexer and rules <http://pygments.org/languages/>`_.



.. Next pages:

.. toctree: :
   :maxdepth: 5
   :glob:
   :titlesonly:

   *
   SubChapter/Index

:ref:`Sitemap <sitemap>`