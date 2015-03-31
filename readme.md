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