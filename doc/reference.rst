Reference
#########

.. highlight:: rst

The Dart domain provides the following directives. Most directives are similar
to JavaScript's.

Directives
==========

Each directive populates the index, and/or the package index.

.. rst:directive:: .. dart:package:: name

   This directive sets the package name for object declarations that follow
   after. The package name is used in the global package index and in cross
   references. This directive does not create an object heading like
   :rst:dir:`py:class` would, for example.

   By default, this directive will create a linkable entity and will cause an
   entry in the global package index, unless the ``noindex`` option is
   specified.  If this option is specified, the directive will only update the
   current package name.

   Package directives support body content.

.. rst:directive:: .. dart:function:: name(signature)

   Describes a Dart function or method.  If you want to describe arguments as
   optional, use square brackets as
   `documented <https://www.sphinx-doc.org/en/master/usage/restructuredtext/domains.html#signatures>`_
   for Python signatures.

   You can use fields to give more details about arguments and their expected
   types, errors which may be thrown by the function, and the value being
   returned::

      .. dart:function:: getJSON(href)

         :param string href: The URI to the location of the resource.
         :throws SomeError: For whatever reason in that case.
         :returns: Something.

   This is rendered as:

   .. dart:function:: getJSON(href)
      :noindex:

      :param string href: The URI to the location of the resource.
      :throws SomeError: For whatever reason in that case.
      :returns: Something.

.. rst:directive:: .. dart:method:: name(signature)

   This directive is an alias for :rst:dir:`dart:function`, however it describes
   a function that is implemented as a method on a class object.

.. rst:directive:: .. dart:class:: name

   Describes a constructor that creates an object.  This is basically like a
   function but will show up with a `class` prefix::

      .. dart:class:: MyAnimal

   This is rendered as:

   .. dart:class:: MyAnimal
      :noindex:

.. rst:directive:: .. dart:data:: name

   Describes a global variable or constant.

.. rst:directive:: .. dart:attribute:: object.name

   Describes the attribute *name* of *object*.

Cross Referencing
=================

The following roles refer to Dart objects and links are generated if a matching
directive is found:

.. rst:role:: dart:pkg

   Reference a package.

.. rst:role:: dart:func

   Reference a Dart function.

.. rst:role:: dart:data

   Reference a global variable or constant.

.. rst:role:: dart:class

   Reference a class.

.. rst:role:: dart:meth

   Reference a method of a class.

.. rst:role:: dart:attr

   Reference a property on an object.
