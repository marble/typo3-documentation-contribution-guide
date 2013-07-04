.. ==================================================
.. FOR YOUR INFORMATION 
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.  ÄÖÜäöüß

.. include:: ../Includes.txt


==========================================
The "ReST Documentation Day" at the T3DD13
==========================================

Welcome!

What are we going to do?
========================

2013-07-06

The plan is to

- start with a short introduction
- get into contact
- try to give everybody a lift so that he can really start
- repeat that every hour
- spend the remaining part of the hour with "Getting started"

I want to learn from the audience to make this a better "TYPO3 
Documentation Contribution Guide".

If you have more time you're welcome to stay here and help with some of
our manuals.


What is ReST?
=============

- ReST stands for "ReStructuredText". It is the name of a text **markup
  syntax**.
  It has nothing to do with restful services known as "REST".

- It has been developed around the year 2000 by David Goodger and it is
  stable.

- It is "an easy-to-read, what-you-see-is-what-you-get 
  plaintext markup syntax and parser system."
  `(Davig Goodger) <http://docutils.sourceforge.net/docs/ref/rst/introduction.html>`__
  
- It is widespread and used all over the world. So we are part of a big
  and growing community of ReST users.


How does it work?
=================

- You write documentation much like you're used to writing other code.
- You can use the same tools you use for coding like PhpStorm.
- You're writing plain text much like you used a typewriter in former
  times.
- Use UTF-8 to encode Non-Ascii characters. There is no other "special
  encoding" for characters.
- If you can and if you know what it is it's a good idea to use 
  UTF-8 **with** byte order mark (BOM) as it gives the Editor a definitive
  hint about the used encoding.
- You can use any line end character like LF, CR, CRLF.
- You stick to the rules of the ReST markup.


Basic principles of ReST markup
===============================

Now - what's this?

- In general you write plain text just as it is.

- Use UTF-8 for special characters.

- Use the line end character you want. For TYPO3 official documents
  we are using LF (linefeed, 0xA).

