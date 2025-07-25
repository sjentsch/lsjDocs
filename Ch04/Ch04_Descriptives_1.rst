.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Measures of central tendency
----------------------------

Drawing pictures of the data, as I did in :numref:`fig4-2`, is an excellent way
to convey the “gist” of what the data is trying to tell you. It is often
extremely useful to try to condense the data into a few simple “summary”
statistics. In most situations, the first thing that you will want to calculate
is a measure of **central tendency**. That is, you would like to know something
about where the “average” or “middle” of your data lies. The three most
commonly used measures are the mean, median and mode. I will explain each of
these in turn, and then discuss when each of them is useful.

The mean
~~~~~~~~

The **mean** of a set of observations is just a normal, old-fashioned average.
Add all of the values up, and then divide by the total number of values. The
first five AFL winning margins were 56, 31, 56, 8 and 32, so the mean of these
observations is just:

.. math:: \frac{56 + 31 + 56 + 8 + 32}{5} = \frac{183}{5} = 36.60

Of course, this definition of the mean is not news to anyone. Averages (i.e.,
means) are used so often in everyday life that this is pretty familiar stuff.
However, since the concept of a mean is something that everyone already
understands, I will use this as an excuse to start introducing some of the
mathematical notation that statisticians use to describe this calculation, and
talk about how the calculations would be done in jamovi.

The first piece of notation to introduce is *N*, which we will use to refer to
the number of observations that we are averaging (in this case *N* = 5). Next,
we need to attach a label to the observations themselves. It is traditional to
use *X* for this, and to use subscripts to indicate which observation we are
actually talking about. That is, we will use *X*\ :sub:`1` to refer to the first
observation, *X*\ :sub:`2` to refer to the second observation, and so on all the
way up to *X*\ :sub:`N` for the last one. Or, to say the same thing in a slightly
more abstract way, we use *X*\ :sub:`i` to refer to the *i*-th observation. Just
to make sure we are clear on the notation, the following table lists the 5
observations in the ``afl.margins`` variable, along with the mathematical
symbol used to refer to it and the actual value that the observation
corresponds to:

+------------------------+---------------+--------------------+
| the observation        | its symbol    | the observed value |
+========================+===============+====================+
| winning margin, game 1 | *X*\ :sub:`1` |          56 points |
+------------------------+---------------+--------------------+
| winning margin, game 2 | *X*\ :sub:`2` |          31 points |
+------------------------+---------------+--------------------+
| winning margin, game 3 | *X*\ :sub:`3` |          56 points |
+------------------------+---------------+--------------------+
| winning margin, game 4 | *X*\ :sub:`4` |           8 points |
+------------------------+---------------+--------------------+
| winning margin, game 5 | *X*\ :sub:`5` |          32 points |
+------------------------+---------------+--------------------+

Okay, now let us try to write a formula for the mean. By tradition, we use *X̄*
as the notation for the mean. So the calculation for the mean could be
expressed using the following formula:

.. math:: \bar{X} = \frac{X_1 + X_2 + \ldots + X_{N - 1} + X_N}{N}

