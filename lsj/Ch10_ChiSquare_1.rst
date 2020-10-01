.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

The χ² (chi-square) goodness-of-fit test
----------------------------------------

The χ² goodness-of-fit test is one of the oldest hypothesis tests around. It 
was invented by `Karl Pearson (1900) <References.html#pearson-1900>`__, with
some corrections made later by `Sir Ronald Fisher (1922a)
<References.html#fisher-1922a>`__. It tests whether an observed frequency
distribution of a nominal variable matches an expected frequency distribution.
For example, suppose a group of patients has been undergoing an experimental
treatment and have had their health assessed to see whether their condition has
improved, stayed the same or worsened. A goodness-of-fit test could be used to
determine whether the numbers in each category - improved, no change, worsened
\- match the numbers that would be expected given the standard treatment
option. Let’s think about this some more, with some psychology.

The cards data
~~~~~~~~~~~~~~

Over the years there have been many studies showing that humans find it
difficult to simulate randomness. Try as we might to “act” random, we *think*
in terms of patterns and structure and so, when asked to “do something at
random”, what people actually do is anything but random. As a consequence, the
study of human randomness (or non-randomness, as the case may be) opens up a
lot of deep psychological questions about how we think about the world. With
this in mind, let’s consider a very simple study. Suppose I asked people to
imagine a shuffled deck of cards, and mentally pick one card from this
imaginary deck “at random”. After they’ve chosen one card I ask them to
mentally select a second one. For both choices what we’re going to look at is
the suit (hearts, clubs, spades or diamonds) that people chose. After asking,
say, *N* =200 people to do this, I’d like to look at the data and figure out
whether or not the cards that people pretended to select were really random.
The data are contained in the ``randomness`` data set in which, when you open
it up in jamovi and take a look at the spreadsheet view, you will see three
variables. These are: an ``id`` variable that assigns a unique identifier to
each participant, and the two variables ``choice_1`` and ``choice_2`` that
indicate the card suits that people chose.

For the moment, let’s just focus on the first choice that people made. We’ll
use the ``Frequency tables`` option under ``Exploration`` → ``Descriptives``
to count the number of times that we observed people choosing each suit. This
is what we get:

.. code-block:: R

   clubs diamonds   hearts   spades 
      35       51       64       50      

That little frequency table is quite helpful. Looking at it, there’s a bit of a
hint that people *might* be more likely to select hearts than clubs, but it’s
not completely obvious just from looking at it whether that’s really true, or
if this is just due to chance. So we’ll probably have to do some kind of
statistical analysis to find out, which is what I’m going to talk about in the
next section.

Excellent. From this point on, we’ll treat this table as the data that we’re
looking to analyse. However, since I’m going to have to talk about this data in
mathematical terms (sorry!) it might be a good idea to be clear about what the
notation is. In mathematical notation, we shorten the human-readable word
“observed” to the letter *O*, and we use subscripts to denote the position of
the observation. So the second observation in our table is written as
*O*\ :sub:`2` in maths. The relationship between the English descriptions and
the mathematical symbols are illustrated below:

============ ========== ============= =========
label        index, *i* math. symbol  the value
============ ========== ============= =========
clubs (♣)    1          *O*\ :sub:`1` 35
diamonds (♢) 2          *O*\ :sub:`2` 51
hearts (♡)   3          *O*\ :sub:`3` 64
spades (♠)   4          *O*\ :sub:`4` 50
============ ========== ============= =========

