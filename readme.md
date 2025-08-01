Getting Started
===============

Running Python Interpreter
--------------------------

Python comes with an interactive interpreter. When you type ``python`` in your
shell or command prompt, the python interpreter becomes active with a ``>>>``
prompt and waits for your commands.

    $ python
    Python 3.4.0 (default, Apr 11 2014, 13:05:11)  
    [GCC 4.8.2] on linux2
    Type "help", "copyright", "credits" or "license" for more information.
    >>> 

Now you can type any valid python expression at the prompt. python reads the
typed expression, evaluates it and prints the result.

    >>> 23
    23
    >>> 3 + 2
    5

Running Python Scripts
======================

Open your favourite text editor, type the following text and save file as ``hello.py``.

    print("Hello, world!")

And run this program by calling ``python hello.py``. Make sure you change the directory to the directory where you save the file

    britone@britone ~$ python hello.py
    Hello, world!
    britone@britone ~$

Text after ``#`` character in any line is considered as comment.

    # This is helloworld program
    # run this as:
    #    python hello.py
    print("Hello, world!")

Assignments
-----------

One of the building blocks of programming is associating a name to a value.
This is called assignment. The associated name is usually called a *variable*.

    >>> y = 5
    >>> y * y
    25

In this example ``y`` is a variable and it's value is ``5``.

If you try to use a name that is not associated with any value, python gives an error message.

    >>> num
    Traceback (most recent call last):
      File "<stdin>", line 1, in ?
    NameError: name 'num' is not defined
    >>> num = 6
    >>> num
    6

If you re-assign a different value to an existing variable, the new value
overwrites the old value.

    >>> y = 5
    >>> y
    5
    >>> y = 'pwaniteknowgalz'
    >>> y
    'pwaniteknowgalz'

It is possible to do multiple assignments at once.

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

    >>> 56
    56
    >>> 5 + 6
    11

Python also supports decimal numbers.

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

    >>> 6.0 / 4.0
    1.5
    >>> 6.0 / 4
    1.5
    >>> 6 / 4.0
    1.5

The operators can be combined.

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

    >>> 2 + 3 * 4
    14

We can use parenthesis to specify the explicit groups.

    >>> (2 + 3) * 4
    20

Strings
-------

Strings are what you use to represent text.

Strings are a sequence of characters, enclosed in single quotes or double quotes.

    >>> x = " pwaniteknowgalz"
    >>> y = 'python'
    >>> print(x, y)
     pwaniteknowgalz python

There is difference between single quotes and double quotes, they can used interchangebly.

Multi-line strings can be written using three single quotes or three double quotes.

    x = """This is a multi-line string
    written in
    three lines."""
    print(x)

    y = '''multi-line strings can be written
    using three single quote characters as well.
    The string can contain 'single quotes' or "double quotes"
    in side it.'''
    print(y)

You can even perform operations on strings
 
    >>> "mambo" * 2
    'mambomambo'
    >>> print("*"*40)
    ****************************************

There are builtin functions like ``len`` that can be used to find the length of a string
 
    >>> len("mambo")
    5

Lists
-----

Lists are one of the most important types in Python

    >>> names = [] # creates an empty list
    >>> names = ["britone", "mwasaru"] # creates a list with 2 items 
    >>> len(names) # function len gets as the lenght of the list
    2
    >>> names[0] # gets us the first item in the list
    'britone'
    >>> names[1] # gets us the second item in the list
    'mwasaru'


Functions
---------

Just like a value can be associated with a name, a piece of logic can also be
associated with a name by defining a function.

    >>> def square(x):
    ...    return x * x
    ...
    >>> square(5)
    25

The body of the function is indented. Indentation is the Python's way of
grouping statements.

The ``...`` is the secondary prompt, which the Python interpreter uses to
denote that it is expecting some more input.

The functions can be used in any expressions.

    >>> square(2) + square(3)
    13
    >>> square(square(3))
    81

Existing functions can be used in creating new functions.

    >>> def sum_of_squares(x, y):
    ...    return square(x) + square(y)
    ...
    >>> sum_of_squares(2, 3)
    13

Functions are just like other values, they can assigned, passed as arguments to
other functions etc.

    >>> f = square
    >>> f(4)
    16

    >>> def fxy(f, x, y):
    ...     return f(x) + f(y)
    ...
    >>> fxy(square, 2, 3)
    13

It is important to understand, the scope of the variables used in functions.

