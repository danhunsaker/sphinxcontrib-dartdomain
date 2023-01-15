Convoluted Test
###############

API
===

.. dart:package:: path

   .. dart:data:: context

      The system path :dart:class:`Context`.

   .. dart:data:: current

      The path to the current working directory.

   .. dart:data:: posix

      A default :dart:class:`Context` for manipulating POSIX paths.

   .. dart:data:: separator

      Gets the path separator for the current platform. This is ``\`` on
      Windows and ``/`` on other platforms (including the browser).

   .. dart:data:: style

      The :dart:class:`Style` of the current :dart:class:`Context`.

   .. dart:data:: url

      A default :dart:class:`Context` for manipulating URLs.

   .. dart:data:: windows

      A default :dart:class:`Context` for manipulating Windows paths.


   .. dart:function:: absolute(String part1, [String? part2, String? part3, String? part4, String? part5, String? part6, String? part7, String? part8, String? part9, String? part10, String? part11, String? part12, String? part13, String? part14, String? part15])

      :returns: String

      Returns a new path with the given path parts appended to
      :dart:data:`current`.

   .. dart:function:: basename(String path)

      :returns: String

      Gets the part of ``path`` after the last separator.

   .. dart:function:: basenameWithoutExtension(String path)

      :returns: String

      Gets the part of ``path`` after the last separator, and without any
      trailing file extension.

   .. dart:function:: canonicalize(String path)

      :returns: String

      Canonicalizes ``path``.

   .. dart:function:: dirname(String path)

      :returns: String

      Gets the part of ``path`` before the last separator.

   .. dart:function:: equals(String path1, String path2)

      :returns: bool

      Returns ``true`` if ``path1`` points to the same location as ``path2``,
      and ``false`` otherwise.

   .. dart:function:: extension(String path, [int level = 1])

      :returns: String

      Gets the file extension of ``path``: the portion of basename from the last
      ``.`` to the end (including the ``.`` itself).

   .. dart:function:: fromUri(dynamic uri)

      :returns: String

      Returns the path represented by ``uri``, which may be a String or a Uri.

   .. dart:function:: hash(String path)

      :returns: int

      Returns a hash code for ``path`` such that, if :dart:func:`equals` returns
      true for two paths, their hash codes are the same.

   .. dart:function:: isAbsolute(String path)

      :returns: bool

      Returns ``true`` if ``path`` is an absolute path and ``false`` if it is a
      relative path.

   .. dart:function:: isRelative(String path)

      :returns: bool

      Returns ``true`` if ``path`` is a relative path and ``false`` if it is
      absolute. On POSIX systems, absolute paths start with a ``/`` (forward
      slash). On Windows, an absolute path starts with ``\\``, or a drive letter
      followed by ``:/`` or ``:\``.

   .. dart:function:: isRootRelative(String path)

      :returns: bool

      Returns ``true`` if ``path`` is a root-relative path and ``false`` if it's
      not.

   .. dart:function:: isWithin(String parent, String child)

      :returns: bool

      Returns ``true`` if ``child`` is a path beneath ``parent``, and ``false``
      otherwise.

   .. dart:function:: join(String part1, [String? part2, String? part3, String? part4, String? part5, String? part6, String? part7, String? part8, String? part9, String? part10, String? part11, String? part12, String? part13, String? part14, String? part15, String? part16])

      :returns: String

      Joins the given path parts into a single path using the current platform's
      separator.

   .. dart:function:: joinAll(Iterable<String> parts)

      :returns: String

      Joins the given path parts into a single path using the current platform's
      separator.

   .. dart:function:: normalize(String path)

      :returns: String

      Normalizes ``path``, simplifying it by handling ``..``, and ``.,`` and
      removing redundant path separators whenever possible.

   .. dart:function:: prettyUri(dynamic uri)

      :returns: String

      Returns a terse, human-readable representation of ``uri``.

   .. dart:function:: relative(String path, {String? from})

      :returns: String

      Attempts to convert ``path`` to an equivalent relative path from the
      current directory.

   .. dart:function:: rootPrefix(String path)

      :returns: String

      Returns the root of ``path``, if it's absolute, or the empty string if
      it's relative.

   .. dart:function:: setExtension(String path, String extension)

      :returns: String

      Returns ``path`` with the trailing extension set to ``extension``.

   .. dart:function:: split(String path)

      :returns: List<String>

      Splits ``path`` into its components using the current platform's
      separator.

   .. dart:function:: toUri(String path)

      :returns: Uri

      Returns the URI that represents ``path``.

   .. dart:function:: withoutExtension(String path)

      :returns: String

      Removes a trailing extension from the last part of ``path``.


   .. dart:class:: Context

      An instantiable class for manipulating paths. Unlike the top-level
      functions, this lets you explicitly select what platform the paths will
      use.

      .. dart:function:: ({Style? style, String? current})

         :param Style? style: The :dart:class:`Style` of paths.
         :param String? current: The path all relative paths are relative to.

         Creates a new path context for the given ``style`` and ``current``
         directory.

      .. dart:attribute:: current

         The current directory that relative paths are relative to.

      .. dart:attribute:: separator

         Gets the path separator for the context's style. On Mac and Linux, this
         is ``/``. On Windows, it's ``\``.

      .. dart:attribute:: style

         The style of path that this context works with.

      .. dart:method:: absolute(String part1, [String? part2, String? part3, String? part4, String? part5, String? part6, String? part7, String? part8, String? part9, String? part10, String? part11, String? part12, String? part13, String? part14, String? part15])

         :returns: String

         Returns a new path with the given path parts appended to
         :dart:attr:`current`.

      .. dart:method:: basename(String path)

         :returns: String

         Gets the part of ``path`` after the last separator on the context's
         platform.

      .. dart:method:: basenameWithoutExtension(String path)

         :returns: String

         Gets the part of ``path`` after the last separator on the context's
         platform, and without any trailing file extension.

      .. dart:method:: canonicalize(String path)

         :returns: String

         Canonicalizes ``path``.

      .. dart:method:: dirname(String path)

         :returns: String

         Gets the part of ``path`` before the last separator.

      .. dart:method:: equals(String path1, String path2)

         :returns: bool

         Returns ``true`` if ``path1`` points to the same location as ``path2``,
         and ``false`` otherwise.

      .. dart:method:: extension(String path, [int level = 1])

         :returns: String

         Gets the file extension of ``path``: the portion of ``basename`` from
         the last ``.`` to the end (including the ``.`` itself).

      .. dart:method:: fromUri(dynamic uri)

         :returns: String

         Returns the path represented by ``uri``, which may be a String or a Uri.

      .. dart:method:: isAbsolute(String path)

         :returns: bool

         Returns ``true`` if ``path`` is an absolute path and ``false`` if it is
         a relative path.

      .. dart:method:: isRelative(String path)

         :returns: bool

         Returns ``true`` if ``path`` is a relative path and ``false`` if it is
         absolute. On POSIX systems, absolute paths start with a ``/`` (forward
         slash). On Windows, an absolute path starts with ``\\``, or a drive
         letter followed by ``:/`` or ``:\``.

      .. dart:method:: isRootRelative(String path)

         :returns: bool

         Returns ``true`` if ``path`` is a root-relative path and ``false`` if
         it's not.

      .. dart:method:: isWithin(String parent, String child)

         :returns: bool

         Returns ``true`` if ``child`` is a path beneath ``parent``, and
         ``false`` otherwise.

      .. dart:method:: join(String part1, [String? part2, String? part3, String? part4, String? part5, String? part6, String? part7, String? part8, String? part9, String? part10, String? part11, String? part12, String? part13, String? part14, String? part15, String? part16])

         :returns: String

         Joins the given path parts into a single path.

      .. dart:method:: joinAll(Iterable<String> parts)

         :returns: String

         Joins the given path parts into a single path.

      .. dart:method:: normalize(String path)

         :returns: String

         Normalizes ``path``, simplifying it by handling ``..``, and ``.``, and
         removing redundant path separators whenever possible.

      .. dart:method:: prettyUri(dynamic uri)

         :returns: String

         Returns a terse, human-readable representation of ``uri``.

      .. dart:method:: relative(String path, {String? from})

         :returns: String

         Attempts to convert ``path`` to an equivalent relative path relative to
         :dart:attr:`current` (or ``from``, if given).

      .. dart:method:: rootPrefix(String path)

         :returns: String

         Returns the root of ``path`` if it's absolute, or an empty string if
         it's relative.

      .. dart:method:: setExtension(String path, String extension)

         :returns: String

         Returns ``path`` with the trailing extension set to ``extension``.

      .. dart:method:: split(String path)

         :returns: List<String>

         Splits ``path`` into its components using the current platform's
         separator.

      .. dart:method:: toUri(String path)

         :returns: Uri

         Returns the URI that represents ``path``.

      .. dart:method:: withoutExtension(String path)

         :returns: String

         Removes a trailing extension from the last part of ``path``.

   .. dart:class:: PathException

      An exception class that's thrown when a path operation is unable to be
      computed accurately.

   .. dart:class:: PathMap<V>

      A map whose keys are paths, compared using ``p.equals`` and ``p.hash``.

      .. dart:method:: ({Context? context})

         Creates an empty :dart:class:`PathMap` whose keys are compared using
         ``context.equals`` and ``context.hash``.

      .. dart:method:: of(Map<String, V> other, {Context? context})

         Creates a :dart:class:`PathMap` with the same keys and values as
         ``other``, whose keys are compared using ``context.equals`` and
         ``context.hash``. 

   .. dart:class:: PathSet

      A set containing paths, compared using ``p.equals`` and ``p.hash``.

      .. dart:method:: ({Context? context})

         Creates an empty :dart:class:`PathSet` whose contents are compared
         using ``context.equals`` and ``context.hash``. 

      .. dart:method:: of(Iterable<String> other, {Context? context})

         Creates a :dart:class:`PathSet` with the same contents as ``other``
         whose elements are compared using ``context.equals`` and
         ``context.hash``. 

   .. dart:class:: Style

      An enum type describing a "flavor" of path.

      .. dart:attribute:: context

         A :dart:class:`Context` using this :dart:class:`Style`.

      .. dart:attribute:: name

         The name of this path style. Will be ``posix`` or ``windows``.

      .. dart:attribute:: platform

         The style of the host platform.

      .. dart:attribute:: posix

         POSIX-style paths use ``/`` (forward slash) as separators. Absolute
         paths start with ``/``. Used by UNIX, Linux, Mac OS X, and others.

      .. dart:attribute:: url

         URLs aren't filesystem paths, but they're supported to make it easier
         to manipulate URL paths in the browser.

      .. dart:attribute:: windows

         Windows paths use ``\`` (backslash) as separators. Absolute paths start
         with a drive letter followed by a colon (example, ``C:``) or two
         backslashes (``\\``) for UNC paths.

Usage
=====

The path library was designed to be imported with a prefix, though you don't
have to if you don't want to:

.. code-block:: dart

   import 'package:path/path.dart' as p;

The most common way to use the library is through the top-level functions. These
manipulate path strings based on your current working directory and the path
style (POSIX, Windows, or URLs) of the host platform. For example:

.. code-block:: dart

   p.join('directory', 'file.txt');

This calls the top-level :dart:func:`join` function to join ``"directory"`` and
``"file.txt"`` using the current platform's directory separator.

If you want to work with paths for a specific platform regardless of the
underlying platform that the program is running on, you can create a
:dart:class:`Context` and give it an explicit :dart:class:`Style`:

.. code-block:: dart

   var context = p.Context(style: p.Style.windows);
   context.join('directory', 'file.txt');

This will join ``"directory"`` and ``"file.txt"`` using the Windows path
separator, even when the program is run on a POSIX machine.

The above code is equivalent to the following two approaches:

.. code-block:: dart

   p.windows.join('directory', 'file.txt');

.. code-block:: dart

   p.Style.windows.context.join('directory', 'file.txt');

Feel free to use whichever makes most sense to you.
