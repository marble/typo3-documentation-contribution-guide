.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../Includes.txt


=================
How to use images
=================

Let's try to understand the docutils_ directive_ "image__". This 
directive needs an argument which is the URI_ of the image.

__ http://docutils.sourceforge.net/docs/ref/rst/directives.html#image

docutils: image.svg ist möglich, image.swf ist möglich.

((options))
-----------

Several options a recognized: The `common options`_ :class: and :name:
and specific options.

\:name:
   can be just one name. Becomes the id in HTML

\:class:
   needs at least one class but can have more.

\:alt:
   Use this option to specifiy the "Alternate text: a short description
   of the image, displayed by applications that cannot display images, or 
   spoken by applications for visually impaired users."
   
   if alt is missing uri is used for alt.

\:align:
   left, center, right seem to work. top, middle, bottom don't.

((specifying the size))   
-----------------------

width
~~~~~
With :width: you can specifiy the `length <http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#length-units>`_.
`Length units`_ are similar to CSS. But there may be whitespace between number and unit.

http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#percentage-units

If you only specify the width then the image is scaled proportionally.

scale
~~~~~
scale takes an integer percentage. The % is optional. If width is also
given they are combined.


Specify the width without unit!?



((linking the image))
---------------------

If :target: is given, the image will be linked and point to the target.
Target can be a URI_ or a `ReST reference name`_ followed by an 
underscore.

The image will not be linked if none of these four options is present:
:target:, :height:, :width: and :scale:.

If :target: is missing but at least one of :height:, :width:, :scale: is
given then the image will have an auto link that opens the image in
a new browser window.

Sphinx specific
---------------

Sphinx allows picture.\* notation ...

transforms :align: into <div align="left|center|right" class="align-left|align-center|align-right">

knows about \*.svg and \*.svgz

Achtung: PIL verträgt keine Unicode pathnames

Wenn 'scale' da ist und PIL verfügbar und keine unicode path und (width fehlt oder height fehlt):
dann: trage die Werte die PIL gefunden hat, dort ein wo sie fehlen. Sphinx macht das genaus wie docutils
es tun würden. Für die ist die Datei aber vielleicht noch nicht vorhanden.


how align works
~~~~~~~~~~~~~~~

container drumherum mit den css klassen left, center, right.

TYPO3 specific
--------------

We know the classes:

screenshot-detail
~~~~~~~~~~~~~~~~~

no scaling, margin, border, shadow. No link, if none of ((these four))
is given. Image bekommt block style.

screenshot-fullsize
~~~~~~~~~~~~~~~~~~~

autolink to image, if no other link is specified through the :target:
option. Size 95%, but not larger than the original image (no upscaling).
Thus automatic downscaling like the browser window width.

Scales with the browser window.

block style.


.. _common options: http://docutils.sourceforge.net/docs/ref/rst/directives.html#common-options
.. _docutils: http://docutils.sourceforge.net/
.. _directive: http://docutils.sourceforge.net/docs/ref/rst/directives.html
.. _ReST reference name: http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#reference-names
.. _URI: http://en.wikipedia.org/wiki/Uniform_resource_identifier
.. _length units: http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#length-units

:ref:`Sitemap <sitemap>`