This formula is entirely correct but it is terribly long, so we make use
of the **summation symbol** Σ to shorten it.\ [#]_ If I want to add up the
first five observations I could write out the sum the long way, *X*\ :sub:`1` +
*X*\ :sub:`2` + *X*\ :sub:`3` + *X*\ :sub:`4` + *X*\ :sub:`5` or I could use
the summation symbol to shorten it to this:

.. math:: \sum_{i = 1} ^ 5 X_i

Taken literally, this could be read as “the sum, taken over all *i* values from
1 to 5, of the value *X*\ :sub:`i`”. But basically what it means is “add up the
first five observations”. In any case, we can use this notation to write out
the formula for the mean, which looks like this:

.. math:: \bar{X} = \frac{1}{N} \sum_{i = 1} ^ N X_i

In all honesty, I can not imagine that all this mathematical notation helps
clarify the concept of the mean at all. In fact, it is really just a fancy way
of writing out the same thing I said in words: add all the values up and then
divide by the total number of items. However, that is not really the reason I
went into all that detail. My goal was to try to make sure that everyone
reading this book is clear on the notation that we will be using throughout the
book: *X̄* for the mean, Σ for the idea of summation, *X*\ :sub:`i` for the
*i*-th observation, and *N* for the total number of observations. We are going
to be re-using these symbols a fair bit so it is important that you understand
them well enough to be able to “read” the equations, and to be able to see that
it is just saying “add up lots of things and then divide by another thing”.

Calculating the mean in jamovi
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Okay, that is the maths. So how do we get the magic computing box to do the
work for us? When the number of observations starts to become large it is much
easier to do these sorts of calculations using a computer. To calculate the
mean using all the data we can use jamovi. The first step is to click on the
``Exploration`` button and then click ``Descriptives``. Then you can highlight
the ``afl.margins`` variable and click the ``→`` to move it across into the
``Variables`` box. As soon as you do that a table appears on the right-hand
side of the screen containing default ``Descriptives`` information, as shown in
:numref:`fig4-3`.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig4-3.*
   :alt: AFL 2010 winning margin data
   :name: fig4-3

   Default descriptives for the AFL 2010 winning margin data (the 
   ``afl.margins`` variable).
   
.. ----------------------------------------------------------------------------


As you can see in :numref:`fig4-3`, the mean value for the ``afl.margins``
variable is **35.30**. Other information presented includes the total number of
observations (*N* = 176), the number of missing values (none), and the median,
minimum and maximum values for the variable.

The median
~~~~~~~~~~

The second measure of central tendency that people use a lot is the **median**,
and it is even easier to describe than the mean. The median of a set of
observations is just the middle value. As before let us imagine we were
interested only in the first five AFL winning margins: 56, 31, 56, 8 and 32.
To figure out the median we sort these numbers into ascending order:

| 8, 31, **32**, 56, 56

From inspection, it is obvious that the median value of these five observations
is 32 since that is the middle one in the sorted list (I have put it in bold to
make it even more obvious). Easy stuff. But what should we do if we are
interested in the first six games rather than the first five? Since the sixth
game in the season had a winning margin of 14 points, our sorted list is now:

| 8, 14, **31**, **32**, 56, 56

Now, there are *two* middle numbers, 31 and 32. The median is defined as the
average of those two numbers, which is of course 31.5. As before, it is very
tedious to do this by hand when you have got lots of numbers. In real life, of
course, no-one actually calculates the median by sorting the data and then
looking for the middle value. In real life, we use a computer to do the heavy
lifting for us, and jamovi has provided us with a median value of 30.50 for the
``afl.margins`` variable (see :numref:`fig4-3`).

Mean or median? What is the difference?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Knowing how to calculate means and medians is only a part of the story. You
also need to understand what each one is saying about the data, and what that
implies for when you should use each one. This is illustrated in 
:numref:`fig4-4`. The mean is kind of like the “centre of gravity” of the data
set, whereas the median is the “middle value” in the data. What this implies,
as far as which one you should use, depends a little on what type of data you
have got and what you are trying to achieve. As a rough guide:

-  If your data are nominal scale |nominal| you probably should not be using
   either the mean or the median. Both the mean and the median rely on the idea 
   that the numbers assigned to values are meaningful. If the numbering scheme 
   is arbitrary then it is probably best to use the :ref:`Mode <mode>` instead.

-  If your data are ordinal scale |ordinal| you are more likely to want to use
   the median than the mean. The median only makes use of the order information 
   in your data (i.e., which numbers are bigger) but does not depend on the 
   precise numbers involved. That is exactly the situation that applies when 
   your data are ordinal scale |ordinal|. The mean, on the other hand, makes 
   use of the precise numeric values assigned to the observations, so it is not 
   really appropriate for ordinal data.

-  For interval and ratio scale data |continuous| either one is generally
   acceptable. Which one you pick depends a bit on what you are trying to
   achieve. The mean has the advantage that it uses all the information in the
   data (which is useful when you do not have a lot of data). But it is very 
   sensitive to extreme, outlying values.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig4-4.*
   :alt: Comparison of mean and median
   :name: fig4-4

   Illustration of the difference between how the mean and the median should be
   interpreted. The mean is basically the “centre of gravity” of the data set.
   If you imagine that the histogram of the data is a solid object, then the
   point on which you could balance it (as if on a see-saw) is the mean. In
   contrast, the median is the middle observation, with half of the
   observations smaller and half of the observations larger.
   
.. ----------------------------------------------------------------------------

Let us expand on that last part a little. One consequence is that there are
systematic differences between the mean and the median when the histogram is
asymmetric (skewed; see :doc:`Ch04_Descriptives_3`). This is illustrated in
:numref:`fig4-4`. Notice that the median (right-hand side) is located closer to
the “body” of the histogram, whereas the mean left-hand side) gets dragged
towards the “tail” (where the extreme values are). To give a concrete example,
suppose Bob (income 50 000 €), Kate (income 60 000 €) and Jane (income 65 000 €)
are sitting at a table. The average income at the table is 58 333 € and the
median income is 60 000 €. Then Bill sits down with them (income 100 000 000 €).
The average income has now jumped to 25 043 750 € but the median rises only to
62 500 €. If you are interested in looking at the overall income at the table
the mean might be the right answer. But if you are interested in what counts as
a typical income at the table the median would be a better choice here.

