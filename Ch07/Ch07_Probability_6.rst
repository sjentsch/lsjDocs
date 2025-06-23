.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Other useful distributions
--------------------------

The normal distribution is the distribution that statistics makes most use of
(for reasons to be discussed shortly), and the binomial distribution is a very
useful one for lots of purposes. But the world of statistics is filled with
probability distributions, some of which we will run into in passing. In
particular, the three that will appear in this book are the *t*-distribution,
the χ²-distribution and the *F*-distribution. I will not give formulas for any
of these, or talk about them in too much detail, but I will show you some
pictures.

-  The **t-distribution** is a continuous distribution that looks very similar
   to a normal distribution, see :numref:`fig7-10`. Note that the “tails” of
   the *t*-distribution are “heavier” (i.e., extend further outwards) than the
   tails of the normal distribution). That is the important difference between
   the two. This distribution tends to arise in situations where you think that
   the data actually follow a normal distribution, but you do not know the mean
   or standard deviation. We will run into this distribution again in chapter 
   :doc:`../Ch11/Ch11_tTest`.
   
.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig7-10.*
   :alt: *t*-distribution with *df* = 3 in comparison to a normal distribution
   :name: fig7-10

   *t*-distribution with 3 degrees of freedom (solid line). It looks similar to
   a normal distribution, but it is not quite the same. For comparison purposes
   I have plotted a standard normal distribution as the dashed line.

.. ----------------------------------------------------------------------------

-  The **χ²-distribution** is another distribution that turns up in lots of
   different places. The situation in which we will see it is when doing
   :doc:`../Ch10/Ch10_ChiSquare`, but it is one of those things that actually
   pops up all over the place. When you dig into the maths (and who does not
   love doing that?), it turns out that the main reason why the χ²-distribution
   turns up all over the place is that if you have a bunch of variables that
   are normally distributed, square their values and then add them up (a
   procedure referred to as taking a “sum of squares”), this sum has a
   χ²-distribution. You would be amazed how often this fact turns out to be
   useful. Anyway, :numref:`fig7-11` illustrates what a χ²-distribution looks 
   like.
   
.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig7-11.*
   :alt: χ²-distribution with *df* = 3
   :name: fig7-11

   χ²-distribution with 3 degrees of freedom. Notice that the observed values 
   must always be greater than zero, and that the distribution is pretty 
   skewed. These are the key features of a χ²-distribution.

.. ----------------------------------------------------------------------------

-  The **F-distribution** looks a bit like a χ²-distribution, and it arises
   whenever you need to compare two χ²-distributions to one another. 
   Admittedly, this does not exactly sound like something that any sane person
   would want to do, but it turns out to be very important in real-world data
   analysis. Remember when I said that χ² turns out to be the key distribution
   when we are taking a “sum of squares”? Well, what that means is if you want
   to compare two different “sums of squares”, you are probably talking about
   something that has an *F*-distribution. Of course, as yet I still have not
   given you an example of anything that involves a sum of squares, but I will
   in chapter :doc:`../Ch13/Ch13_ANOVA`. And that is where we will run into the
   *F*-distribution. Oh, and there is a picture in :numref:`fig7-12`.
   
.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig7-12.*
   :alt: *F*-distribution with *df* = 3 and *df* = 5
   :name: fig7-12

   *F*-distribution with 3 and 5 degrees of freedom. Qualitatively speaking, it
   looks pretty similar to a χ²-distribution, but they are not quite the
   same in general.
   
.. ----------------------------------------------------------------------------

Okay, time to wrap this section up. We have seen three new distributions: *t*,
χ² and *F*. They are all continuous distributions, and they are all closely
related to the normal distribution. The main thing for our purposes is that you
grasp the basic idea that these distributions are all deeply related to one
another, and to the normal distribution. Later on in this book we are going to
run into data that are normally distributed, or at least assumed to be normally
distributed. What I want you to understand right now is that, if you make the
assumption that your data are normally distributed, you should not be surprised
to see *t*-, χ²- and *F*-distributions popping up all over the place when you
start trying to do your data analysis.
