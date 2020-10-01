.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Some issues to consider
-----------------------

What I’ve described to you in this chapter is the orthodox framework for
null hypothesis significance testing (NHST). Understanding how NHST
works is an absolute necessity because it has been the dominant approach
to inferential statistics ever since it came to prominence in the early
20th century. It’s what the vast majority of working scientists rely on
for their data analysis, so even if you hate it you need to know it.
However, the approach is not without problems. There are a number of
quirks in the framework, historical oddities in how it came to be,
theoretical disputes over whether or not the framework is right, and a
lot of practical traps for the unwary. I’m not going to go into a lot of
detail on this topic, but I think it’s worth briefly discussing a few of
these issues.

Neyman versus Fisher
~~~~~~~~~~~~~~~~~~~~

The first thing you should be aware of is that orthodox NHST is actually
a mash-up of two rather different approaches to hypothesis testing, one
proposed by Sir Ronald Fisher and the other proposed by Jerzy Neyman
(see `Lehmann, 2011 <References.html#cronbach-1951>`__ for a historical
summary). The history is messy because Fisher and Neyman were real people
whose opinions changed over time, and at no point did either of them offer
“the definitive statement” of how we should interpret their work many
decades later. That said, here’s a quick summary of what I take these
two approaches to be.

First, let’s talk about Fisher’s approach. As far as I can tell, Fisher
assumed that you only had the one hypothesis (the null) and that what
you want to do is find out if the null hypothesis is inconsistent with
the data. From his perspective, what you should do is check to see if
the data are “sufficiently unlikely” according to the null. In fact, if
you remember back to our earlier discussion, that’s how Fisher defines
the *p*-value. According to Fisher, if the null hypothesis
provided a very poor account of the data then you could safely reject
it. But, since you don’t have any other hypotheses to compare it to,
there’s no way of “accepting the alternative” because you don’t
necessarily have an explicitly stated alternative. That’s more or less
all there is to it.

In contrast, Neyman thought that the point of hypothesis testing was as
a guide to action and his approach was somewhat more formal than
Fisher’s. His view was that there are multiple things that you could
*do* (accept the null or accept the alternative) and the point of the
test was to tell you which one the data support. From this perspective,
it is critical to specify your alternative hypothesis properly. If you
don’t know what the alternative hypothesis is, then you don’t know how
powerful the test is, or even which action makes sense. His framework
genuinely requires a competition between different hypotheses. For
Neyman, the *p* value didn’t directly measure the probability of
the data (or data more extreme) under the null, it was more of an
abstract description about which “possible tests” were telling you to
accept the null, and which “possible tests” were telling you to accept
the alternative.

As you can see, what we have today is an odd mishmash of the two. We
talk about having both a null hypothesis and an alternative (Neyman),
but usually\ [#]_ define the *p* value in terms of exreme data
(Fisher), but we still have *α* values (Neyman). Some of the
statistical tests have explicitly specified alternatives (Neyman) but
others are quite vague about it (Fisher). And, according to some people
at least, we’re not allowed to talk about accepting the alternative
(Fisher). It’s a mess, but I hope this at least explains why it’s a
mess.

Bayesians versus frequentists
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Earlier on in this chapter I was quite emphatic about the fact that you
*cannot* interpret the *p* value as the probability that the null hypothesis is
true. NHST is fundamentally a frequentist tool (see Chapter `Introduction to
probability <Ch07_Probability.html#introduction-to-probability>`__) and as such
it does not allow you to assign probabilities to hypotheses. The null
hypothesis is either true or it is not. The Bayesian approach to statistics
interprets probability as a degree of belief, so it’s totally okay to say that
there is a 10% chance that the null hypothesis is true. That’s just a
reflection of the degree of confidence that you have in this hypothesis.
You aren’t allowed to do this within the frequentist approach. Remember,
if you’re a frequentist, a probability can only be defined in terms of
what happens after a large number of independent replications (i.e., a
long run frequency). If this is your interpretation of probability,
talking about the “probability” that the null hypothesis is true is
complete gibberish: a null hypothesis is either true or it is false.
There’s no way you can talk about a long run frequency for this
statement. To talk about “the probability of the null hypothesis” is as
meaningless as “the colour of freedom”. It doesn’t have one!

Most importantly, this *isn’t* a purely ideological matter. If you
decide that you are a Bayesian and that you’re okay with making
probability statements about hypotheses, you have to follow the Bayesian
rules for calculating those probabilities. I’ll talk more about this in
Chapter `Bayesian statistics <Ch16_Bayes.html#bayesian-statistics>`__,
but for now what I want to point out to you is the *p* value is a *terrible*
approximation to the probability that H\ :sub:`0` is true. If what you want
to know is the probability of the null, then the *p* value is not what you’re
looking for!

Traps
~~~~~

As you can see, the theory behind hypothesis testing is a mess, and even
now there are arguments in statistics about how it “should” work.
However, disagreements among statisticians are not our real concern
here. Our real concern is practical data analysis. And while the
“orthodox” approach to null hypothesis significance testing has many
drawbacks, even an unrepentant Bayesian like myself would agree that
they can be useful if used responsibly. Most of the time they give
sensible answers and you can use them to learn interesting things.
Setting aside the various ideologies and historical confusions that
we’ve discussed, the fact remains that the biggest danger in all of
statistics is *thoughtlessness*. I don’t mean stupidity, I literally
mean thoughtlessness. The rush to interpret a result without spending
time thinking through what each test actually says about the data, and
checking whether that’s consistent with how you’ve interpreted it.
That’s where the biggest trap lies.

To give an example of this, consider the following example (`Gelman &
Stern, 2006 <References.html#gleman-2006>`__\ ). Suppose I’m running my
ESP study and I’ve decided to analyse the data separately for the male
participants and the female participants. Of the male participants, 33
out of 50 guessed the colour of the card correctly. This is a
significant effect (*p* = 0.03). Of the female participants, 29 out
of 50 guessed correctly. This is not a significant effect
(p = 0.32). Upon observing this, it is extremely tempting for
people to start wondering why there is a difference between males and
females in terms of their psychic abilities. However, this is wrong. If
you think about it, we haven’t *actually* run a test that explicitly
compares males to females. All we have done is compare males to chance
(binomial test was significant) and compared females to chance (binomial
test was non significant). If we want to argue that there is a real
difference between the males and the females, we should probably run a
test of the null hypothesis that there is no difference! We can do that
using a different hypothesis test,\ [#]_ but when we do that it turns
out that we have no evidence that males and females are significantly
different (*p* = 0.54). *Now* do you think that there’s anything
fundamentally different between the two groups? Of course not. What’s
happened here is that the data from both groups (male and female) are
pretty borderline. By pure chance one of them happened to end up on the
magic side of the *p* = 0.05 line, and the other one didn’t. That
doesn’t actually imply that males and females are different. This
mistake is so common that you should always be wary of it. The
difference between significant and not-significant is *not* evidence of
a real difference. If you want to say that there’s a difference between
two groups, then you have to test for that difference!

The example above is just that, an example. I’ve singled it out because
it’s such a common one, but the bigger picture is that data analysis can
be tricky to get right. Think about what it is you want to test, why you
want to test it, and whether or not the answers that your test gives
could possibly make any sense in the real world.

------

.. [#]
   Although this book describes both Neyman’s and Fisher’s definition of
   the *p* value, most don’t. Most introductory textbooks will
   only give you the Fisher version.

.. [#]
   In this case, the Pearson `χ²-test of independence
   <Ch10_ChiSquare_2.html#the-2-chi-square-test-of-independence-or-association>`__. 
