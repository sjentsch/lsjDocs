.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Other useful distributions
--------------------------

The normal distribution is the distribution that statistics makes most use of
(for reasons to be discussed shortly), and the binomial distribution is a very
useful one for lots of purposes. But the world of statistics is filled with
probability distributions, some of which we’ll run into in passing. In
particular, the three that will appear in this book are the *t* distribution,
the *χ²*-distribution and the *F*-distribution. I won’t give formulas for any
of these, or talk about them in too much detail, but I will show you some
pictures.

-  The **t-distribution** is a continuous distribution that looks very similar
   to a normal distribution, see :numref:`fig-tdist`. Note that the “tails” of
   the *t*-distribution are “heavier” (i.e., extend further outwards) than the
   tails of the normal distribution). That’s the important difference between
   the two. This distribution tends to arise in situations where you think that
   the data actually follow a normal distribution, but you don’t know the mean
   or standard deviation. We’ll run into this distribution again in Chapter 
   `Comparing two means <Ch11_tTest.html#comparing-two-means>`__.
   
.. ----------------------------------------------------------------------------

.. _fig-tDist:
.. figure:: ../_images/lsj_tDist.*
   :alt: t-distribution with df = 3 in comparison to a normal distribution

   t-distribution with 3 degrees of freedom (solid line). It looks similar to a
   normal distribution, but it’s not quite the same. For comparison purposes
   I’ve plotted a standard normal distribution as the dashed line.

.. ----------------------------------------------------------------------------

-  The **χ²-distribution** is another distribution that turns up in lots of
   different places. The situation in which we’ll see it is when doing
   `Categorical data analysis <Ch10_ChiSquare.html#categorical-data-analysis>`__,
   but it’s one of those things that actually pops up all over the place. When
   you dig into the maths (and who doesn’t love doing that?), it turns out that
   the main reason why the *χ²*-distribution turns up all over the place is
   that if you have a bunch of variables that are normally distributed, square
   their values and then add them up (a procedure referred to as taking a “sum
   of squares”), this sum has a *χ²*-distribution. You’d be amazed how often
   this fact turns out to be useful. Anyway, here’s what a χ²-distribution
   looks like: :numref:`fig-chiSqDist`.
   
.. ----------------------------------------------------------------------------

.. _fig-chiSqDist:
.. figure:: ../_images/lsj_chiSqDist.*
   :alt: χ²-distribution with with df = 3

   χ²-distribution with 3 degrees of freedom. Notice that the observed values
   must always be greater than zero, and that the distribution is pretty
   skewed. These are the key features of a χ²-distribution.

.. ----------------------------------------------------------------------------

-  The **F-distribution** looks a bit like a *χ²*-distribution, and it arises
   whenever you need to compare two *χ²*-distributions to one another. 
   Admittedly, this doesn’t exactly sound like something that any sane person
   would want to do, but it turns out to be very important in real world data
   analysis. Remember when I said that *χ²* turns out to be the key
   distribution when we’re taking a “sum of squares”? Well, what that means is
   if you want to compare two different “sums of squares”, you’re probably
   talking about something that has an *F*-distribution. Of course, as yet I
   still haven’t given you an example of anything that involves a sum of
   squares, but I will in Chapter `Comparing several means (one-way ANOVA)
   <Ch13_ANOVA.html#comparing-several-means-one-way-anova>`__. And that’s where
   we’ll run into the *F*-distribution. Oh, and there’s a picture in
   :numref:`fig-Fdist`.
   
.. ----------------------------------------------------------------------------

.. _fig-FDist:
.. figure:: ../_images/lsj_FDist.*
   :alt: F-distribution with df = 3 and df = 5

   F-distribution with 3 and 5 degrees of freedom. Qualitatively speaking, it
   looks pretty similar to a χ²-distribution, but they’re not quite the same in
   general.
   
.. ----------------------------------------------------------------------------

Okay, time to wrap this section up. We’ve seen three new distributions: *χ²*,
*t* and *F*. They’re all continuous distributions, and they’re all closely
related to the normal distribution. The main thing for our purposes is that you
grasp the basic idea that these distributions are all deeply related to one
another, and to the normal distribution. Later on in this book we’re going to
run into data that are normally distributed, or at least assumed to be normally
distributed. What I want you to understand right now is that, if you make the
assumption that your data are normally distributed, you shouldn’t be surprised
to see *χ²*-, *t*-and *F*-distributions popping up all over the place when you
start trying to do your data analysis.
