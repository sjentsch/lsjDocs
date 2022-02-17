.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Making decisions
----------------

Okay, we’re very close to being finished. We’ve constructed a test
statistic (*X*) and we chose this test statistic in such a way
that we’re pretty confident that if *X* is close to *N* / 2
then we should retain the null, and if not we should reject it. The
question that remains is this. Exactly which values of the test
statistic should we associate with the null hypothesis, and exactly
which values go with the alternative hypothesis? In my ESP study, for
example, I’ve observed a value of *X* = 62. What decision should I
make? Should I choose to believe the null hypothesis or the alternative
hypothesis?

Critical regions and critical values
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To answer this question we need to introduce the concept of a **critical
region** for the test statistic *X*. The critical region of the
test corresponds to those values of *X* that would lead us to
reject null hypothesis (which is why the critical region is also
sometimes called the rejection region). How do we find this critical
region? Well, let’s consider what we know:

-  *X* should be very big or very small in order to reject the
   null hypothesis.

-  If the null hypothesis is true, the sampling distribution of
   *X* is Binomial(0.5, N).

-  If *α* = 0.05, the critical region must cover 5% of this
   sampling distribution.

It’s important to make sure you understand this last point. The critical
region corresponds to those values of *X* for which we would
reject the null hypothesis, and the sampling distribution in question
describes the probability that we would obtain a particular value of
*X* if the null hypothesis were actually true. Now, let’s suppose
that we chose a critical region that covers 20% of the sampling
distribution, and suppose that the null hypothesis is actually true.
What would be the probability of incorrectly rejecting the null? The
answer is of course 20%. And, therefore, we would have built a test that
had an *α* level of 0.2. If we want
*α* = 0.05, the critical region is only *allowed* to cover 5%
of the sampling distribution of our test statistic.

.. ----------------------------------------------------------------------------

.. _fig-rejectionRegion1:
.. figure:: ../_images/lsj_rejectionRegion1.*
   :alt: Critical region associated with a two-sided test

   The critical region associated with the hypothesis test for the ESP study,
   for a hypothesis test with a significance level of α = 0.05. The plot shows
   the sampling distribution of X under the null hypothesis (i.e., same as 
   :numref:`fig-samplingDist`). The grey bars correspond to those values of X
   for which we would retain the null hypothesis. The blue (darker shaded) bars
   show the critical region, those values of X for which we would reject the
   null. Because the alternative hypothesis is two-sided (i.e., allows both
   θ < 0.5 and θ > 0.5), the critical region covers both tails of the
   distribution. To ensure an α level of 0.05, we need to ensure that each of
   the two regions encompasses 2.5% of the sampling distribution.
   
.. ----------------------------------------------------------------------------

As it turns out those three things uniquely solve the problem. Our critical
region consists of the most *extreme values*, known as the **tails** of the
distribution. This is illustrated in :numref:`fig-rejectionRegion1`. If we
want *α* = 0.05 then our critical regions correspond to *X* ≤ 40` and
*X* ≥ 60.\ [#]_ That is, if the number of people saying “true” is between 41
and 59, then we should retain the null hypothesis. If the number is between 0
to 40, or between 60 to 100, then we should reject the null hypothesis. The
numbers 40 and 60 are often referred to as the **critical values** since they
define the edges of the critical region.

At this point, our hypothesis test is essentially complete:

#. (1) we choose an *α* level (e.g., *α* = 0.05;

#. (2) come up with some test statistic (e.g., *X*) that does a
   good job (in some meaningful sense) of comparing H\ :sub:`0` to
   H\ :sub:`1`;

#. (3) figure out the sampling distribution of the test statistic on the
   assumption that the null hypothesis is true (in this case, binomial);
   and then

#. (4) calculate the critical region that produces an appropriate
   *α* level (0-40 and 60-100).

All that we have to do now is calculate the value of the test statistic
for the real data (e.g., *X* = 62) and then compare it to the
critical values to make our decision. Since 62 is greater than the
critical value of 60 we would reject the null hypothesis. Or, to phrase
it slightly differently, we say that the test has produced a
statistically **significant** result.

A note on statistical “significance”
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. epigraph::

   | *Like other occult techniques of divination, the statistical method
     has a private jargon deliberately contrived to obscure its methods
     from non-practitioners.*
     
   -- Attributed to G. O. Ashley\ [#]_

A very brief digression is in order at this point, regarding the word
“significant”. The concept of statistical significance is actually a
very simple one, but has a very unfortunate name. If the data allow us
to reject the null hypothesis, we say that “the result is *statistically
significant*”, which is often shortened to “the result is significant”.
This terminology is rather old and dates back to a time when
“significant” just meant something like “indicated”, rather than its
modern meaning which is much closer to “important”. As a result, a lot
of modern readers get very confused when they start learning statistics
because they think that a “significant result” must be an important one.
It doesn’t mean that at all. All that “statistically significant” means
is that the data allowed us to reject a null hypothesis. Whether or not
the result is actually important in the real world is a very different
question, and depends on all sorts of other things.

The difference between one-sided and two-sided tests
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

There’s one more thing I want to point out about the hypothesis test
that I’ve just constructed. If we take a moment to think about the
statistical hypotheses I’ve been using,

H\ :sub:`0`: *θ* = 0.5

H\ :sub:`1`: *θ* ≠ 0.5 

we notice that the alternative hypothesis covers *both* the possibility
that *θ* < 0.5 and the possibility that *θ* > 0.5.
This makes sense if I really think that ESP could produce either
better-than-chance performance *or* worse-than-chance performance (and
there are some people who think that). In statistical language this is
an example of a **two-sided test**. It’s called this because the
alternative hypothesis covers the area on both “sides” of the null
hypothesis, and as a consequence the critical region of the test covers
both tails of the sampling distribution (2.5% on either side if
*α* = 0.05), as illustrated earlier in :numref:`fig-rejectionRegion1`.

However, that’s not the only possibility. I might only be willing to
believe in ESP if it produces better than chance performance. If so,
then my alternative hypothesis would only covers the possibility that
*θ* > 0.5, and as a consequence the null hypothesis now
becomes *θ* ≤ 0.5

H\ :sub:`1`: *θ* ≤ 0.5

H\ :sub:`1`: *θ* > 0.5 

When this happens, we have what’s called a **one-sided test** and the
critical region only covers one tail of the sampling distribution. This
is illustrated in :numref:`fig-rejectionRegion2`.

.. ----------------------------------------------------------------------------

.. _fig-rejectionRegion2:
.. figure:: ../_images/lsj_rejectionRegion2.*
   :alt: Critical region associated with a one-sided test

   The critical region for a one-sided test. In this case, the alternative
   hypothesis is that θ = 0.5 so we would only reject the null hypothesis for
   large values of X. As a consequence, the critical region only covers the
   upper tail of the sampling distribution, specifically the upper 5% of the
   distribution. Contrast this to the two-sided version in
   :numref:`fig-rejectionRegion1`.
   
.. ----------------------------------------------------------------------------

------

.. [#]
   Strictly speaking, the test I just constructed has
   *α* = 0.057, which is a bit too generous. However, if I’d
   chosen 39 and 61 to be the boundaries for the critical region then
   the critical region only covers 3.5% of the distribution. I figured
   that it makes more sense to use 40 and 60 as my critical values, and
   be willing to tolerate a 5.7% type I error rate, since that’s as
   close as I can get to a value of *α* = 0.05.

.. [#]
   The internet seems fairly convinced that Ashley said this, though I
   can’t for the life of me find anyone willing to give a source for the
   claim.
