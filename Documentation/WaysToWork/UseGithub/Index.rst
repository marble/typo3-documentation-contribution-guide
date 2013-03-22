.. ==================================================
.. FOR YOUR INFORMATION 
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.  ÄÖÜäöüß

.. include:: ../../Includes.txt

.. _ways-to-work-use-github:

=================================
Use Github
=================================

How to quickly start a new TYPO3 related manual
===============================================

This note reflects the state of today, 2013-03-19.

In short
--------

    ... just push to your Github account
    and find a new rendering of your manual 
    on docs.typo3.org within five minutes!
    
This document describes the few steps you have to do to achieve that.    


What you do
-----------

+  Create a project with an appropriate name like "My-TYPO3-Manual"
   at Github_.

   *Example:* https://github.com/marble/notes-about-TYPO3-ReST-stuff

+  Download a snapshot of the `Official Manual Example`__
   and use the subfolder ``./Documentation`` as a starter. Edit the files
   in ``./My-TYPO3-Manual/Documentation/`` to meet your intentions. Push
   your manual to Github whenever you think you should do so.

+  Send an email to me (martin.bless@typo3.org) on behalf of the
   *TYPO3 Documentation Team* and let me know:

   - What is the **URL** of the ./Documentation folder in your repository?

     *Example:* https://github.com/marble/notes-about-TYPO3-ReST-stuff/tree/master/DocumentationContributionGuide/Documentation

   - What is the intended **title** of your manual?

     *Example:* ``Documentation Contribution Guide``

   - What **kind** of documentation will your manual mostly be
     (example, guide, reference, tutorial, ...)?

     *Example:* ``Guide``



+  Go to the settings page of your repository at Github and and fill in
   the value for *WebHook URL*. You have to fill in the following URL::

        http://docs.typo3.org/services/handle_github_post_receive_hook.php

   And here's how you do it:

   Step 1
      .. figure:: 001-settings.png
         :class: screenshot-detail

   Step 2
      .. figure:: 002-service-hooks.png
         :class: screenshot-detail

   Step 3
      .. figure:: 003-webhook-url.png
         :class: screenshot-detail

   Step 4
      .. figure:: 004-enter-the-url.png
         :class: screenshot-detail


.. _Github: http://github.com
__ https://git.typo3.org/Documentation/TYPO3/Example/OfficialManual.git/snapshot/master.tar.gz


What we will do
---------------

We, the *TYPO3 Documentation Team*\ , will make some server settings in
order to automatically trigger a
new rendering of your manual whenever you do a push to Github. The result
will be somewhere at ``http://docs.typo3.org/.../drafts/[YOUR_GITHUB_NAME]/ManualName``.
We will let you know. *Example:* `Documentation Contribution Guide (Draft)`__

__ http://docs.typo3.org/typo3cms/drafts/NotesAboutTYPO3ReSTStuff/DocumentationContributionGuide/

You can find the logfiles of the rendering process at
``http://docs.typo3.org/~mbless/github.com/[YOUR_GITHUB_NAME]/ManualName.git.make``.
*Example:* `notes-about-TYPO3-ReST-stuff.git.make.DocumentationContributionGuide`__

__ http://docs.typo3.org/~mbless/github.com/marble/notes-about-TYPO3-ReST-stuff.git.make.DocumentationContributionGuide/


What Github does
----------------

On each push Github transmits a bunch of json data like in the example
below to ``http://docs.typo3.org/services/handle_github_post_receive_hook.php``.
That script contains a list of known repository and does a ``wget -q ... -O /dev/null``
of the appropriate ``My-TYPO3-Manual.git.make/request_rebuild.php`` script.
The server looks for those rendering tasks every five minutes.


Technical background
====================

Good to know
------------

``drafts`` URLs are disallowed by our `robots.txt
<http://docs.typo3.org/robots.txt>`_ file.


Links
-----

- https://help.github.com/articles/post-receive-hooks


Example of the JSON data Github sends as a post request
-------------------------------------------------------

What github for example sends in $_POST['payload']:

