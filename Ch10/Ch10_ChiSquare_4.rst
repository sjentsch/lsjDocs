.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Effect size
-----------

As we discussed earlier in section :doc:`../Ch09/Ch09_HypothesisTesting_08`,
it is becoming commonplace to ask researchers to report some measure of effect
size. So, let us suppose that you have run your χ²-test, which turns out to be
significant. So you now know that there is some association between your
variables (independence test) or some deviation from the specified
probabilities (goodness-of-fit test). Now you want to report a measure of
effect size. That is, given that there is an association or deviation, how
strong is it?

There are several different measures that you can choose to report, and
several different tools that you can use to calculate them. I will not
discuss all of them but will instead focus on the most commonly reported
measures of effect size.

By default, the two measures that people tend to report most frequently
are the ϕ statistic and the somewhat superior version, known
as Cramér’s *V*.

Mathematically, they are very simple. To calculate the ϕ
statistic, you just divide your χ² value by the sample size,
and take the square root:

.. math:: \phi = \sqrt{\frac{\chi ^ 2}{N}}

The idea here is that the ϕ statistic is supposed to range between 0 (no
association at all) and 1 (perfect association), but it does not always do this
when your contingency table is bigger than 2 × 2, which is a total pain. For
bigger tables it is actually possible to obtain ϕ > 1, which is pretty
unsatisfactory. So, to correct for this, people usually prefer to report the
*V* statistic proposed by :ref:`Cramer (1946) <Cramer_1946>`. It is a pretty
simple adjustment to ϕ. If you have got a contingency table with *r* rows and
*c* columns, then define *k* = min(*r*, *c*) to be the smaller of the two
values. If so, then **Cramér’s V** statistic is:

.. math:: V = \sqrt{\frac{\chi ^ 2}{N(k - 1)}}

And you are done. This seems to be a fairly popular measure, presumably because
it is easy to calculate, and it gives answers that are not completely silly.
With Cramer’s V, you know that the value really does range from 0 (no
association at all) to 1 (perfect association).
