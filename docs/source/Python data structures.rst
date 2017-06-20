Python data structures
=======================

Here are some basics about data types in Python.

Probing type of an object
--------------------------

You can always check/print the type of the object using ``type()``:

.. code-block:: python

   >>> type(1)
   <class 'int'>

In this case, the output says that ``1`` is an object of type ``int``.

Primitive types
----------------

+ ``None`` -- this object represent "nothing". A sort of "null" object in C/Java.
+ bool (``True``, ``False``) -- used to represent boolean logic.
+ int (e.g. ``1``, ``-10``, ``65536``) -- numeric value objects.
+ float (e.g. ``1.0``, ``0.24e5``) -- floating-point numbers.


String type(s)
--------------

At the very minimum, you can write string like:

.. code-block:: python

   >>> "this is a python string"
   'this is a python string'
   >>> "" # empty string
   ''

This is called a ``str`` object. ``str`` is used even when it is to represent a single character.

You can call ``len()`` to determine the length of the string:

.. code-block:: python

   >>> len("blah")
   4 # it says "blah" consists of four characters

**If you are completely new to Python, just skip the rest of the section** because everything is just so confusing.

When digging a bit deeper, there is a place where Python is confusing. In other languages such as C/C++, "string" object can refer to several concepts:

1. a mere representation of a byte array.
2. a sequence of ASCII characters (i.e. 26 alphabets; no greek, Umlauts, accents or strange Chinese characters).
3. a sequence of multi-byte characters (i.e. all the possible characters you can ever imagine).

The way Python handles the above concepts depends on its version:

=============== =========== ============= =================
Python version  Byte array  ASCII string  multibyte string
=============== =========== ============= =================
2.x             str         str           unicode
3.x             byte        str           str
=============== =========== ============= =================

On Python 2.x, you need to write a multibyte string in a special way:

.. code-block:: python

   >>> u"µV"
   u'\xb5V'
   >>> print u"MΩ and µV"
   MΩ and µV

Note that the multibyte character is not displayed properly unless you call it with ``print``.

On the other hand, there will be no distinction between ASCII string and multibyte string for Python 3.x (because every string is in multibyte internally).


Lists and tuples
-----------------

There are two basic array object types in Python: ``list`` and ``tuple``.

A tuple can be defined as follows:

.. code-block:: python

   >>> (1, 2, 3)
   (1, 2, 3)

A list can be defined as follows:

.. code-block:: python

   >>> [1, 2, 3]
   [1, 2, 3]

What is the difference (other than the notation)? You cannot update elements in a tuple, but for a list, you can.

,, code-block:: python

   >>> T = (1, 2, 3)
   >>> T[0] = 0
   Traceback (most recent call last):
     File "<stdin>", line 1, in <module>
   TypeError: 'tuple' object does not support item assignment
   >>> L = [1,2,3]
   >>> L[0] = 0 # no error
   >>> L
   [0, 2, 3]


Still, concatenation of two objects are supported for both list and tuple objects:

.. code-block:: python

   >>> (1, 2, 3) + (4, 5, 6)
   (1, 2, 3, 4, 5, 6)
   >>> ['a', 'b'] + [1, 2]
   ['a', 'b', 1, 2]

Actually a ``str`` object can be seen as an "array of characters", it also supports concatenation:

.. code-block:: python

   >>> "Hello, " + "John!"
   'Hello, John!'

(TODO: slicing)