- A few characters have a special meaning and need to be escaped::

      write the   underscore    _  as  \_       
                  star          *  as  \*       
                  vertical bar  |  as  \|       
                  backslash     \  as  \\       
                  backtick      `  as  \`       

- The ReST markup adds **structure** to your document. It doesn't say
  anything about final appearance in terms of **design**.
  
- Whitespace is significant in the sense that it's often important
  whether there is whitespace or not. On the other hand in general
  multiple spaces are treated as one space and multiple lines are treated
  as one line.

- **Indentation** is an important concept and used to make up "blocks".


..        Let's look at an example of ReST markup
          =======================================
          
          Source::
          
            Example
            -------
            
            Let's have an example.
            Adjoining lines are combined to one paragraph.
            We can use special symbols ((...)) but need to
            escape the characters '\*', '\_', '\|', '\`' and '\\'.
            
            To start a new paragraph we need at least one empty 
            preceeding line.
            
                 This text is indented and which makes it a quote.
          
          
          Result:
          
          Example
          =======
          
          Let's have an example.
          Adjoining lines are combined to one paragraph.
          We can use special symbols ((...)) but need to
          escape the characters '\*', '\_', '\|', '\`' and '\\'.
          
          To start a new paragraph we need at least one empty 
          preceeding line.
          
              This text is indented and which makes it a quote.

              
Let's see some live examples
============================

A cool online tool: **RSTED**
             
- rsted: http://rst.ninjs.org/

An experimental version of **RSTED** at http://docs.typo3.org:

- http://docs.typo3.org:5000/

..         How to restart the service:
           mbless@srv123: cd ~/rst-ninjs-org/rsted
           mbless@srv123: cat README.rst
           mbless@srv123: python application.py
           start http://docs.typo3.org:5000/


One word about tabs
===================

With ReST tabs are evil! Don't use them!

  

The general procedure of the documentation process
==================================================

1. Start writing your documentation as normal text.
2. Feed your source files into some ReST processing tools
3. Have that tools produce the desired output like Html, Pdf, Json, ePub
   and so on.
   
.. Advantages: gets parsed and compiled, can be transformed,
   extendable
   
   
Some names and basics you should know
=====================================

- "DOCUTILS" is the name of the basic Python documentation package. 
  It contains the one and only ReST parser.
  Handles one file at a time.
  
- "Sphinx" is ...
  Handles a "documentation project" with a lot of ReST files.


  
How can I get started within five minutes?
==========================================

This is how:

1. Create a project at Github
2. Enter the data of your project here:
   https://notes.typo3.org/p/t3dd13-documentation-projects/
3. Add hook processing to your Github repository
4. Test your hook or do a push to Github
5. Find your documentation at http://docs.typo3.org/typo3cms/drafts/,
   http://docs.typo3.org/neos/drafts/ or http://docs.typo3.org/flow/drafts/.


Places of information
=====================

Learn from our existing documentation:
    http://docs.typo3.org

Wiki
    http://wiki.typo3.org/Rest

    
    

..  

    What infrastructure do we have?
    ===============================

    What resources do we have?
    ==========================
   
    TYPO3 documentation repositories

    * http://git.typo3.org 
    * Helper script  by Philipp Gampe to clone all documentation from git.typo3.org: https://github.com/pgampe/TYPO3-Documentation_clone
    * TYPO3-spezifische ReST Tools sind in: http://git.typo3.org/Documentation/RestTools.git 
    * 

   



    Online helpers: "Get The Docs" by Fabien Udriot

        * http://lists.typo3.org/pipermail/typo3-project-documentation/2012-December/004257.html
        * A service:

    http://docs.typo3.org/getthedocs/ 


        * From manual.sxw to ReST:
        * http://docs.typo3.org/getthedocs/service-convert.html 


        * From ReST to HTML:
    http://docs.typo3.org/getthedocs/service-render.html


        * https://git.typo3.org/Documentation/GetTheDocs.git 



    Online Resources

        * TYPO3 documentation Mailinglist:
    http://lists.typo3.org/cgi-bin/mailman/listinfo/typo3-project-documentation


        * One place where I work in the open:
    http://docs.typo3.org/~mbless/


        * http://docs.typo3.org/~mbless/2013-03-14-ReST-Workshop-Stuttgart/


        * About: Sphinx
    A project http://www.pocoo.org/projects/sphinx/#sphinx 
    by Georg Brandl http://www.pocoo.org/team/#georg-brandl
    at http://www.pocoo.org/


        * 
            * 




    About: Docutils
    David Goodger developed the reStructuredText format, created the Docutils, is the "Benevolent Dictator for Now (BDFN"
    http://docutils.sourceforge.net/
    http://docutils.sourceforge.net/rst.html
    http://docutils.sourceforge.net/README.html#quick-start
    http://docutils.sourceforge.net/docs/index.html

    http://docs.typo3.org/~mbless/DOCROOT_HTDOCS/World/Docutils/html/
    http://srv123.typo3.org/~mbless/DOCROOT_HTDOCS/World/Docutils/html/docutils-docs/user/rst/quickstart.html 
     


        * About: Python
    Guido van Rossum invented and created Python, is accepted by the Python community as the "Benevolent Dictator for Life (BDFL)"


        * About: PyPi and the "setuptools"


        * Motivation song: http://www.youtube.com/watch?v=oXo6G5mfmro 


        * 


    Local Installation

        * ...

    Server Installation

        * ...


    Verfahren: Understanding local rendering

        * Convert a local manual.sxw to ReST
        * For example http://docs.typo3.org/~mbless/2013-03-14-ReST-Workshop-Stuttgart/manual.sxw
        * Use GetTheDocs: http://docs.typo3.org/getthedocs/service-convert.html
        * Add makefiles: http://docs.typo3.org/~mbless/2013-03-14-ReST-Workshop-Stuttgart/_make.zip 
        * Render locally!
        * Inspect _not_versioned
        * See the result



    Verfahren: Related Topics ...

        * related: http://wiki.typo3.org/Contribution_Walkthrough_Tutorials 



    Missing

        * Documentation Contribution Manual (covering ReST)


    Writing ReST: Elemente der Syntax

        * Überschriften, Absätze, Listen, Tabellen, Bilder, ...: Wie macht man das?



    Notizen:

    :ref:`t3api:xliff`
    shift+ctrl v : evernote, einfügen ohne Formatierung
    http://de.slideshare.net/marco-huber/phpstorm-6-configuration-for-typo3


Tricky
======

Where Sphinx differs from Docutils

See ``other.py``::

    # register the standard rst class directive under a different name
    # only for backwards compatibility now
    directives.register_directive('cssclass', Class)
    # new standard name when default-domain with "class" is in effect
    directives.register_directive('rst-class', Class)




.. toctree::
   :maxdepth: 5
   :glob:
   :titlesonly:

   *

   
:ref:`Sitemap <sitemap>`