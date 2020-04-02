.. _tex-html:

####
html
####

The `html` extension gives you access to some HTML features like
styles, classes, element ID's, and clickable links.  It defines the
following non-standard macros:

.. describe:: \\href{url}{math}

    Makes ``math`` be a link to the page given by ``url``.

.. describe:: \\class{name}{math}

    Attaches the CSS class ``name`` to the output associated with
    ``math`` when it is included in the HTML page.  This allows your
    CSS to style the element.

.. describe:: \\cssId{id}{math}

    Attaches an id attribute with value ``id`` to the output
    associated with ``math`` when it is included in the HTML page.
    This allows your CSS to style the element, or your javascript to
    locate it on the page.

.. describe:: \\style{css}{math}

    Adds the give ``css`` declarations to the element associated with
    ``math``.

For example:

.. code-block:: latex

    x \href{why-equal.html}{=} y^2 + 1

    (x+1)^2 = \class{hidden}{(x+1)(x+1)}

    (x+1)^2 = \cssId{step1}{\style{visibility:hidden}{(x+1)(x+1)}}

This extension is loaded automatically when the `autoload` extension
is used.  To load the `html` extension explicitly, add
``'[tex]/html'`` to the ``load`` array of the ``loader`` block of
your MathJax configuration, and add ``'html'`` to the ``packages``
array of the ``tex`` block.

.. code-block:: javascript

   window.MathJax = {
     loader: {load: ['[tex]/html']},
     tex: {packages: {'[+]': ['html']}}
   };

Alternatively, use ``\require{html}`` in a TeX expression to load it
dynamically from within the math on the page, if the `require`
extension is loaded.

|-----|
