.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Estimating population parameters
--------------------------------

In all the IQ examples in the previous sections we actually knew the
population parameters ahead of time. As every undergraduate gets taught
in their very first lecture on the measurement of intelligence, IQ
scores are *defined* to have mean 100 and standard deviation 15.
However, this is a bit of a lie. How do we know that IQ scores have a
true population mean of 100? Well, we know this because the people who
designed the tests have administered them to very large samples, and
have then “rigged” the scoring rules so that their sample has mean 100.
That is not a bad thing of course, it is an important part of designing a
psychological measurement. However, it is important to keep in mind that
this theoretical mean of 100 only attaches to the population that the
test designers used to design the tests. Good test designers will
actually go to some lengths to provide “test norms” that can apply to
lots of different populations (e.g., different age groups, nationalities
etc).

This is very handy, but of course almost every research project of
interest involves looking at a different population of people to those
used in the test norms. For instance, suppose you wanted to measure the
effect of low level lead poisoning on cognitive functioning in Port
Pirie, a South Australian industrial town with a lead smelter. Perhaps
you decide that you want to compare IQ scores among people in Port Pirie
to a comparable sample in Whyalla, a South Australian industrial town
with a steel refinery.\ [#]_ Regardless of which town you are thinking
about, it does not make a lot of sense simply to *assume* that the true
population mean IQ is 100. No-one has, to my knowledge, produced
sensible norming data that can automatically be applied to South
Australian industrial towns. We are going to have to **estimate** the
population parameters from a sample of data. So how do we do this?

Estimating the population mean
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Suppose we go to Port Pirie and 100 of the locals are kind enough to sit
through an IQ test. The average IQ score among these people turns out to be
*X̄* = 98.5. So what is the true mean IQ for the entire population of Port
Pirie? Obviously, we do not know the answer to that question. It could be 97.2,
but it could also be 103.5. Our sampling is not exhaustive so we cannot give a
definitive answer. Nevertheless, if I was forced at gunpoint to give a “best
guess” I would have to say 98.5. That is the essence of statistical estimation:
giving a best guess.

In this example estimating the unknown poulation parameter is straightforward.
I calculate the sample mean and I use that as my **estimate of the population
mean**. It is pretty simple, and in the next section I will explain the
statistical justification for this intuitive answer. However, for the moment
what I want to do is make sure you recognise that the sample statistic and the
estimate of the population parameter are conceptually different things. A
sample statistic is a description of your data, whereas the estimate is a guess
about the population. With that in mind, statisticians often different notation
to refer to them. For instance, if the true population mean is denoted µ,
then we would use :math:`\hat\mu` to refer to our estimate of the population
mean. In contrast, the sample mean is denoted *X̄* or sometimes *m* or *M*.
However, in simple random samples the estimate of the population mean is
identical to the sample mean. If I observe a sample mean of *X̄* = 98.5 then my
estimate of the population mean is also :math:`\hat\mu` = 98.5. To help keep
the notation clear, here is a handy table:

.. list-table::
   :header-rows: 1

   * - Symbol
     - What is it?
     - Do we know what it is?
   * - *X̄*
     - Sample mean
     - Yes, calculated from the raw data
   * - µ
     - True population mean
     - Almost never known for sure
   * - :math:`\hat{\mu}`
     - Estimate of the population mean
     - Yes, identical to the sample mean in simple random samples


Estimating the population standard deviation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

So far, estimation seems pretty simple, and you might be wondering why I forced
you to read through all that stuff about sampling theory. In the case of the
mean our estimate of the population parameter (i.e. :math:`\hat\mu`) turned out
to be identical to the corresponding sample statistic (i.e. *X̄*). However,
that is not always true. To see this, let us have a think about how to construct
an **estimate of the population standard deviation**, which we will denote
:math:`\hat\sigma`. What shall we use as our estimate in this case? Your first
thought might be that we could do the same thing we did when estimating the
mean, and just use the sample statistic as our estimate. That is almost the
right thing to do, but not quite.

Here is why. Suppose I have a sample that contains a single observation. For
this example, it helps to consider a sample where you have no intuitions at all
about what the true population values might be, so let us use something
completely fictitious. Suppose the observation in question measures the
*cromulence* of my shoes. It turns out that my shoes have a cromulence of 20.
So here is my sample:

``20``

This is a perfectly legitimate sample, even if it does have a sample
size of *N* = 1. It has a sample mean of 20 and because every
observation in this sample is equal to the sample mean (obviously!) it
has a sample standard deviation of 0. As a description of the *sample*
this seems quite right, the sample contains a single observation and
therefore there is no variation observed within the sample. A sample
standard deviation of *s* = 0 is the right answer here. But as an
estimate of the *population* standard deviation it feels completely
insane, right? Admittedly, you and I do not know anything at all about
what “cromulence” is, but we know something about data. The only reason
that we do not see any variability in the *sample* is that the sample is
too small to display any variation! So, if you have a sample size of
*N* = 1 it *feels* like the right answer is just to say “no idea at all”.

Notice that you *do not* have the same intuition when it comes to the
sample mean and the population mean. If forced to make a best guess
about the population mean it does not feel completely insane to guess
that the population mean is 20. Sure, you probably would not feel very
confident in that guess because you have only the one observation to
work with, but it is still the best guess you can make.

Let us extend this example a little. Suppose I now make a second
observation. My data set now has *N* = 2 observations of the
cromulence of shoes, and the complete sample now looks like this:

``20, 22``

This time around, our sample is *just* large enough for us to be able to 
observe some variability: two observations is the bare minimum number needed
for any variability to be observed! For our new data set, the sample mean is
*X̄* = 21, and the sample standard deviation is *s* = 1. What intuitions do we
have about the population? Again, as far as the population mean goes, the best
guess we can possibly make is the sample mean. If forced to guess we would probably
guess that the population mean cromulence is 21. What about the standard
deviation? This is a little more complicated. The sample standard deviation is
only based on two observations, and if you are at all like me you probably have
the intuition that, with only two observations we have not given the population
“enough of a chance” to reveal its true variability to us. It is not just that
we suspect that the estimate is *wrong*, after all with only two observations
we expect it to be wrong to some degree. The worry is that the error is
*systematic*. Specifically, we suspect that the sample standard deviation is
likely to be smaller than the population standard deviation.

This intuition feels right, but it would be nice to demonstrate this somehow.
There are in fact mathematical proofs that confirm this intuition, but unless
you have the right mathematical background they do not help very much. Instead,
what I will do is simulate the results of some experiments. With that in mind,
let us return to our IQ studies. Suppose the true population mean IQ is 100 and
the standard deviation is 15. First I will conduct an experiment in which I
measure *N* = 2 IQ scores and I will calculate the sample standard deviation.
If I do this over and over again, and plot a histogram of these sample standard
deviations, what I have is the *sampling distribution of the standard
deviation*. I have plotted this distribution in 
:numref:`fig-samplingDistSampleSD`. Even though the true population standard
deviation is 15 the average of the *sample* standard deviations is only 8.5.
Notice that this is a very different result to what we found in 
:numref:`fig-samplingDistDiffN` (middle panel) when we plotted the sampling
distribution of the mean, where the population mean is 100 and the average of
the sample means is also 100.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_samplingDistSampleSD.*
   :alt: Sampling distrib. of the std. dev. for a “two IQ scores” experiment
   :name: fig-samplingDistSampleSD

   Sampling distribution of the sample standard deviation for a “two IQ
   scores” experiment. The true population standard deviation is 15 (dashed
   line), but as you can see from the histogram the vast majority of
   experiments will produce a much smaller sample standard deviation than this.
   On average, this experiment would produce a sample standard deviation of
   only 8.5, well below the true value! In other words, the sample standard
   deviation is a biased estimate of the population standard deviation.
   
.. ----------------------------------------------------------------------------

Now let us extend the simulation. Instead of restricting ourselves to the
situation where *N* = 2, let us repeat the exercise for sample sizes
from 1 to 10. If we plot the average sample mean and average sample
standard deviation as a function of sample size, you get the results
shown in :numref:`fig-biasMeanSD`. On the left hand side I have plotted the
average sample mean and on the right hand side I have plotted the average
standard deviation. The two plots are quite different: *on average*, the
average sample mean is equal to the population mean. It is an **unbiased
estimator**, which is essentially the reason why your best estimate for the
population mean is the sample mean.\ [#]_ The plot on the right is quite
different: on average, the sample standard deviation *s* is *smaller* than
the population standard deviation σ. It is a **biased estimator**. In other
words, if we want to make a “best guess” :math:`\hat\sigma` about the value
of the population standard deviation σ we should make sure our guess is a
little bit larger than the sample standard deviation *s*.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_biasMeanSD.*
   :alt: Sample size: Mean (un-biased) and standard deviation (biased)
   :name: fig-biasMeanSD

   Illustration of the fact that the sample mean is an unbiased estimator of
   the population mean (left panel), but the sample standard deviation is a
   biased estimator of the population standard deviation (right panel). For
   the figure, I generated 10,000 simulated data sets with one observation
   each, 10,000 more with two observations, and so on up to a sample size of
   \10. Each data set consisted of fake IQ data, that is the data were normally
   distributed with a true population mean of 100 and standard deviation 15.
   On average, the sample means turn out to be 100, regardless of sample size
   (left panel). However, the sample standard deviations turn out to be
   systematically too small (right panel), especially for small sample sizes.
   
.. ----------------------------------------------------------------------------

The fix to this systematic bias turns out to be very simple. Here is how it
works. Before tackling the standard deviation let us look at the variance. If
you recall from :doc:`../Ch04/Ch04_Descriptives_2`, the sample variance is
defined to be the average of the squared deviations from the sample mean. That
is:

.. math:: s^2 = \frac{1}{N} \sum_{i=1}^N (X_i - \bar{X})^2

The sample variance *s*\² is a biased estimator of the population variance 
σ². But as it turns out, we only need to make a tiny tweak to transform this
into an unbiased estimator. All we have to do is divide by *N* - 1 rather than
by *N*. If we do that, we obtain the following formula:

.. math:: \hat\sigma^2 = \frac{1}{N-1} \sum_{i=1}^N (X_i - \bar{X})^2

This is an unbiased estimator of the population variance σ². Moreover, this
finally answers the question we raised in :doc:`../Ch04/Ch04_Descriptives_2`.
Why did jamovi give us slightly different answers for variance? It is because
jamovi calculates :math:`\hat\sigma^2` not *s*\², that is why. A similar story
applies for the standard deviation. If we divide by *N* - 1 rather than *N*
our estimate of the population standard deviation becomes:

.. math:: \hat\sigma = \sqrt{\frac{1}{N-1} \sum_{i=1}^N (X_i - \bar{X})^2}

and when we use jamovi’s built in standard deviation function, what it is
doing is calculating :math:`\hat\sigma`, not *s*.\ [#]_

One final point. In practice, a lot of people tend to refer to
:math:`\hat{\sigma}` (i.e., the formula where we divide by *N* - 1)
as the *sample* standard deviation. Technically, this is incorrect. The
*sample* standard deviation should be equal to *s* (i.e., the formula where
we divide by *N*). These are not the same thing, either conceptually or
numerically. One is a property of the sample, the other is an estimated
characteristic of the population. However, in almost every real life
application what we actually care about is the estimate of the population
parameter, and so people always report :math:`\hat\sigma` rather than *s*.
This is the right number to report, of course. It is just that people tend to
get a little bit imprecise about terminology when they write it up, because
“sample standard deviation” is shorter than “estimated population standard
deviation”. It is no big deal, and in practice I do the same thing
everyone else does. Nevertheless, I think it is important to keep the two
*concepts* separate. It is never a good idea to confuse “known properties
of your sample” with “guesses about the population from which it came”.
The moment you start thinking that *s* and :math:`\hat\sigma` are
the same thing, you start doing exactly that.

To finish this section off, here is another couple of tables to help keep
things clear.

+------------------------+----------------------+------------------------+
| Symbol                 | What is it?          | Do we know what it is? |
+========================+======================+========================+
| *s*                    | Sample standard      | Yes, calculated from   |
|                        | deviation            | the raw data           |
+------------------------+----------------------+------------------------+
| σ                      | Population standard  | Almost never known for |
|                        | deviation            | sure                   |
+------------------------+----------------------+------------------------+
| :math:`\hat{\sigma}`   | Estimate of the      | Yes, but not the same  |
|                        | population standard  | as the sample standard |
|                        | deviation            | deviation              |
+------------------------+----------------------+------------------------+
+------------------------+----------------------+------------------------+
| *s*\²                  | Sample variance      | Yes, calculated from   |
|                        |                      | the raw data           |
+------------------------+----------------------+------------------------+
| σ²                     | Population variance  | Almost never known for |
|                        |                      | sure                   |
+------------------------+----------------------+------------------------+
| :math:`\hat{\sigma}^2` | Estimate of the      | Yes, but not the same  |
|                        | population variance  | as the sample variance |
+------------------------+----------------------+------------------------+

------

.. [#]
   Please note that if you were *actually* interested in this question you
   would need to be a *lot* more careful than I am being here. You *can not* just
   compare IQ scores in Whyalla to Port Pirie and assume that any differences
   are due to lead poisoning. Even if it were true that the only differences
   between the two towns corresponded to the different refineries (and it
   is not, not by a long shot), you need to account for the fact that people
   already *believe* that lead pollution causes cognitive deficits. If you
   recall back to chapter :doc:`../Ch02/Ch02_StudyDesign`, this means that
   there are different demand characteristics for the Port Pirie sample than 
   for the Whyalla sample. In other words, you might end up with an illusory
   group difference in your data, caused by the fact that people *think* that
   there is a real difference. I find it pretty implausible to think that the
   locals would not be well aware of what you were trying to do if a bunch of
   researchers turned up in Port Pirie with lab coats and IQ tests, and even
   less plausible to think that a lot of people would be pretty resentful of
   you for doing it. Those people will not be as co-operative in the tests. Other
   people in Port Pirie might be *more* motivated to do well because they
   do not want their home town to look bad. The motivational effects that would
   apply in Whyalla are likely to be weaker, because people do not have any
   concept of “iron ore poisoning” in the same way that they have a concept
   for “lead poisoning”. Psychology is *hard*.

.. [#]
   I should note that I am hiding something here. Unbiasedness is a
   desirable characteristic for an estimator, but there are other things
   that matter besides bias. However, it is beyond the scope of this book
   to discuss this in any detail. I just want to draw your attention to
   the fact that there is some hidden complexity here.

.. [#]
   Okay, I am hiding something else here. In a bizarre and counter-intuitive
   twist, since :math:`\hat\sigma^2` is an unbiased estimator of σ², you would
   assume that taking the square root would be fine and :math:`\hat\sigma`
   would be an unbiased estimator of σ. Right? Weirdly, it is not. There is
   actually a subtle, tiny bias in :math:`\hat\sigma`. This is just bizarre:
   :math:`\hat\sigma^2` is an unbiased estimate of the population variance
   σ², but when you take the square root, it turns out that :math:`\hat\sigma`
   is a biased estimator of the population standard deviation σ. Weird, weird,
   weird, right? So, why is :math:`\hat\sigma` biased? The technical answer is
   “because non-linear transformations (e.g., the square root) do not commute
   with expectation”, but that just sounds like gibberish to everyone who
   has not taken a course in mathematical statistics. Fortunately, it does not
   matter for practical purposes. The bias is small, and in real life everyone
   uses :math:`\hat\sigma` and it works just fine. Sometimes mathematics is
   just annoying.