.. _a_real_life_example:

A real-life example
~~~~~~~~~~~~~~~~~~~

To try to get a sense of why you need to pay attention to the differences
between the mean and the median let us consider a real-life example. Since I
tend to mock journalists for their poor scientific and statistical knowledge, I
should give credit where credit is due. This is described in an excellent
article by Michael Janda: `Housing bubble debate boils over
<https://www.abc.net.au/news/stories/2010/09/24/3021480.htm>`__:

   Senior Commonwealth Bank executives have travelled the world in the  past 
   couple of weeks with a presentation showing how Australian house prices, and 
   the key price to income ratios, compare favourably with similar countries. 
   “Housing affordability has actually been going sideways for the last five to 
   six years,” said Craig James, the chief economist of the bank’s trading arm, 
   CommSec.

This probably comes as a huge surprise to anyone with a mortgage, or who wants
a mortgage, or pays rent, or is not completely oblivious to what is been going
on in the Australian housing market over the last several years. Back to the
article:

   CBA has waged its war against what it believes are housing doomsayers with 
   graphs, numbers and international comparisons. In its presentation, the bank 
   rejects arguments that Australia’s housing is relatively expensive compared 
   to incomes. It says Australia’s house price to household income ratio of 5.6 
   in the major cities, and 4.3 nationwide, is comparable to many other
   developed nations. It says San Francisco and New York have ratios of 7, 
   Auckland’s is 6.7, and Vancouver comes in at 9.3.

More excellent news! Except, the article goes on to make the observation that:

   Many analysts say that has led the bank to use misleading figures and
   comparisons. If you go to page four of CBA’s presentation and read the 
   source information at the bottom of the graph and table, you would notice 
   there is an additional source on the international comparison – Demographia. 
   However, if the Commonwealth Bank had also used Demographia’s analysis of 
   Australia’s house price to income ratio, it would have come up with a figure 
   closer to 9 rather than 5.6 or 4.3.

That is, um, a rather serious discrepancy. One group of people say 9, another
says 4 to 5. Should we just split the difference and say the truth lies
somewhere in between? Absolutely not! This is a situation where there is a
right answer and a wrong answer. Demographia is correct, and the Commonwealth
Bank is wrong. As the article points out:

   [An] obvious problem with the Commonwealth Bank’s domestic price to income 
   figures is they compare average incomes with median house prices (unlike the 
   Demographia figures that compare median incomes to median prices). The 
   median is the mid-point, effectively cutting out the highs and lows, and 
   that means the average is generally higher when it comes to incomes and 
   asset prices, because it includes the earnings of Australia’s wealthiest 
   people. To put it another way: the Commonwealth Bank’s figures count Ralph 
   Norris’ multi-million dollar pay packet on the income side, but not his 
   (no doubt) very expensive house in the property price figures, thus 
   understating the house price to income ratio for middle-income Australians.

I could not have put it better myself. The way that Demographia calculated the
ratio is correct. The way that the Bank did it is incorrect. As for why an
extremely quantitatively sophisticated organisation such as a major bank made
such an elementary mistake, well… I can not say for sure since I have no
special insight into their thinking. But the article itself does happen to
mention the following facts, which may or may not be relevant:

   [As] Australia’s largest home lender, the Commonwealth Bank has one of the 
   biggest vested interests in house prices rising. It effectively owns a 
   massive swathe of Australian housing as security for its home loans as well 
   as many small business loans.

