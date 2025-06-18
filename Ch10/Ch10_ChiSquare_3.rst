.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

The continuity correction
-------------------------

Okay, time for a little bit of a digression. I have been lying to you a
little bit so far. There is a tiny change that you need to make to your
calculations whenever you only have 1 degree of freedom. It is called the
“continuity correction”, or sometimes the **Yates correction**. Remember
what I pointed out earlier: the χ² test is based on an
approximation, specifically on the assumption that the binomial
distribution starts to look like a normal distribution for large
*N*. One problem with this is that it often does not quite work,
especially when you have only got 1 degree of freedom (e.g., when you are
doing a test of independence on a 2 × 2 contingency table).
The main reason for this is that the true sampling distribution for the
χ²-statistic is actually discrete (because you are dealing with
categorical data!) but the χ² distribution is continuous.
This can introduce systematic problems. Specifically, when *N* is
small and when *df* = 1, the goodness-of-fit statistic tends to be
“too big”, meaning that you actually have a bigger α value
than you think (or, equivalently, the *p*-values are a bit too
small).

:ref:`Yates (1934) <Yates_1934>` suggested a simple fix, in which you redefine
the goodness-of-fit statistic as:

.. math:: \chi^2 = \sum_{i} \frac{(|E_i - O_i| - 0.5)^2}{E_i}

Basically, he just subtracts off 0.5 everywhere.

As far as I can tell from reading Yates’ paper, the correction is
basically a hack. It is not derived from any principled theory. Rather,
it is based on an examination of the behaviour of the test, and observing
that the corrected version seems to work better. You can specify this
correction in jamovi from a check box in the ``Statistics`` options, where
it is called ``χ² continuity correction``.
