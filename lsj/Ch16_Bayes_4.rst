.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Bayesian t-tests
----------------

An important type of statistical inference problem discussed in this book is
the comparison between two means, discussed in some detail in the chapter on
*t*-tests (Chapter `Comparing two means <Ch11_tTest.html#comparing-two-means>`__).
If you can remember back that far, you’ll recall that there are several
versions of the *t*-test. I’ll talk a little about Bayesian
versions of the independent samples *t*-tests and the paired
samples *t*-test in this section.

Independent samples t-test
~~~~~~~~~~~~~~~~~~~~~~~~~~

The most common type of *t*-test is the independent samples *t*-test, and it
arises when you have data as in the ``harpo`` dataset that we used in the
earlier chapter on *t*-tests (Chapter `Comparing two means
<Ch11_tTest.html#comparing-two-means>`__). In this data set, we have two
groups of students, those who received lessons from Anastasia and those
who took their classes with Bernadette. The question we want to answer
is whether there’s any difference in the grades received by these two
groups of students. Back in that chapter, I suggested you could analyse this
kind of data using the Independent Samples *t*-test in jamovi, which gave us
the results in :numref:`fig-bayes1`. As we obtain a *p*-value less than \0.05,
we reject the null hypothesis.

.. ----------------------------------------------------------------------------

.. _fig-bayes1:
.. figure:: ../_images/lsj_bayes1.*
   :alt: Independent Samples t-test result in jamovi

   Independent Samples t-test result in jamovi
   
.. ----------------------------------------------------------------------------

What does the Bayesian version of the *t*-test look like? We can get the Bayes
factor analysis by selecting the ‘Bayes factor’ checkbox under the ‘Tests’
option, and accepting the suggested default value for the ‘Prior’. This gives
the results shown in the table in :numref:`fig-bayes2`. What we get in this
table is a Bayes factor statistic of 1.75, meaning that the evidence provided
by these data are about 1.8:1 in favour of the alternative hypothesis.

.. ----------------------------------------------------------------------------

.. _fig-bayes2:
.. figure:: ../_images/lsj_bayes2.*
   :alt: Bayes factors analysis alongside Independent Samples t-Test

   Bayes factors analysis alongside Independent Samples t-Test
   
.. ----------------------------------------------------------------------------

Before moving on, it’s worth highlighting the difference between the orthodox
test results and the Bayesian one. According to the orthodox test, we obtained
a significant result, though only barely. Nevertheless, many people would
happily accept *p* = 0.043 as reasonably strong evidence for an effect. In
contrast, notice that the Bayesian test doesn’t even reach 2:1 odds in favour
of an effect, and would be considered very weak evidence at best. In my
experience that’s a pretty typical outcome. Bayesian methods usually require
more evidence before rejecting the null.

Paired samples *t*-test
~~~~~~~~~~~~~~~~~~~~~~~

Back in Section `The paired-samples t-test <Ch11_tTest_05.html#the-paired-samples-t-test>`__
I discussed the ``chico.csv`` data set in which student grades were measured on
two tests, and we were interested in finding out whether grades went up from
test 1 to test 2. Because every student did both tests, the tool we used to
analyse the data was a paired samples *t*-test. :numref:`fig-bayes3` shows the
jamovi results table for the conventional paired *t*-test alongside the Bayes
factor analysis. At this point, I hope you can read this output without any
difficulty. The data provide evidence of about 6000:1 in favour of the
alternative. We could probably reject the null with some confidence!

.. ----------------------------------------------------------------------------

.. _fig-bayes3:
.. figure:: ../_images/lsj_bayes3.*
   :alt: Paired samples T-Test and Bayes Factor result in jamovi

   Paired samples T-Test and Bayes Factor result in jamovi
   
.. ----------------------------------------------------------------------------

So that’s pretty straightforward: it’s exactly what we’ve been doing
throughout the book. The output, however, is a little different from
what you get from ``lm()``. Here’s what we get:

.. code-block:: rout

   Bayes factor analysis
   --------------
   [1] dan.sleep                    : 1.622545e+34 @plusorminus0%
   [2] day                          : 0.2724027    @plusorminus0%
   [3] baby.sleep                   : 10018411     @plusorminus0%
   [4] dan.sleep + day              : 1.016578e+33 @plusorminus0.01%
   [5] dan.sleep + baby.sleep       : 9.770233e+32 @plusorminus0.01%
   [6] day + baby.sleep             : 2340755      @plusorminus0%
   [7] dan.sleep + day + baby.sleep : 7.835625e+31 @plusorminus0%

   Against denominator:
     Intercept only 
   ---
   Bayes factor type: BFlinearModel, JZS

The format of this is pretty familiar. At the bottom we have some
techical rubbish, and at the top we have some information about the
Bayes factors. What’s new is the fact that we seem to have *lots* of
Bayes factors here. What’s all this about?

The trick to understanding this output is to recognise that if we’re
interested in working out which of the 3 predictor variables are related
to ``dan.grump``, there are actually 8 possible regression models that
could be considered. One possibility is the *intercept only model*, in
which none of the three variables have an effect. At the other end of
the spectrum is the *full model* in which all three variables matter. So
what ``regressionBF()`` does is treat the *intercept only* model as the
null hypothesis, and print out the Bayes factors for all other models
when compared against that null. For example, if we look at line 4 in
the table, we see that the evidence is about 10\ :sup:`33` to 1 in
favour of the claim that a model that includes both ``dan.sleep`` and
``day`` is better than the intercept only model. Or if we look at line
1, we can see that the odds are about 1.6 · 10\ :sup:`34` that a
model containing the ``dan.sleep`` variable (but no others) is better
than the intercept only model.