.. _mode:

Mode
~~~~

The mode of a sample is very simple. It is the value that occurs most
frequently. We can illustrate the mode using a different AFL variable: who has
played in the most finals? Open the |aflsmall_finalists|_ data set and take a
look at the ``afl.finalists`` variable, see :numref:`fig4-5`. This variable
contains the names of all 400 teams that played in all 200 finals matches
played during the period 1987 to 2010.


.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig4-5.*
   :alt: Variables in |aflsmall_finalists|
   :name: fig4-5

   Screenshot of jamovi showing the variables stored in the
   |aflsmall_finalists|_ data set
   
.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig4-6.*
   :alt: Frequency table for the ``afl.margins`` variable in 
         |aflsmall_finalists|
   :name: fig4-6

   Screenshot of jamovi showing the frequency table for the ``afl.finalists``
   variable in the |aflsmall_finalists|_ data set
   
.. ----------------------------------------------------------------------------

What we *could* do is read through all 400 entries and count the number of
occasions on which each team name appears in our list of finalists, thereby
producing a **frequency table**. However, that would be mindless and boring:
exactly the sort of task that computers are great at. So let us use jamovi to
do this for us. Under ``Exploration`` → ``Descriptives`` click the small check
box labelled ``Frequency tables`` and you should get something like
:numref:`fig4-6`.

Now that we have our frequency table we can just look at it and see that, over
the 24 years for which we have data, Geelong has played in more finals than any
other team. Thus, the mode of the ``afl.finalists`` data is “Geelong”. We can
see that Geelong (39 finals) played in more finals than any other team during
the 1987 to 2010 period. It is also worth noting that in the
``Descriptives``-table no results are calculated for mean, median, minimum or
maximum. This is because the ``afl.finalists`` variable is a nominal (text)
variable so it makes no sense to calculate these values.

One last point to make regarding the mode. Whilst the mode is most often 
calculated when you have nominal data, because means and medians are useless
for those sorts of variables, there are some situations in which you really do
want to know the mode of an ordinal, interval or ratio scale variable. For
instance, let us go back to our ``afl.margins`` variable. This variable is
clearly ratio scale (if it is not clear to you, it may help to reread section
:doc:`Scales of measurement <../Ch02/Ch02_StudyDesign_2>`), and so in most
situations the mean or the median is the measure of central tendency that you
want. But consider this scenario: a friend of yours is offering a bet and they
pick a football game at random. Without knowing who is playing you have to
guess the *exact* winning margin. If you guess correctly you win 50 €. If you
do not you lose 1 €. There are no consolation prizes for “almost” getting the
right answer. You have to guess exactly the right margin. For this bet, the
mean and the median are completely useless to you. It is the mode that you
should bet on. To calculate the mode for the ``afl.margins`` variable in
jamovi, go back to that data set and in the ``Exploration`` → ``Descriptives``
analysis panel you will see you can expand the drop-down menu ``Statistics``.
Click on the checkbox marked ``Mode`` and you will see the modal value
presented in the ``Descriptives``-table, as in :numref:`fig4-7`. So, the 2010
data suggest you should bet on a 3-point margin.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig4-7.*
   :alt: Modal value of the ``afl.margins`` variable in |aflsmall_finalists|
   :name: fig4-7

   Screenshot of jamovi showing the modal value for the ``afl.margins``
   variable
   
.. ----------------------------------------------------------------------------

------

.. [#]
   The choice to use *Σ* to denote summation is not arbitrary. It is the Greek
   upper case letter sigma, which is the analogue of the letter S in that
   alphabet. Similarly, there is an equivalent symbol used to denote the
   multiplication of lots of numbers, because multiplications are also called
   “products” we use the *Π* symbol for this (the Greek upper case pi, which is
   the analogue of the letter P).

.. ----------------------------------------------------------------------------
   
.. |aflsmall_finalists|                replace:: ``aflsmall_finalists``
.. _aflsmall_finalists:                ../../_static/data/aflsmall_finalists.omv

.. |continuous|                        image:: ../_images/variable-continuous.*
   :width: 16px
 
.. |nominal|                           image:: ../_images/variable-nominal.*
   :width: 16px
 
.. |ordinal|                           image:: ../_images/variable-ordinal.*
   :width: 16px
