.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Effect size
-----------

The most commonly used measure of effect size for a *t*-test is **Cohen’s d**
(:ref:`Cohen, 1988 <Cohen_1988>`). It is a very simple measure in principle,
with quite a few wrinkles when you start digging into the details. Cohen
himself defined it primarily in the context of an independent samples
*t*-test, specifically the Student test. In that context, a natural way of
defining the effect size is to divide the difference between the means by an
estimate of the standard deviation. In other words, we are looking to calculate
*something* along the lines of this:

| d = (mean 1 - mean 2) / std. dev.

and he suggested a rough guide for interpreting *d* in
:numref:`tab-cohensdinterpretation`. You would think that this would be pretty
unambiguous, but it is not. This is largely because Cohen was not too specific
on what he thought should be used as the measure of the standard deviation
(in his defence he was trying to make a broader point in his book, not
nitpick about tiny details). As discussed by :ref:`McGrath and Meyer (2006)
<McGrath_2006>`, there are several different versions in common usage, and
each author tends to adopt slightly different notation. For the sake of
simplicity (as opposed to accuracy), I will use *d* to refer to any statistic
that you calculate from the sample, and use δ to refer to a theoretical
population effect. Obviously, that does mean that there are several different
things all called *d*.

My suspicion is that the only time that you would want Cohen’s *d* is when
you are running a *t*-test, and jamovi has an option to calculate the effect
size for all the different flavours of *t*-test it provides.

.. table::
   A (very) rough guide to interpreting Cohen’s *d*. My personal recommendation
   is to not use these blindly. The *d*-statistic has a natural interpretation
   in and of itself. It re-describes the difference in means as the number of
   standard deviations that separates those means. So it is generally a good
   idea to think about what that means in practical terms. In some contexts a
   “small” effect could be of big practical importance. In other situations a
   “large” effect may not be all that interesting.
   :name: tab-cohensdinterpretation

   +-----------+----------------------+
   | *d*-value | rough interpretation |
   +===========+======================+
   | about 0.2 |       “small” effect |
   +-----------+----------------------+
   | about 0.5 |    “moderate” effect |
   +-----------+----------------------+
   | about 0.8 |       “large” effect |
   +-----------+----------------------+

Cohen’s *d* from one sample
~~~~~~~~~~~~~~~~~~~~~~~~~~~

The simplest situation to consider is the one corresponding to a one-sample
*t*-test. In this case, this is the one sample mean *X̄* and one (hypothesised)
population mean µ\ :sub:`o` to compare it to. Not only that, there is really
only one sensible way to estimate the population standard deviation. We just
use our usual estimate :math:`\hat{\sigma}`. Therefore, we end up with the
following as the only way to calculate d:

.. math:: d = \frac{\bar{X} - \mu_0}{\hat{\sigma}}

When we look back at the results in :numref:`fig11-6`, the effect size value is
Cohen’s *d* = 0.50. Overall, then, the psychology students in Dr Zeppo’s class
are achieving grades (mean = 72.3\%) that are about 0.5 standard deviations
higher than the level that you would expect (67.5\%) if they were performing at
the same level as other students. Judged against Cohen’s rough guide, this is a
moderate effect size.

Cohen’s *d* from a Student’s *t*-test
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The majority of discussions of Cohen’s *d* focus on a situation that is
analogous to Student’s independent samples *t*-test, and it is in this context
that the story becomes messier, since there are several different versions of
*d* that you might want to use in this situation. To understand why there are
multiple versions of *d*, it helps to take the time to write down a formula
that corresponds to the true population effect size δ. It is pretty
straightforward:

| δ = (µ\ :sub:`1` - µ\ :sub:`2`) / σ.

As usual, µ\ :sub:`1` and µ\ :sub:`2` are the population means corresponding
to group 1 and group 2 respectively, and σ is the standard deviation (the same
for both populations). The obvious way to estimate δ is to do exactly the same
thing that we did in the *t*-test itself, i.e., use the sample means as the
top line and a pooled standard deviation estimate for the bottom line:

.. math:: d = \frac{\bar{X}_1 - \bar{X}_2}{\hat{\sigma}_p}

where :math:`\hat\sigma_p` is the exact same pooled standard deviation
measure that appears in the *t*-test. This is the most commonly used version
of Cohen’s *d* when applied to the outcome of a Student *t*-test, and is the
one provided in jamovi. It is sometimes referred to as Hedges’ *g* statistic
(:ref:`Hedges, 1981 <Hedges_1981>`).

However, there are other possibilities which I will briefly describe. Firstly,
you may have reason to want to use only one of the two groups as the basis
for calculating the standard deviation. This approach (often called Glass’
*Δ*, pronounced *delta*) only makes most sense when you have good reason to
treat one of the two groups as a purer reflection of “natural variation” than
the other. This can happen if, for instance, one of the two groups is a
control group. Secondly, recall that in the usual calculation of the pooled
standard deviation we divide by *N* - 2 to correct for the bias in the sample
variance. In one version of Cohen’s *d* this correction is omitted, and
instead we divide by *N*. This version makes sense primarily when you are
trying to calculate the effect size in the sample rather than estimating an
effect size in the population. Finally, there is a version based on
:ref:`Hedges and Olkin (1985) <Hedges_1985>`, who point out there is a small
bias in the usual (pooled) estimation for Cohen’s *d*. Thus they introduce a
small correction by multiplying the usual value of *d* by (*N* - 3) /
(*N* - 2.25).

In any case, ignoring all those variations that you could make use of if you
wanted, let us have a look at the default version in jamovi. In
:numref:`fig11-9` Cohen’s *d* = 0.74, indicating that the grade scores
for students in Anastasia’s class are, on average, 0.74 standard deviations
higher than the grade scores for students in Bernadette’s class. For a
Welch-test, the estimated effect size is the same (:numref:`fig11-11`).

Cohen’s *d* from a paired-samples test
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Finally, what should we do for a paired samples *t*-test? In this case, the
answer depends on what it is you are trying to do. jamovi assumes that you want
to measure your effect sizes relative to the distribution of difference scores,
and the measure of *d* that you calculate is:

.. math:: d = \frac{\bar{D}}{\hat{\sigma}_D}

:math:`\hat{\sigma}_D` is the estimate of the standard deviation of the
differences. In :numref:`fig11-16` Cohen’s *d* = 1.45, indicating that the time
2 grade scores are, on average, 1.45 standard deviations higher than the time 1
grade scores.

This is the version of Cohen’s *d* that gets reported by the jamovi ``Paired
Samples T-Test`` analysis. The only wrinkle is figuring out whether this is the
measure you want or not. To the extent that you care about the practical
consequences of your research, you often want to measure the effect size
relative to the *original* variables, not the *difference* scores (e.g., the
\1\% improvement in Dr Chico’s class over time is pretty small when measured
against the amount of between-student variation in grades), in which case you
use the same versions of Cohen’s *d* that you would use for a Student or Welch
test. It is not so straightforward to do this in jamovi; essentially you have
to change the structure of the data in the spreadsheet view so I will not go
into that here,\ [#]_ but the Cohen’s *d* for this perspective is quite
different: it is 0.22 which is quite small when assessed on the scale of the
original variables.

------

.. [#]
   If you are interested, you can look at how this was done in the |chico2|_
   data set

.. ----------------------------------------------------------------------------

.. |chico2|                            replace:: ``chico2``
.. _chico2:                            ../../_static/data/chico2.omv
