.. ==================================================
.. FOR YOUR INFORMATION 
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.  ÄÖÜäöüß

.. include:: ../Includes.txt


=================================
Some notes
=================================



Python
------

- use latest Python 2.x


What's installed? Run some checks
---------------------------------

::

    $ python -c "import docutils; print docutils.__version__"
    $ 0.9

::

    $ python -c "import sphinx; print sphinx.__version__"
    $ 1.2pre

::

    $ python -c "import yaml; print yaml.__version__"
    $ 3.10
    
::

    $ python -c "import yaml"
    $ # error?
    
    
::

    $ python 
    $ # help(), interactive help, "modules" ...
    
::

    $ rst2html.py --help
    
    


Python packages
---------------

"setuptools"
~~~~~~~~~~~~

Make sure the setup tools are installed. Command "easy_install" should work.

::

    $ easy_install --help
    
    Global options:
    
      --verbose (-v)  run verbosely (default)
      --quiet (-q)    run quietly (turns verbosity off)
      --dry-run (-n)  don't actually do anything
      --help (-h)     show detailed help message
      --no-user-cfg   ignore pydistutils.cfg in your home directory
    
    Options for 'easy_install' command:
    
      --prefix                       installation prefix
      --zip-ok (-z)                  install package as a zipfile
      --multi-version (-m)           make apps have to require() a version
      --upgrade (-U)                 force upgrade (searches PyPI for latest
                                     versions)
      --install-dir (-d)             install package to DIR
      --script-dir (-s)              install scripts to DIR
      --exclude-scripts (-x)         Don't install scripts
      --always-copy (-a)             Copy all needed packages to install dir
      --index-url (-i)               base URL of Python Package Index
      --find-links (-f)              additional URL(s) to search for packages
      --delete-conflicting (-D)      no longer needed; don't use this
      --ignore-conflicts-at-my-risk  no longer needed; don't use this
      --build-directory (-b)         download/extract/build in DIR; keep the
                                     results
      --optimize (-O)                also compile with optimization: -O1 for
                                     "python -O", -O2 for "python -OO", and -O0 to
                                     disable [default: -O0]
      --record                       filename in which to record list of installed
                                     files
      --always-unzip (-Z)            don't install as a zipfile, no matter what
      --site-dirs (-S)               list of directories where .pth files work
      --editable (-e)                Install specified packages in editable form
      --no-deps (-N)                 don't install dependencies
      --allow-hosts (-H)             pattern(s) that hostnames must match
      --local-snapshots-ok (-l)      allow building eggs from local checkouts
    
    usage: easy_install-script.py [options] requirement_or_url ...
       or: easy_install-script.py --help


Use the "setuptools"
~~~~~~~~~~~~~~~~~~~~

::

    easy_install docutils
    easy_install pyyaml
    easy_install PIL