.. code-block:: javascript

    {
        "after": "7fd06814461758a6422a26f414c1983a53455f6e",
        "repository": {
            "size": 152,
            "has_wiki": true,
            "watchers": 0,
            "pushed_at": 1363683225,
            "private": false,
            "created_at": 1363678352,
            "url": "https://github.com/marble/notes-about-TYPO3-ReST-stuff",
            "master_branch": "master",
            "open_issues": 0,
            "stargazers": 0,
            "description": "This is my scratchpad where I want to take notes while I'm travelling the land of TYPO3 ReST documentation (ReStructuredText).",
            "owner": {
                "email": "m.bless@gmx.de",
                "name": "marble"
            },
            "has_downloads": true,
            "fork": false,
            "name": "notes-about-TYPO3-ReST-stuff",
            "has_issues": true,
            "language": "Python",
            "forks": 0,
            "id": 8873143
        },
        "commits": [{
                "added": [".gitignore", "DocumentationContributionGuide/.gitignore", "DocumentationContributionGuide/Documentation/FinalPages/Targets.rst", "DocumentationContributionGuide/Documentation/Includes.txt", "DocumentationContributionGuide/Documentation/Index.rst", "DocumentationContributionGuide/Documentation/Settings.yml", "DocumentationContributionGuide/Documentation/Sitemap/Index.rst", "DocumentationContributionGuide/Documentation/_make/Makefile", "DocumentationContributionGuide/Documentation/_make/build/.gitignore", "DocumentationContributionGuide/Documentation/_make/conf.py", "DocumentationContributionGuide/Documentation/_make/make-html.bat", "DocumentationContributionGuide/Documentation/_make/make.bat", "DocumentationContributionGuide/Documentation/directives/Images.rst", "IncomingNotes/.gitignore", "IncomingNotes/Documentation/FinalPages/Targets.rst", "IncomingNotes/Documentation/Includes.txt", "IncomingNotes/Documentation/Index.rst", "IncomingNotes/Documentation/Settings.yml", "IncomingNotes/Documentation/Sitemap/Index.rst", "IncomingNotes/Documentation/_make/Makefile", "IncomingNotes/Documentation/_make/build/.gitignore", "IncomingNotes/Documentation/_make/conf.py", "IncomingNotes/Documentation/_make/make-html.bat", "IncomingNotes/Documentation/_make/make.bat", "README.rst"],
                "url": "https://github.com/marble/notes-about-TYPO3-ReST-stuff/commit/e84adbe48612a63507d015a48c091bd7dd567f38",
                "removed": ["README.md"],
                "author": {
                    "email": "martin.bless@gmail.com",
                    "username": "marble",
                    "name": "Martin Bless"
                },
                "message": "Initial commit.",
                "distinct": true,
                "modified": [],
                "id": "e84adbe48612a63507d015a48c091bd7dd567f38",
                "committer": {
                    "email": "martin.bless@gmail.com",
                    "username": "marble",
                    "name": "Martin Bless"
                },
                "timestamp": "2013-03-19T01:43:53-07:00"
            }, {
                "added": ["IncomingNotes/Documentation/Notes-001/TYPO3-Extension-restdoc.rst"],
                "url": "https://github.com/marble/notes-about-TYPO3-ReST-stuff/commit/7fd06814461758a6422a26f414c1983a53455f6e",
                "removed": [],
                "author": {
                    "email": "martin.bless@gmail.com",
                    "username": "marble",
                    "name": "Martin Bless"
                },
                "message": "Add a note",
                "distinct": true,
                "modified": ["IncomingNotes/Documentation/Index.rst"],
                "id": "7fd06814461758a6422a26f414c1983a53455f6e",
                "committer": {
                    "email": "martin.bless@gmail.com",
                    "username": "marble",
                    "name": "Martin Bless"
                },
                "timestamp": "2013-03-19T01:53:36-07:00"
            }
        ],
        "created": false,
        "compare": "https://github.com/marble/notes-about-TYPO3-ReST-stuff/compare/3fd933c5165d...7fd068144617",
        "before": "3fd933c5165d480a405e7deff877aa88ccac7eef",
        "pusher": {
            "name": "none"
        },
        "head_commit": {
            "added": ["IncomingNotes/Documentation/Notes-001/TYPO3-Extension-restdoc.rst"],
            "url": "https://github.com/marble/notes-about-TYPO3-ReST-stuff/commit/7fd06814461758a6422a26f414c1983a53455f6e",
            "removed": [],
            "author": {
                "email": "martin.bless@gmail.com",
                "username": "marble",
                "name": "Martin Bless"
            },
            "message": "Add a note",
            "distinct": true,
            "modified": ["IncomingNotes/Documentation/Index.rst"],
            "id": "7fd06814461758a6422a26f414c1983a53455f6e",
            "committer": {
                "email": "martin.bless@gmail.com",
                "username": "marble",
                "name": "Martin Bless"
            },
            "timestamp": "2013-03-19T01:53:36-07:00"
        },
        "forced": false,
        "deleted": false,
        "ref": "refs/heads/master"
    }


Communication
=============

Questions & answers of general interest
---------------------------------------

Please send questions and answers of general interest to the 
`TYPO3 documentation mailinglist [TYPO3-doc]`__.

__ http://lists.typo3.org/cgi-bin/mailman/listinfo/typo3-project-documentation


Bugs and issues
---------------

Send bugs and issue reports to the `forge issue tracker at [team-doc-rendering]`__.

__ https://forge.typo3.org/projects/team-doc-rendering


Email
-----

If you think your question is definitely specific and not of public
interest send me an email: martin.bless@typo3.org


What this means?
================

Have fun, start writing!


.. toctree: :
   :maxdepth: 5
   :glob:
   :titlesonly:

   subsubtopic/Index