Lets look at an example.

    x = 0
    y = 0
    def incr(x):
        y = x + 1
        return y
    incr(5)
    print(x, y)

Variables assigned in a function, including the arguments are called the local
variables to the function. The variables defined in the top-level are called
global variables.

Changing the values of ``x`` and ``y`` inside the function ``incr`` won't
effect the values of global ``x`` and ``y``.

But, we can use the values of the global variables.

    pi = 3.14
    def area(r):
        return pi * r * r

When Python sees use of a variable not defined locally, it tries to find a
global variable with that name.

However, you have to explicitly declare a variable as ``global`` to modify it.

    numcalls = 0
    def square(x):
        global numcalls
        numcalls = numcalls + 1
        return x * x

    print(square(5))
    print(square(2*5))

	x = 1
	def f():
            return x
	print(x)
	print(f())

	x = 1
	def f():
            x = 2
            return x
	print(x)
	print(f())
	print(x)


	x = 1
	def f():
		y = x
		x = 2
		return x + y
	print(x)
	print(f())
	print(x)


    x = 2
    def f(a):
        x = a * a
        return x
    y = f(3)
    print(x, y)

Functions can be called with keyword arguments.


    >>> def difference(x, y):
    ...    return x - y
    ...
    >>> difference(5, 2)
    3
    >>> difference(x=5, y=2)
    3
    >>> difference(5, y=2)
    3
    >>> difference(y=2, x=5)
    3

And some arguments can have default values.

    >>> def increment(x, amount=1):
    ...    return x + amount
    ...
    >>> increment(10)
    11
    >>> increment(10, 5)
    15
    >>> increment(10, amount=2)
    12

Built-in Functions
------------------

Python provides some useful built-in functions.

    >>> min(12, 3)
    3
    >>> max(23, 34)
    34

The built-in function ``len`` computes length of a string.

    >>> len(" pwaniteknowgalz python")
    17

The built-in function ``int`` converts string to ingeter and built-in function
``str`` converts integers and other type of objects to strings.


    >>> int("2323")
    2323
    >>> str(2323)
    "2323"

Methods
-------

Methods are special kind of functions that work on an object.

For example, ``upper`` is a method available on string objects.

    >>> x = " pwaniteknowgalz"
    >>> print(x.upper())
     PWANITEKNOWGALZ

As already mentioned, methods are also functions. They can be assigned to other
variables can be called separately.

 

    >>> f = x.upper
    >>> print(f())
     PWANITEKNOWGALZ

Conditional Expressions
-----------------------

There are operators for comparing values, the result is a boolean value either ```True``` or ```False```

    >>> 2 > 3
    False
    >>> 2 < 3
    True

These are the available conditional operators.

* ``==`` equal to
* ``!=`` not equal to
* ``<`` less than
* ``>`` greater than
* ``<=`` less than or equal to
* ``>=`` greater than or equal to 

These operators can be combined

    >>> y = 10
    >>> 4 < y > 5
    True
    >>> 11 > y < 12
    False

You can combine boolean values using logical operators

* ``x and y`` is ``True`` only if both ``x`` and ``y`` are True.
* ``x or y`` is True if either ``x`` or ``y`` is True.
* ``not x`` is True only if ``x`` is False.

Example

    >>> True and True
    True
    >>> True and False
    False

Control Structures
------------------

if statements
-------------

In python if statement is the main statement used for selecting from alternative actions based on test results

 

    >>> names = ["Britone", "Angela", "Maria", "Brian"]
    >>> if "Maria" in names:
    ...     print("Maria is present")
    >>> if "Aliya" in names:
    ...     print("Aliya is in the house :)")
    ... else:
    ...     print("Aliya is absent :(")

for loop
--------

for statement, is designed for stepping through the items in a sequence or other iterable object and running a block of code for each.

 

    >>> names = ["Britone", "Angela", "Maria", "Brian"]
    >>> for name in names:
    ...     print(name)
    ...
    Britone
    Angela
    Maria
    Brian

while loop
----------

while statement repeatedly executes a block of statements as long as a test at the top keeps evaluating to a true value.

 

    >>> while True:
    ...     print("Press Ctrl+C to stop me!")
    Press Ctrl+C to stop me!
    Press Ctrl+C to stop me!
    Press Ctrl+C to stop me!
    Press Ctrl+C to stop me!
    Press Ctrl+C to stop me!
    Press Ctrl+C to stop me!
    Press Ctrl+C to stop me!
    
