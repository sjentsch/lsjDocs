.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_, and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_, and `Sebastian Jentschke <https://www4.uib.no/en/find-employees/Sebastian.Jentschke>_`

Mathematical functions and operations
-------------------------------------

In the previous section, I discussed the ideas behind variable transformations
and showed that a lot of the transformations that you might want to apply to
your data are based on fairly simple mathematical functions and operations. In
this section I want to return to that discussion and mention several other
mathematical functions and arithmetic operations that are actually quite useful
for a lot of real-world data analysis. :numref:`tab-mathfunc` gives a brief
overview of the various mathematical functions I want to talk about here, or
later.\ [#]_ Obviously this does not even come close to cataloguing the range of
possibilities available, but it does cover a range of functions that are used
regularly in data analysis and that are available in jamovi.

.. table:: Some of the mathematical functions available in jamovi
   :name: tab-mathfunc

   +----------------+----------------------+----------------------+----------+
   |                | Function             | Example input        |   result |
   +================+======================+======================+==========+
   | Square root    | ``SQRT(x)``          | ``SQRT(25)``         |        5 |
   +----------------+----------------------+----------------------+----------+
   | Absolute value | ``ABS(x)``           | ``ABS(-23)``         |       23 |
   +----------------+----------------------+----------------------+----------+
   | Logarithm      | ``LOG10(x)``         | ``LOG10(1000)``      |        3 |
   | (base 10)      |                      |                      |          |
   +----------------+----------------------+----------------------+----------+
   | Logarithm      | ``LN(x)``            | ``LN(1000)``         |    6.908 |
   | (base *e*)     |                      |                      |          |
   +----------------+----------------------+----------------------+----------+
   | Exponentiation | ``EXP(x)``           | ``EXP(6.908)``       | 1000.245 |
   +----------------+----------------------+----------------------+----------+
   | Box-Cox        | ``BOXCOX(x, lamda)`` | ``BOXCOX(6.908, 3)`` |  109.551 |
   +----------------+----------------------+----------------------+----------+
   | Rounding to    | ``ROUND()``          | ``ROUND(1.32)``      |        1 |
   | nearest        |                      |                      |          |
   +----------------+----------------------+----------------------+----------+
   | Rounding down  | ``FLOOR()``          | ``FLOOR(1.32)``      |        1 |
   +----------------+----------------------+----------------------+----------+
   | Rounding up    | ``CEILING()``        | ``CEILING(1.32)``    |        2 |
   +----------------+----------------------+----------------------+----------+

Rounding values
~~~~~~~~~~~~~~~

One very simple transformation that crops up surprisingly often is the need
to round a number to the nearest whole number, or to a certain number of
significant digits. To start with, let's assume that we want to round to a
whole number. To that end, there are three useful functions in jamovi you want
to know about: ``ROUND()``, ``FLOOR()`` and ``CEILING()``.
The ``ROUND()`` function just rounds the values in a variable to the *nearest*
whole number. So if you had a variable value  of 4.3, it would be “rounded
down” to 4. In contrast, if we want to round the variable value 4.7, we would
round upwards to 5. In everyday life, when someone talks about "rounding",
they usually mean “round to the nearest”, so this is the function we use most
of the time. Sometimes, you have reasons to want to always round up or always
round down. If you want to always round down, use the ``FLOOR()`` function
instead; and if you want to round up, then use ``CEILING()``. Finally, in some
cases you want to round to a a fixed number of decimal places, say 2 decimal
places. If so, what you need to do is provide the number of places as an
argument to the ``ROUND()`` function. However, please note that only
``ROUND()`` accepts the number of decimal places as argument, whereas
``FLOOR()`` and ``CEILING()`` do not.

The functions are used as follows (with ``VAR`` being a placeholder for a
variable name):

.. code-block:: text

   ROUND(``VAR``)
   ROUND(``VAR``, 2)
   FLOOR(``VAR``)
   CEILING(``VAR``)

Modulus and integer division
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Since we are on the topic of simple calculations, there are two other
arithmetic operations that I should mention, since they can come in handy when
working with real data. These operations are calculating a modulus and doing
integer division. First, let's consider **integer division**. Suppose I have
\$42 in my wallet, and want to buy some sandwiches, which are selling for \$10
each. How many sandwiches can I afford to buy? The answer is 4.\ [#]_ Note
that it is not 4.2, since no shop will sell me one-fifth of a sandwich.
Integer division is performed by using the ``INT()`` operator. The **modulus**
is the remainder after integer division, and it is calculated using the ``%``
operator. For the sake of argument, let us suppose I buy four overpriced \$10
sandwiches. If I started out with \$42, how much money do I have left? The
answer, as both jamovi and common sense tells us, is \$2. It is possible to
calculate just one value using the functions below (then this value would be
shown in every row), but most often it is more useful to apply these functions
to a variable (where the calculation is performed on the value of the variable
in that row).

.. code-block:: text

   INT(42 / 10)
   INT(``VAR`` / 10)
   42 % 10
   ``VAR`` % 10
   -42 % 10


There is, however, one subtlety (demonstrated in the last line) that I need to
mention, and this relates to how negative numbers are handled by the modulus
operator. Suppose I *owe* the sandwich shop \$42, but I do not have any money.
To pay my debts, I would have to hand over five sandwiches to the shop in
order to pay off my debt of \$42, then *they* now owe me \$8.

Logarithms and exponentials
~~~~~~~~~~~~~~~~~~~~~~~~~~~

As I have mentioned earlier, jamovi has a useful range of mathematical
functions built into it and there really would not be much point in
trying to describe or even list all of them. For the most part, I have
focused only on those functions that are strictly necessary for this
book. However I do want to make an exception for logarithms and
exponentials. Although they are not needed anywhere else in this book,
they are *everywhere* in statistics more broadly. And not only that,
there are a *lot* of situations in which it is convenient to analyse the
logarithm of a variable (i.e., to take a “log-transform” of the
variable). I suspect that many (maybe most) readers of this book will
have encountered logarithms and exponentials before, but from past
experience I know that there is a substantial proportion of students who
take a social science statistics class who have not touched logarithms
since high school, and would appreciate a bit of a refresher.

In order to understand logarithms and exponentials, the easiest thing to
do is to actually calculate them and see how they relate to other simple
calculations. There are three jamovi functions in particular that I want
to talk about, namely ``LN()``, ``LOG10()`` and ``EXP()``. To start
with, let us consider ``LOG10()``, which is known as the “logarithm in
base 10”. The trick to understanding a **logarithm** is to understand
that it is basically the “opposite” of taking a power. Specifically, the
logarithm in base 10 is closely related to the powers of 10. So let us
start by noting that 10-cubed is 1000. Mathematically, we would write
this:

| 10³ = 1000

The trick to understanding a logarithm is to recognise that the
statement that “10 to the power of 3 is equal to 1000” is equivalent to
the statement that “the logarithm (in base 10) of 1000 is equal to 3”.
Mathematically, we write this as:

| log\ :sub:`10`\(1000) = 3

Okay, since the ``LOG10()`` function is related to the powers of 10, you
might expect that there are other logarithms (in bases other than 10)
that are related to other powers too. And of course that is true: there is
not really anything mathematically special about the number 10. You and
I happen to find it useful because decimal numbers are built around the
number 10, but the big bad world of mathematics scoffs at our decimal
numbers. Sadly, the universe does not actually care how we write down
numbers. Anyway, the consequence of this cosmic indifference is that
there is nothing particularly special about calculating logarithms in
base 10. You could, for instance, calculate your logarithms in base 2.
Alternatively, a third type of logarithm, and one we see a lot more of
in statistics than either base 10 or base 2, is called the **natural
logarithm**, and corresponds to the logarithm in base *e*. Since you might one
day run into it, I should better explain what *e* is. The number *e*, known as
**Euler’s number**, is one of those annoying “irrational” numbers whose decimal
expansion is infinitely long, and is considered one of the most important
numbers in mathematics. The first few digits of *e* are:

*e* = 2.718282

There are quite a few situations in statistics that require us to
calculate powers of *e*, though none of them appear in this book.
Raising *e* to the power *x* is called the **exponential**
of *x*, and so it is very common to see e\ :sup:`x` written as
*exp(x)*. And so it is no surprise that jamovi has a function that
calculates exponentials, called ``EXP()``. Because the number *e*
crops up so often in statistics, the natural logarithm (i.e., logarithm
in base *e*) also tends to turn up. Mathematicians often write it
as log\ :sub:`e`\ (x) or *ln(x)*. In fact, jamovi works the same
way: the ``LN()`` function corresponds to the natural logarithm.

And with that, I think we have had quite enough exponentials and
logarithms for this book!

.. Transforming skewed variables
   ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

   Add in details about sqrt and boxcox as useful for transforming skewed
   variables

------

.. [#]
   The real answer is 0: \$10 for a sandwich is a total ripoff so I
   should go next door and buy noodles.

.. [#]
   We will leave the box-cox function until :ref:`later on <box-cox>`.