Hopefully that’s pretty clear. It’s also worth noting that mathematicians
prefer to talk about general rather than specific things, so you’ll also see
the notation *O*\ :sub:`i`\, which refers to the number of observations that
fall within the *i*-th category (where *i* could be 1, 2, 3 or 4). Finally, if
we want to refer to the set of all observed frequencies, statisticians group
all observed values into a vector\ [#]_, which I’ll refer to as *O*.

O = (*O*\ :sub:`1`\, *O*\ :sub:`2`\, *O*\ :sub:`3`\, *O*\ :sub:`4`\)

Again, this is nothing new or interesting. It’s just notation. If I say that
*O* = (35, 51, 64, 50) all I’m doing is describing the table of observed
frequencies (i.e., ``observed``), but I’m referring to it using mathematical
notation.

The null hypothesis and the alternative hypothesis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

As the last section indicated, our research hypothesis is that “people don’t
choose cards randomly”. What we’re going to want to do now is translate this
into some statistical hypotheses and then construct a statistical test of those
hypotheses. The test that I’m going to describe to you is **Pearson’s χ²
(chi-square) goodness-of-fit test**, and as is so often the case we have to
begin by carefully constructing our null hypothesis. In this case, it’s pretty
easy. First, let’s state the null hypothesis in words:

H\ :sub:`0`: All four suits are chosen with equal probability

Now, because this is statistics, we have to be able to say the same thing in a
mathematical way. To do this, let’s use the notation *P*\ :sub:`j`\ to refer to
the true probability that the *j*-th suit is chosen. If the null hypothesis is
true, then each of the four suits has a 25% chance of being selected. In other
words, our null hypothesis claims that *P*\ :sub:`1` = 0.25, 
*P*\ :sub:`2` = 0.25, *P*\ :sub:`3` = 0.25 and finally that *P*\ :sub:`4` = 0.25.
However, in the same way that we can group our observed frequencies into a
vector *O* that summarises the entire data set, we can use *P* to refer to the
probabilities that correspond to our null hypothesis. So if I let the vector
P = (*P*\ :sub:`1`\, *P*\ :sub:`2`\, *P*\ :sub:`3`\, *P*\ :sub:`4`\)
refer to the collection of probabilities that describe our null hypothesis,
then we have:

H\ :sub:`0`: *P* = (0.25, 0.25, 0.25, 0.25)

In this particular instance, our null hypothesis corresponds to a vector of
probabilities *P* in which all of the probabilities are equal to one another.
But this doesn’t have to be the case. For instance, if the experimental task
was for people to imagine they were drawing from a deck that had twice as many
clubs as any other suit, then the null hypothesis would correspond to something
like *P* = (0.4, 0.2, 0.2, 0.2). As long as the probabilities are all positive
numbers, and they all sum to 1, then it’s a perfectly legitimate choice for the
null hypothesis. However, the most common use of the goodness-of-fit test is to
test a null hypothesis that all of the categories are equally likely, so we’ll
stick to that for our example.

What about our alternative hypothesis, H\ :sub:`1`? All we’re really interested
in is demonstrating that the probabilities involved aren’t all identical (that
is, people’s choices weren’t completely random). As a consequence, the “human
friendly” versions of our hypotheses look like this:

| H\ :sub:`0`: All four suits are chosen with equal probability
| H\ :sub:`1`: At least one of the suit-choice probabilities *isn’t* 0.25

and the “mathematician friendly” version is:

| H\ :sub:`0`: *P* = (0.25, 0.25, 0.25, 0.25)
| H\ :sub:`1`: *P* ≠ (0.25, 0.25, 0.25, 0.25)

The “goodness-of-fit” test statistic
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

At this point, we have our observed frequencies *O* and a collection of
probabilities *P* corresponding to the null hypothesis that we want to test.
What we now want to do is construct a test of the null hypothesis. As always,
if we want to test H\ :sub:`0` against H\ :sub:`1`, we’re going to need a test
statistic. The basic trick that a goodness-of-fit test uses is to construct a
test statistic that measures how “close” the data are to the null hypothesis.
If the data don’t resemble what you’d “expect” to see if the null hypothesis
were true, then it probably isn’t true. Okay, if the null hypothesis were true,
what would we expect to see? Or, to use the correct terminology, what are the
**expected frequencies**. There are N = 200 observations, and (if the null is
true) the probability of any one of them choosing a heart is *P*\ :sub:`3` =
\0.25, so I guess we’re expecting 200 · 0.25 = 50 hearts, right? Or, more
specifically, if we let *E*\ :sub:`i` refer to “the number of category *i*
responses that we’re expecting if the null is true”, then:

*E*\ :sub:`i` = N · *P*\ :sub:`i`

This is pretty easy to calculate.If there are 200 observations that can fall
into four categories, and we think that all four categories are equally likely,
then on average we’d expect to see 50 observations in each category, right?

Now, how do we translate this into a test statistic? Clearly, what we want to
do is compare the *expected* number of observations in each category
(*E*\ :sub:`i`\) with the *observed* number of observations in that category
(*O*\ :sub:`i`\). And on the basis of this comparison we ought to be able to
come up with a good test statistic. To start with, let’s calculate the
difference between what the null hypothesis expected us to find and what we
actually did find. That is, we calculate the “observed minus expected”
difference score, *O*\ :sub:`i` - *E*\ :sub:`i`. This is illustrated in the
following table:

+--------------------+-----------------+-----+-----+-----+-----+
|                    |                 | ♣   | ♢   | ♡   | ♠   |
+====================+=================+=====+=====+=====+=====+
| expected frequency | *E*\ :sub:`i`   | 50  | 50  | 50  | 50  |
+--------------------+-----------------+-----+-----+-----+-----+
| observed frequency | *O*\ :sub:`1`   | 35  | 51  | 64  | 50  |
+--------------------+-----------------+-----+-----+-----+-----+
| difference score   | *E*\ :sub:`i` - | -15 | 1   | 14  | 0   |
|                    | *O*\ :sub:`1`   |     |     |     |     |
+--------------------+-----------------+-----+-----+-----+-----+

So, based on our calculations, it’s clear that people chose more hearts and
fewer clubs than the null hypothesis predicted. However, a moment’s thought
suggests that these raw differences aren’t quite what we’re looking for.
Intuitively, it feels like it’s just as bad when the null hypothesis predicts
too few observations (which is what happened with hearts) as it is when it
predicts too many (which is what happened with clubs). So it’s a bit weird
that we have a negative number for clubs and a positive number for hearts. One
easy way to fix this is to square everything, so that we now calculate the
squared differences, (*O*\ :sub:`i` - *O*\ :sub:`i`\)². As before, we can do
this by hand:

.. code-block:: R

   (observed - expected) ^ 2
      clubs diamonds   hearts   spades 
        225        1      196        0 

Now we’re making progress. What we’ve got now is a collection of numbers that
are big whenever the null hypothesis makes a bad prediction (clubs and hearts),
but are small whenever it makes a good one (diamonds and spades). Next, for
some technical reasons that I’ll explain in a moment, let’s also divide all
these numbers by the expected frequency *E*\ :sub:`i`\, so we’re actually
calculating :math:`\frac{(E_i-O_i)^2}{E_i}`\. Since *E*\ :sub:`i` = 50 for all
categories in our example, it’s not a very interesting calculation, but let’s
do it anyway:

.. code-block:: R

   (observed - expected) ^ 2 / expected
      clubs diamonds   hearts   spades 
       4.50     0.02     3.92     0.00 

In effect, what we’ve got here are four different “error” scores, each one
telling us how big a “mistake” the null hypothesis made when we tried to use it
to predict our observed frequencies. So, in order to convert this into a useful
test statistic, one thing we could do is just add these numbers up. The result
is called the **goodness-of-fit** statistic, conventionally referred to either
as χ² (chi-square) or GOF. We can calculate it as follows:

.. code-block:: R

   sum((observed - expected) ^ 2 / expected)

This gives us a value of ``8.44``.

If we let *k* refer to the total number of categories (i.e., *k* = 4  for our
cards data), then the χ² statistic is given by:

.. math:: \chi^2 = \sum_{i=1}^k \frac{(O_i - E_i)^2}{E_i}

Intuitively, it’s clear that if χ² is small, then the observed data
*O*\ :sub:`i` are very close to what the null hypothesis predicted
*E*\ :sub:`i`\, so we’re going to need a large χ² statistic in order to reject
the null.

As we’ve seen from our calculations, in our cards data set we’ve got a value
of χ² = 8.44. So now the question becomes is this a big enough value to reject
the null?

The sampling distribution of the GOF statistic 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To determine whether or not a particular value of χ² is large enough to justify
rejecting the null hypothesis, we’re going to need to figure out what the
sampling distribution for χ² would be if the null hypothesis were true. So
that’s what I’m going to do in this section. I’ll show you in a fair amount of
detail how this sampling distribution is constructed, and then, in the next
section, use it to build up a hypothesis test. If you want to cut to the chase
and are willing to take it on faith that the sampling distribution is a
**χ²-distribution** with *k* - 1 degrees of freedom, you can skip the rest of
this section. However, if you want to understand *why* the goodness-of-fit test
works the way it does, read on.

Okay, let’s suppose that the null hypothesis is actually true. If so, then the
true probability that an observation falls in the *i*-th category is
*P*\ :sub:`i`\. After all, that’s pretty much the definition of our null
hypothesis. Let’s think about what this actually means. This is kind of like
saying that “nature” makes the decision about whether or not the observation
ends up in category *i* by flipping a weighted coin (i.e., one where the
probability of getting a head is *P*\ :sub:`j`\).
And therefore we can think of our observed frequency *O*\ :sub:`i` by
imagining that nature flipped *N* of these coins (one for each observation in
the data set), and exactly *O*\ :sub:`i` of them came up heads. Obviously, this
is a pretty weird way to think about the experiment. But what it does (I hope)
is remind you that we’ve actually seen this scenario before. It’s exactly the
same set up that gave rise to the binomial distribution in Section `Binomial
distribution <Ch07_Probability_4.html#the-binomial-distribution>`__. In other
words, if the null hypothesis is true, then it follows that our observed
frequencies were generated by sampling from a binomial distribution:

*O*\ :sub:`i` ~ Binomial(*P*\ :sub:`i`\, N)

Now, if you remember from our discussion of `the central limit theorem
<Ch08_Estimation_3.html#the-central-limit-theorem>`__ the binomial distribution
starts to look pretty much identical to the normal distribution, especially
when *N* is large and when *P*\ :sub:`i` isn’t *too* close to 0 or 1. In other
words as long as *N* · *P*\ :sub:`i` is large enough. Or, to put it another
way, when the expected frequency *E*\ :sub:`i` is large enough then the
theoretical distribution of *O*\ :sub:`i` is approximately normal. Better yet,
if *O*\ :sub:`i` is normally distributed, then so is 
:math:`(O_i - E_i)/\sqrt{E_i}`. Since *E*\ :sub:`i` is a fixed value,
subtracting off *E*\ :sub:`i` and dividing by :math:`\sqrt{E_i}` changes the
mean and standard deviation of the normal distribution but that’s all it does.
Okay, so now let’s have a look at what our goodness-of-fit statistic actually
*is*. What we’re doing is taking a bunch of things that are
normally-distributed, squaring them, and adding them up. Wait. We’ve seen that
before too! As we discussed in `Other useful distributions
<Ch07_Probability_6.html#other-useful-distributions>`__, when you take a bunch
of things that have a standard normal distribution (i.e., mean 0 and standard
deviation 1), square them and then add them up, the resulting quantity has a
χ²-distribution. So now we know that the null hypothesis predicts that the
sampling distribution of the goodness-of-fit statistic is a χ²-distribution.
Cool.

There’s one last detail to talk about, namely the degrees of freedom. If you
remember back to `Other useful distributions
<Ch07_Probability_6.html#other-useful-distributions>`__, I said that if the
number of things you’re adding up is *k*, then the degrees of freedom for the
resulting χ²-distribution is *k*. Yet, what I said at the start of this section
is that the actual degrees of freedom for the χ²-goodness-of-fit test is *k* -
\1. What’s up with that? The answer here is that what we’re supposed to be
looking at is the number of genuinely *independent* things that are getting
added together. And, as I’ll go on to talk about in the next section, even
though there are *k* things that we’re adding only *k* - 1 of them are truly
independent, and so the degrees of freedom is actually only *k* - 1. That’s the
topic of the next section.\ [#]_

Degrees of freedom
~~~~~~~~~~~~~~~~~~

When I introduced the χ²-distribution in `Other useful distributions
<Ch07_Probability_6.html#other-useful-distributions>`__, I was a bit vague 
about what “**degrees of freedom**” actually *means*. Obviously, it matters.
Looking at :numref:`fig-chiSqDists`, you can see that if we change the
degrees of freedom then the χ²-distribution changes shape quite substantially.
But what exactly *is* it? Again, when I introduced the distribution and
explained its relationship to the normal distribution, I did offer an answer:
it’s the number of “normally distributed variables” that I’m squaring and
adding together. But, for most people, that’s kind of abstract and not entirely
helpful. What we really need to do is try to understand degrees of freedom in
terms of our data. So here goes.

.. ----------------------------------------------------------------------------

.. _fig-chiSqDists:
.. figure:: ../_images/lsj_chiSqDists.*
   :alt: χ² distributions with different degrees of freedom

   χ² (chi-square) distributions with different values for the “degrees of
   freedom”
   
.. ----------------------------------------------------------------------------

The basic idea behind degrees of freedom is quite simple. You calculate it by
counting up the number of distinct “quantities” that are used to describe your
data and then subtracting off all of the “constraints” that those data must
satisfy.\ [#]_ This is a bit vague, so let’s use our cards data as a concrete
example. We describe our data using four numbers, *O*\ :sub:`1`\,
*O*\ :sub:`2`\, *O*\ :sub:`3` and *O*\ :sub:`4` corresponding to the observed
frequencies of the four different categories (hearts, clubs, diamonds, spades).
These four numbers are the *random outcomes* of our experiment. But my
experiment actually has a fixed constraint built into it: the sample size
*N*.\ [#]_ That is, if we know how many people chose hearts, how many chose
diamonds and how many chose clubs, then we’d be able to figure out exactly how
many chose spades. In other words, although our data are described using four
numbers, they only actually correspond to 4 - 1 = 3 degrees of freedom. A
slightly different way of thinking about it is to notice that there are four
*probabilities* that we’re interested in (again, corresponding to the four
different categories), but these probabilities must sum to one, which imposes
a constraint. Therefore the degrees of freedom is 4 - 1 = 3. Regardless of
whether you want to think about it in terms of the observed frequencies or in
terms of the probabilities, the answer is the same. In general, when running
the χ² (chi-square) goodness-of-fit test for an experiment involving *k*
groups, then the degrees of freedom will be *k* - 1.

Testing the null hypothesis
~~~~~~~~~~~~~~~~~~~~~~~~~~~

The final step in the process of constructing our hypothesis test is to figure
out what the rejection region is. That is, what values of χ² would lead us to
reject the null hypothesis. As we saw earlier, large values of χ² imply that
the null hypothesis has done a poor job of predicting the data from our
experiment, whereas small values of χ² imply that it’s actually done pretty
well. Therefore, a pretty sensible strategy would be to say there is some
critical value such that if χ² is bigger than the critical value we reject the
null, but if χ² is smaller than this value we retain the null. In other words,
to use the language we introduced in Chapter `Hypothesis testing
<Ch09_HypothesisTesting.html#hypothesis-testing>`__ the χ²-goodness-of-fit test
is always a **one-sided test**. Right, so all we have to do is figure out what
this critical value is. And it’s pretty straightforward. If we want our test to
have significance level of *α* = 0.05 (that is, we are willing to tolerate a
Type I error rate of 5%), then we have to choose our critical value so that
there is only a 5% chance that χ² could get to be that big if the null
hypothesis is true. This is illustrated in :numref:`fig-chiSqTest`.

.. ----------------------------------------------------------------------------

.. _fig-chiSqTest:
.. figure:: ../_images/lsj_chiSqTest.*
   :alt: Hypothesis testing works for the χ² GOF test

   Illustration of how the hypothesis testing works for the χ² (chi-square)
   goodness-of-fit test
   
.. ----------------------------------------------------------------------------

Ah but, I hear you ask, how do I find the critical value of a χ²-distribution
with *k* - 1 degrees of freedom? Many many years ago when I first took a
psychology statistics class we used to look up these critical values in a book
of critical value tables, like the one in :numref:`fig-chisquared_critvalues`.
Looking at :numref:`fig-chisquared_critvalues`, we can see that the critical
value for a χ²-distribution with 3 degrees of freedom, and *p* = 0.05 is 7.815.

.. ----------------------------------------------------------------------------

.. _fig-chisquared_critvalues:
.. figure:: ../_images/lsj_chisquared_critvalues.*
   :alt: Table of critical values for the χ² distribution

   Table of critical values for the χ² (chi-square) distribution
   
.. ----------------------------------------------------------------------------

So, if our calculated χ² statistic is bigger than the critical value of 7.815,
then we can reject the null hypothesis (remember that the null hypothesis,
H\ :sub:`0`, is that all four suits are chosen with equal probability). Since
we actually already calculated that before (i.e., χ² = 8.44) we can reject the
null hypothesis. And that’s it, basically. You now know “Pearson’s χ² test for
the goodness-of-fit”. Lucky you.

Doing the test in jamovi
~~~~~~~~~~~~~~~~~~~~~~~~

Not surprisingly, jamovi provides an analysis that will do these calculations
for you. From the main ``Analyses`` toolbar select ``Frequencies`` → ``One
Sample Proportion Tests`` → ``N Outcomes``. Then in the analysis panel that
appears move the variable you want to analyse (``choice_1`` across into the
``Variable`` box. Also, click on the ``Expected counts`` check box so that
these are shown on the results table. When you have done all this, you should
see the analysis results in jamovi as in :numref:`fig-chisquared_analysis1`.
No surprise then that jamovi provides the same expected counts and statistics
that we calculated by hand above, with a χ² value of 8.44 with *df* = 3 and
*p* =0.038. Note that we don’t need to look up a critical *p*-value threshold
value any more, as jamovi gives us the actual *p*-value of the calculated χ²
for *df* = 3.

.. ----------------------------------------------------------------------------

.. _fig-chisquared_analysis1:
.. figure:: ../_images/lsj_chisquared_analysis1.*
   :alt: χ² One Sample Proportion Test in jamovi

   χ² One Sample Proportion Test in jamovi, with table showing both observed
   and expected frequencies and proportions
   
.. ----------------------------------------------------------------------------

Specifying a different null hypothesis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

At this point you might be wondering what to do if you want to run a
goodness-of-fit test but your null hypothesis is *not* that all categories are
equally likely. For instance, let’s suppose that someone had made the
theoretical prediction that people should choose red cards 60% of the time, and
black cards 40% of the time (I’ve no idea why you’d predict that), but had no
other preferences. If that were the case, the null hypothesis would be to
expect 30% of the choices to be hearts, 30% to be diamonds, 20% to be spades
and 20% to be clubs. In other words we would expect hearts and diamonds to
appear 1.5 times more often than spades and clubs (the ratio 30% : 20% is the
same as 1.5 : 1). This seems like a silly theory to me, and it’s pretty easy to
test this explicitly specified null hypothesis with the data in our jamovi
analysis. In the analysis window (labelled ``Proportion Test (N Outcomes)`` in
:numref:`fig-chisquared_analysis1` you can expand the options for ``Expected
Proportions``. When you do this, there are options for entering different ratio
values for the variable you have selected, in our case this is ``choice_1``.
Change the ratio to reflect the new null hypothesis, as in
:numref:`fig-chisquared_analysis2`, and see how the results change.

The expected counts are now:

+--------------------+---------------+----+----+----+----+
|                    |               | ♣  | ♢  | ♡  | ♠  |
+--------------------+---------------+----+----+----+----+
| expected frequency | *E*\ :sub:`i` | 40 | 60 | 60 | 40 |
+--------------------+---------------+----+----+----+----+

and the χ² statistic is 4.74, *df* = 3, *p* = 0.182. Now, the results of our
updated hypotheses and the expected frequencies are different from what they
were last time. As a consequence our χ² test statistic is different, and our
*p*-value is different too. Annoyingly, the *p*-value is 0.182, so we can’t
reject the null hypothesis (look back at Section `The p value of a test
<Ch09_HypothesisTesting_05.html#the-p-value-of-a-test>`__ to remind yourself
why). Sadly, despite the fact that the null hypothesis corresponds to a very
silly theory, these data don’t provide enough evidence against it.

.. ----------------------------------------------------------------------------

.. _fig-chisquared_analysis2:
.. figure:: ../_images/lsj_chisquared_analysis2.*
   :alt: Changing expected proportions in the χ² One Sample Proportion Test

   Changing the expected proportions in the χ² One Sample Proportion Test in
   jamovi
   
.. ----------------------------------------------------------------------------

How to report the results of the test
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

So now you know how the test works, and you know how to do the test using a
wonderful jamovi flavoured magic computing box. The next thing you need to know
is how to write up the results. After all, there’s no point in designing and
running an experiment and then analysing the data if you don’t tell anyone
about it! So let’s now talk about what you need to do when reporting your
analysis. Let’s stick with our card-suits example. If I wanted to write this
result up for a paper or something, then the conventional way to report this
would be to write something like this:

   Of the 200 participants in the experiment, 64 selected hearts for their
   first choice, 51 selected diamonds, 50 selected spades, and 35 selected
   clubs. A χ²-goodness-of-fit test was conducted to test whether the choice
   probabilities were identical for all four suits. The results were
   significant (χ²(3) = 8.44, p < 0.05), suggesting that people did not
   select suits purely at random.

This is pretty straightforward and hopefully it seems pretty unremarkable. That
said, there’s a few things that you should note about this description:

-  *The statistical test is preceded by the descriptive statistics*. That is, I
   told the reader something about what the data look like before going on to
   do the test. In general, this is good practice. Always remember that your
   reader doesn’t know your data anywhere near as well as you do. So, unless
   you describe it to them properly, the statistical tests won’t make any sense
   to them and they’ll get frustrated and cry.

-  *The description tells you what the null hypothesis being tested is*. To be
   honest, writers don’t always do this but it’s often a good idea in those
   situations where some ambiguity exists, or when you can’t rely on your
   readership being intimately familiar with the statistical tools that you’re
   using. Quite often the reader might not know (or remember) all the details
   of the test that your using, so it’s a kind of politeness to “remind” them!
   As far as the goodness-of-fit test goes, you can usually rely on a
   scientific audience knowing how it works (since it’s covered in most intro
   stats classes). However, it’s still a good idea to be explicit about stating
   the null hypothesis (briefly!) because the null hypothesis can be different
   depending on what you’re using the test for. For instance, in the cards
   example my null hypothesis was that all the four suit probabilities were
   identical (i.e., *P*\ :sub:`1` = *P*\ :sub:`2` = *P*\ :sub:`3` =
   *P*\ :sub:`4` = 0.25), but there’s nothing special about that hypothesis. I
   could just as easily have tested the null hypothesis that *P*\ :sub:`1` =
   \0.7 and *P*\ :sub:`2` = *P*\ :sub:`3` = *P*\ :sub:`4` = 0.1 using a
   goodness-of-fit test. So it’s helpful to the reader if you explain to them
   what your null hypothesis was. Also, notice that I described the null
   hypothesis in words, not in maths. That’s perfectly acceptable. You can
   describe it in maths if you like, but since most readers find words easier
   to read than symbols, most writers tend to describe the null using words if
   they can.

-  *A “stat block” is included*. When reporting the results of the test itself,
   I didn’t just say that the result was significant, I included a “stat block”
   (i.e., the dense mathematical-looking part in the parentheses) which reports
   all the “key” statistical information. For the χ²-goodness-of-fit test, the
   information that gets reported is the test statistic (that the
   goodness-of-fit statistic was 8.44), the information about the distribution
   used in the test (χ² with 3 degrees of freedom which is usually shortened to
   χ²(3)), and then the information about whether the result was significant
   (in this case p < 0.05). The particular information that needs to go into
   the stat block is different for every test, and so each time I introduce a
   new test I’ll show you what the stat block should look like.\ [#]_ However,
   the general principle is that you should always provide enough information
   so that the reader could check the test results themselves if they really
   wanted to.

-  *The results are interpreted*. In addition to indicating that the result was
   significant, I provided an interpretation of the result (i.e., that people
   didn’t choose randomly). This is also a kindness to the reader, because it
   tells them something about what they should believe about what’s going on in
   your data. If you don’t include something like this, it’s really hard for
   your reader to understand what’s going on.\ [#]_

As with everything else, your overriding concern should be that you *explain*
things to your reader. Always remember that the point of reporting your results
is to communicate to another human being. I cannot tell you just how many times
I’ve seen the results section of a report or a thesis or even a scientific
article that is just gibberish, because the writer has focused solely on making
sure they’ve included all the numbers and forgotten to actually communicate
with the human reader.

A comment on statistical notation 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

   | *Satan delights equally in statistics and in quoting scripture*
   | – H.G. Wells

If you’ve been reading very closely, and are as much of a mathematical pedant
as I am, there is one thing about the way I wrote up the χ²-test in the last
section that might be bugging you a little bit. There’s something that feels a
bit wrong with writing “χ²(3) = 8.44”, you might be thinking. After all, it’s
the goodness-of-fit statistic that is equal to 8.44, so shouldn’t I have
written χ² = 8.44` or maybe GOF = 8.44? This seems to be conflating the
*sampling distribution* (i.e., χ² with *df* = 3) with the *test statistic*
(i.e., χ²). Odds are you figured it was a typo, since *χ* and *X* look pretty
similar. Oddly, it’s not. Writing :χ²(3) = 8.44 is essentially a highly
condensed way of writing “the sampling distribution of the test statistic is
χ²(3), and the value of the test statistic is 8.44”.

In one sense, this is kind of stupid. There are *lots* of different test
statistics out there that turn out to have a χ²-sampling-distribution. The
χ²-statistic that we’ve used for our goodness-of-fit test is only one of many
(albeit one of the most commonly encountered ones). In a sensible, perfectly
organised world we’d *always* have a separate name for the test statistic and
the sampling distribution. That way, the stat block itself would tell you
exactly what it was that the researcher had calculated. Sometimes this happens.
For instance, the test statistic used in the Pearson goodness-of-fit test is
written χ², but there’s a closely related test known as the *G*-test\ [#]_
(`Sokal & Rohlf, 1994 <References.html#sokal-1994>`__\ ), in which the test
statistic is written as *G*. As it happens, the Pearson goodness-of-fit test
and the *G*-test both test the same null hypothesis, and the sampling
distribution is exactly the same (i.e., a χ²-distribution  with *k* - 1
degrees of freedom). If I’d done a *G*-test for the cards data rather than a
goodness-of-fit test, then I’d have ended up with a test statistic of
*G* = 8.65, which is slightly different from the χ² = 8.44 value that I got
earlier and which produces a slightly smaller *p*-value of *p* = 0.034. Suppose
that the convention was to report the test statistic, then the sampling
distribution, and then the *p*-value. If that were true, then these two
situations would produce different stat blocks: my original result would be
written χ² = 8.44, χ²(3), p = 0.038, whereas the new version using the *G*-test
would be written as *G* = 8.65, χ²(3), p = 0.034. However, using the condensed
reporting standard, the original result is written χ²(3) = 8.44, p = 0.038,
and the new one is written χ²(3) = 8.65, p = 0.034, and so it’s actually
unclear which test I actually ran.

So why don’t we live in a world in which the contents of the stat block
uniquely specifies what tests were ran? The deep reason is that life is messy.
We (as users of statistical tools) want it to be nice and neat and organised.
We want it to be *designed*, as if it were a product, but that’s not how life
works. Statistics is an intellectual discipline just as much as any other one,
and as such it’s a massively distributed, partly-collaborative and
partly-competitive project that no-one really understands completely. The
things that you and I use as data analysis tools weren’t created by an Act of
the Gods of Statistics. They were invented by lots of different people,
published as papers in academic journals, implemented, corrected and modified
by lots of other people, and then explained to students in textbooks by someone
else. As a consequence, there’s a *lot* of test statistics that don’t even have
names, and as a consequence they’re just given the same name as the
corresponding sampling distribution. As we’ll see later, any test statistic
that follows a χ² distribution is commonly called a χ²-statistic”,
anything that follows a *t*-distribution is called a “*t*-statistic”, and so
on. But, as the χ² versus *G* example illustrates, two different things with
the same sampling distribution are still, well, different.

As a consequence, it’s sometimes a good idea to be clear about what the actual
test was that you ran, especially if you’re doing something unusual. If you
just say “χ²-test” it’s not actually clear what test you’re talking about.
Although, since the two most common χ² tests are the goodness-of-fit test and
the `test of independence (or association)
<Ch10_ChiSquare_2.html#the-2-chi-square-test-of-independence-or-association>`__,
most readers with stats training can probably guess. Nevertheless, it’s
something to be aware of.

------

.. [#]
   A vector is a sequence of data elements of the same basic type

.. [#]
   If you rewrite the equation for the goodness-of-fit statistic as a sum over
   *k* - 1 independent things you get the “proper” sampling distribution, which
   is χ²-distribution with *k* - 1 degrees of freedom. It’s beyond the scope of
   an introductory book to show the maths in that much detail. All I wanted to
   do is give you a sense of why the goodness-of-fit statistic is associated
   with the χ²-distribution.

.. [#]
   I feel obliged to point out that this is an over-simplification. It
   works nicely for quite a few situations, but every now and then we’ll
   come across degrees of freedom values that aren’t whole numbers.
   Don’t let this worry you too much; when you come across this just
   remind yourself that “degrees of freedom” is actually a bit of a
   messy concept, and that the nice simple story that I’m telling you
   here isn’t the whole story. For an introductory class it’s usually
   best to stick to the simple story, but I figure it’s best to warn you
   to expect this simple story to fall apart. If I didn’t give you this
   warning you might start getting confused when you see
   *df* = 3.4 or something, (incorrectly) thinking that you had
   misunderstood something that I’ve taught you rather than (correctly)
   realising that there’s something that I haven’t told you.

.. [#]
   In practice, the sample size isn’t always fixed. For example, we
   might run the experiment over a fixed period of time and the number
   of people participating depends on how many people show up. That
   doesn’t matter for the current purposes.

.. [#]
   Well, sort of. The conventions for how statistics should be reported
   tend to differ somewhat from discipline to discipline. I’ve tended to
   stick with how things are done in psychology, since that’s what I do.
   But the general principle of providing enough information to the
   reader to allow them to check your results is pretty universal, I
   think.

.. [#]
   To some people, this advice might sound odd, or at least in conflict
   with the “usual” advice on how to write a technical report. Very
   typically, students are told that the “results” section of a report
   is for describing the data and reporting statistical analysis, and
   the “discussion” section is for providing interpretation. That’s true
   as far as it goes, but I think people often interpret it way too
   literally. The way I usually approach it is to provide a quick and
   simple interpretation of the data in the results section, so that my
   reader understands what the data are telling us. Then, in the
   discussion, I try to tell a bigger story about how my results fit
   with the rest of the scientific literature. In short, don’t let the
   “interpretation goes in the discussion” advice turn your results
   section into incomprehensible garbage. Being understood by your
   reader is *much* more important.

.. [#]
   Complicating matters, the *G*-test is a special case of a whole
   class of tests that are known as *likelihood ratio tests*. I don’t
   cover LRTs in this book, but they are quite handy things to know
   about.
