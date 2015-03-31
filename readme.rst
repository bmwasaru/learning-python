Getting Started
===============

Running Python Interpreter
--------------------------

Python comes with an interactive interpreter. When you type ``python`` in your
shell or command prompt, the python interpreter becomes active with a ``>>>``
prompt and waits for your commands.

.. code-block:: python

    $ python
    Python 2.7.6 (default, Mar 22 2014, 22:59:56) 
    [GCC 4.8.2] on linux2
    Type "help", "copyright", "credits" or "license" for more information.
    >>> 

Now you can type any valid python expression at the prompt. python reads the
typed expression, evaluates it and prints the result.

.. code-block:: python

    >>> 23
    23
    >>> 3 + 2
    5

Running Python Scripts
======================

Open your favourite text editor, type the following text and save file as ``hell.py``.

.. code-block:: python

    print "Hello, world!"

And run this program by calling ``python hello.py``. Make sure you change the directory to the directory where you save the file

.. code-block:: python

    britone@britone ~$ python hello.py
    Hello, world!
    britone@britone ~$

Text after ``#`` character in any line is considered as comment.

.. code-block:: python

    # This is helloworld program
    # run this as:
    #    python hello.py
    print "Hello, world!"

Assignments
-----------

One of the building blocks of programming is associating a name to a value.
This is called assignment. The associated name is usually called a *variable*.

.. code-block:: python

    >>> y = 5
    >>> y * y
    25

In this example ``y`` is a variable and it's value is ``5``.

If you try to use a name that is not associated with any value, python gives an error message.

.. code-block:: python

    >>> num
    Traceback (most recent call last):
      File "<stdin>", line 1, in ?
    NameError: name 'num' is not defined
    >>> num = 6
    >>> num
    6

If you re-assign a different value to an existing variable, the new value
overwrites the old value.

.. code-block:: python

    >>> y = 5
    >>> y
    5
    >>> y = 'swahilibox'
    >>> y
    'swahilibox'

It is possible to do multiple assignments at once.

.. code-block:: python

    >>> a, b = 12, 5
    >>> a
    12
    >>> b
    5
    >>> a + b
    17

Numbers
-------

We did this from the begining.

.. code-block:: python

    >>> 56
    56
    >>> 5 + 6
    11

Python also supports decimal numbers.

.. code-block:: python

    >>> 5.6
    5.6
    >>> 5.6 + 0.2
    5.8

Python supports the following operators on numbers.

* ``+`` addition
* ``-`` subtraction
* ``*`` multiplication
* ``/`` division
* ``**`` exponent
* ``%`` remainder

Let's try them on integers.

.. code-block:: python

    >>> 6 + 4
    10
    >>> 6 - 4
    2
    >>> 6 * 4
    24
    >>> 6 / 4
    1
    >>> 6 ** 4
    1296
    >>> 6 % 4
    2

If you notice, the result ``6 / 4`` is ``1`` not ``1.5``. It is because the ``/`` operator when working on integers, produces only an integer. Lets see what happens when we try it with decimal numbers:

.. code-block:: python

    >>> 6.0 / 4.0
    1.5
    >>> 6.0 / 4
    1.5
    >>> 6 / 4.0
    1.5

The operators can be combined.

.. code-block:: python

    >>> 7 + 2 + 5 - 3
    11
    >>> 2 * 3 + 4
    10

It is important to understand how these compound expressions are evaluated. The
operators have precedence, a kind of priority that determines which operator is
applied first. Among the numerical operators, the precedence of operators is as
follows, from low precedence to high.

* ``+``, ``-``
* ``*``, ``/``, ``%``
* ``**``

When we compute ``2 + 3 * 4``, ``3 * 4`` is computed first as the precedence of
``*`` is higher than ``+`` and then the result is added to 2.

.. code-block:: python

    >>> 2 + 3 * 4
    14

We can use parenthesis to specify the explicit groups.

.. code-block:: python

    >>> (2 + 3) * 4
    20

Strings
-------

Strings are what you use to represent text.

Strings are a sequence of characters, enclosed in single quotes or double quotes.

.. code-block:: python

    >>> x = "swahilibox"
    >>> y = 'python'
    >>> print x, y
    swahilibox python

There is difference between single quotes and double quotes, they can used interchangebly.

Multi-line strings can be written using three single quotes or three double quotes.

.. code-block:: python

    x = """This is a multi-line string
    written in
    three lines."""
    print x

    y = '''multi-line strings can be written
    using three single quote characters as well.
    The string can contain 'single quotes' or "double quotes"
    in side it.'''
    print y