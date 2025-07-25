.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Standard scores
---------------

Suppose my friend is putting together a new questionnaire intended to measure
“grumpiness”. The survey has 50 questions which you can answer in a grumpy way
or not. Across a big sample (hypothetically, let us imagine a million people)
the data are fairly normally distributed, with the mean grumpiness score being
17 out of 50 questions answered in a grumpy way, and the standard deviation is
\5. In contrast, when I take the questionnaire I answer 35 out of 50 questions
in a grumpy way. So, how grumpy am I? One way to think about it would be to say
that I have grumpiness of 35/50, so you might say that I am 70\% grumpy. But
that is a bit weird, when you think about it. If my friend had phrased her
questions a bit differently people might have answered them in a different way,
so the overall distribution of answers could easily move up or down depending
on the precise way in which the questions were asked. So, I am only 70\% grumpy
*with respect to this set of survey questions*. Even if it is a very good
questionnaire this is not very a informative statement.

A simpler way around this is to describe my grumpiness by comparing me to other
people. Shockingly, out of my friend’s sample of 1 000 000 people, only 159
people were as grumpy as me (that is not at all unrealistic, frankly)
suggesting that I am in the top 0.016\% of people for grumpiness. This makes
much more sense than trying to interpret the raw data. This idea, that we
should describe my grumpiness in terms of the overall distribution of the
grumpiness of humans, is the qualitative idea that standardisation attempts to
get at. One way to do this is to do exactly what I just did and describe
everything in terms of percentiles. However, the problem with doing this is
that “is is lonely at the top”. Suppose that my friend had only collected a
sample of 1000 people (still a pretty big sample for the purposes of testing a
new questionnaire, I would like to add), and this time had gotten, let us say,
a mean of 16 out of 50 with a standard deviation of 5. The problem is that
almost certainly not a single person in that sample would be as grumpy as me.

However, all is not lost. A different approach is to convert my grumpiness
score into a **standard score**, also referred to as a *z*-score. The standard
score is defined as the number of standard deviations above the mean that my
grumpiness score lies. To phrase it in “pseudo-maths” the standard score is
calculated like this:

.. math:: \mbox{standard score} = \frac{\mbox{raw score} - \mbox{mean}}{\mbox{standard deviation}}

In actual maths, the equation for the *z*-score is:

.. math:: z_i = \frac{X_i - \bar{X}}{\hat\sigma}

So, going back to the grumpiness data, we can now transform Danielle’s raw
grumpiness into a standardised grumpiness score:

.. math:: z = \frac{35 - 17}{5} = 3.6

To interpret this value, recall the rough heuristic that I provided in section
:ref:`Standard deviation <standard_deviation>` in which I noted that 99.7\% of
values are expected to lie within three standard deviations of the mean. So the
fact that my grumpiness corresponds to a *z* score of 3.6 indicates that I am
very grumpy indeed. In fact this suggests that I am grumpier than 99.98\% of
people. Sounds about right.

In addition to allowing you to interpret a raw score in relation to a larger
population (and thereby allowing you to make sense of variables that lie on
arbitrary scales), standard scores serve a second useful function. Standard
scores can be compared to one another in situations where the raw scores can
not. Suppose, for instance, my friend also had another questionnaire that
measured extraversion using a 24 item questionnaire. The overall mean for this
measure turns out to be 13 with standard deviation 4, and I scored a 2. As you
can imagine, it does not make a lot of sense to try to compare my raw score of
2 on the extraversion questionnaire to my raw score of 35 on the grumpiness
questionnaire. The raw scores for the two variables are “about” fundamentally
different things, so this would be like comparing apples to oranges.

What about the standard scores? Well, this is a little different. If we
calculate the standard scores we get *z* = (35 - 17) / 5 = 3.6 for grumpiness
and *z* = (2 - 13) / 4 = -2.75 for extraversion. These two numbers *can* be
compared to each other.\ [#]_ I am much less extraverted than most people
(*z* = -2.75) and much grumpier than most people (*z* = 3.6). But the extent of
my unusualness is much more extreme for grumpiness, since 3.6 is a bigger
number than 2.75. Because each standardised score is a statement about where an
observation falls *relative to its own population*, it is possible to compare
standardised scores across completely different variables.

------

.. [#]
   Though some caution is usually warranted. It is not always the case that one 
   standard deviation on variable A corresponds to the same “kind” of thing as 
   one standard deviation on variable B. Use common sense when trying to 
   determine whether or not the *z* scores of two variables can be meaningfully 
   compared.
