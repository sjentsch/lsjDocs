.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Checking the normality of a sample
----------------------------------

All of the tests that we have discussed so far in this chapter have assumed
that the data are normally distributed. This assumption is often quite
reasonable, because :ref:`the central limit theorem <central_limit_theorem>`
does tend to ensure that many real-world quantities are normally distributed.
Any time that you suspect that your variable is *actually* an average of lots
of different things, there is a pretty good chance that it will be normally
distributed, or at least close enough to normal that you can get away with
using *t*-tests. However, life does not come with guarantees, and besides there
are lots of ways in which you can end up with variables that are highly
non-normal. For example, any time you think that your variable is actually the
minimum of lots of different things, there is a very good chance it will end up
quite skewed. In psychology, response time (RT) data is a good example of this.
If you suppose that there are lots of things that could trigger a response from
a human participant, then the actual response will occur the first time one of
these trigger events occurs.\ [#]_ This means that RT data are systematically
non-normal. Okay, so if normality is assumed by all the tests, and is mostly
but not always satisfied (at least approximately) by real-world data, how can
we check the normality of a sample? In this section I discuss two methods:
QQ plots and the Shapiro-Wilk test.

QQ plots
~~~~~~~~

One way to check whether a sample violates the normality assumption is
to draw a **“QQ plot”** (Quantile-Quantile plot). This allows you to
visually check whether you are seeing any systematic violations. In a QQ
plot, each observation is plotted as a single dot. The x co-ordinate is
the theoretical quantile that the observation should fall in if the data
were normally distributed (with mean and variance estimated from the
sample), and on the y co-ordinate is the actual quantile of the data
within the sample. If the data are normal, the dots should form a
straight line. For instance, lets see what happens if we generate data
by sampling from a normal distribution, and then drawing a QQ plot. The
results are shown in :numref:`fig11-21`.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig11-20.*
   :alt: Histogram and QQ plot for normally-distributed data
   :name: fig11-20

   Histogram (left panel) and QQ plot (right panel) for the column ``Normal``
   in the |distributions|_ data set, a normally-distributed sample with 200
   observations. The Shapiro-Wilk statistic associated with these data is
   *W* = 0.992, indicating that no significant departures from normality were
   detected (*p* = 0.361).
   
.. ----------------------------------------------------------------------------

As you can see, these data form a pretty straight line; which is no surprise
given that we sampled them from a normal distribution! In contrast, have a look
at the two data sets shown in :numref:`fig11-21`. The top panels show the
histogram and a QQ plot for a data set that is highly skewed: the QQ plot
curves upwards. The lower panels show the same plots for a heavy tailed (i.e.,
high kurtosis) data set: in this case the QQ plot flattens in the middle and
curves sharply at either end.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig11-21.*
   :alt: Histogram and QQ plot for skewed and tailed data
   :name: fig11-21

   In the top row, a histogram (top-left panel) and QQ plot (top-right panel)
   for 200 observations in the column ``Skewed`` of the |distributions|_ data
   set. The skewness of the data here is 1.543, and is reflected in a QQ plot
   that curves upwards and is lacking the lower values within the
   ``Standardized Residuals``. As a consequence, the Shapiro-Wilk statistic is
   *W* = 0.732, reflecting a significant departure from normality (*p* <
   0.001). The bottom row shows the same plots for the 200 observations in the
   column ``Heavy Tailed`` of the |distributions|_ data set. In this case, the
   heavy tails in the data produce a high kurtosis (8.225), and cause the QQ
   plot to flatten in the middle, and curve away sharply on either side. The
   resulting Shapiro-Wilk statistic is *W* = 0.765, again reflecting a
   significant deviation from normality (*p* < 0.001).
   
.. ----------------------------------------------------------------------------

Shapiro-Wilk tests
~~~~~~~~~~~~~~~~~~

QQ plots provide a nice way to informally check the normality of your data, but
sometimes you will want to do something a bit more formal and the **Shapiro-Wilk
test** (:ref:`Shapiro & Wilk, 1965 <Shapiro_1965>`) is probably what you are
looking for.\ [#]_ As you would expect, the null hypothesis being tested is
that a set of *N* observations is normally distributed.\ [#]_

Because it is a little hard to explain the maths behind the *W* statistic, a
better idea is to give a general description of how it behaves. *Small* values
of *W* indicate departure from normality. The *W* statistic has a maximum value
of 1, which occurs when the data look “perfectly normal”. The smaller the value
of *W* the less normal the data are. However, the sampling distribution for *W*,
which is not one of the standard ones that I discussed in chapter
:doc:`../Ch07/Ch07_Probability`, does depend on the sample size *N*. To give
you a feel for what these sampling distributions look like, I have plotted
three of them in :numref:`fig11-sw`. Notice that, as the sample size starts to
get large, the sampling distribution becomes very tightly clumped up near
*W* = 1, and as a consequence, for larger samples *W* does not have to be very
much smaller than 1 in order for the test to be significant.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig11-sw.*
   :alt: Sampling distribution of the Shapiro-Wilk W statistic
   :name: fig11-sw

   Sampling distribution of the Shapiro-Wilk W statistic, under the null
   hypothesis that the data are normally-distributed, for samples of size 10,
   20 and 50. Note that small values of W indicate departure from normality.
   
.. ----------------------------------------------------------------------------

To get the Shapiro-Wilk statistic in jamovi *t*-tests, check the option for
``Normality`` listed under ``Assumptions``. In the randomly sampled data
(*N* = 100) we used for the QQ plot, the value for the Shapiro-Wilk normality
test statistic was W = 0.99 with a *p*-value of 0.54. So, not surprisingly, we
have no evidence that these data depart from normality. When reporting the
results for a Shapiro-Wilk test, you should (as usual) make sure to include the
test statistic *W* and the *p*-value, though given that the sampling
distribution depends so heavily on *N* it would probably be a politeness to
include *N* as well.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig11-22.*
   :alt: jamovi QQ plot for the independent *t*-test in :numref:`fig11-10`
   :name: fig11-22

   jamovi QQ plot for the independent *t*-test in :numref:`fig11-10`

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig11-23.*
   :alt: jamovi QQ plot for the paired *t*-test in :numref:`fig11-16`
   :name: fig11-23

   jamovi QQ plot for the paired *t*-test in :numref:`fig11-16`

.. ----------------------------------------------------------------------------

Example
~~~~~~~

In the meantime, it is probably worth showing you an example of what happens to
the QQ plot and the Shapiro-Wilk test when the data turn out to be non-normal.
For that, let us look at the distribution of our AFL winning margins variable
(``afl.margins`` from the |aflsmall_margins|_ data set), which if you remember
back to th chapter on :doc:`../Ch04/Ch04_Descriptives` did not look like they
came from a normal distribution at all. Here is what happens to the QQ plot:

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig11-24.*
   :alt: jamovi QQ plot for the data (skewed) data in the ``afl.margins``
         variable of the |aflsmall_margins| data set
   :name: fig11-24

   jamovi QQ plot for the (skewed) data in the ``afl.margins`` variable of the
   |aflsmall_margins|_ data set
   
.. ----------------------------------------------------------------------------

And when we run the Shapiro-Wilk test with the ``afl.margins`` variable, we get
a value for the Shapiro-Wilk normality test statistic of W = 0.94, and
*p*-value = 9.481e-07. Clearly a significant effect!

------

.. [#]
   This is a massive oversimplification.

.. [#]
   Either that, or the Kolmogorov-Smirnov test, which is probably more
   traditional than the Shapiro-Wilk. Although most things I have read seem to
   suggest Shapiro-Wilk is the better test of normality, the
   Kolomogorov-Smirnov is a general purpose test of distributional equivalence
   that can be adapted to handle other kinds of distribution tests. In jamovi
   the Shapiro-Wilk test is preferred.

.. [#]
   The test statistic that it calculates is conventionally denoted as *W*, and 
   it is calculated as follows. First, we sort the observations in order of 
   increasing size, and let *X*\ :sub:`1` be the smallest value in the sample, 
   *X*\ :sub:`2` be the second smallest and so on. Then the value of *W* is 
   given by:

   .. math:: W = \frac{ \left( \sum_{i = 1} ^ N a_i X_i \right) ^ 2 }{ \sum_{i = 1} ^ N (X_i - \bar{X}) ^ 2}

   *X̄* is the mean of the observations, and the *a*\ :sub:`i` values are 
   something complicated that is a bit beyond the scope of an introductory 
   text.

.. ----------------------------------------------------------------------------

.. |distributions|                     replace:: ``distributions``
.. _distributions:                     ../../_static/data/distributions.omv

.. |aflsmall_margins|                  replace:: ``aflsmall_margins``
.. _aflsmall_margins:                  ../../_static/data/aflsmall_margins.omv
