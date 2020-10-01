.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Two types of errors
-------------------

Before going into details about how a statistical test is constructed
it’s useful to understand the philosophy behind it. I hinted at it when
pointing out the similarity between a null hypothesis test and a
criminal trial, but I should now be explicit. Ideally, we would like to
construct our test so that we never make any errors. Unfortunately,
since the world is messy, this is never possible. Sometimes you’re just
really unlucky. For instance, suppose you flip a coin 10 times in a row
and it comes up heads all 10 times. That feels like very strong evidence
for a conclusion that the coin is biased, but of course there’s a 1 in
1024 chance that this would happen even if the coin was totally fair. In
other words, in real life we *always* have to accept that there’s a
chance that we made a mistake. As a consequence the goal behind
statistical hypothesis testing is not to *eliminate* errors, but to
*minimise* them.

At this point, we need to be a bit more precise about what we mean by
“errors”. First, let’s state the obvious. It is either the case that the
null hypothesis is true or that it is false, and our test will either
retain the null hypothesis or reject it.\ [#]_ So, as the table below
illustrates, after we run the test and make our choice one of four
things might have happened:

+----------------------+--------------------+--------------------+
|                      | retain H\ :sub:`0` | reject H\ :sub:`0` |
+======================+====================+====================+
| H\ :sub:`0` is true  | correct decision   | error (type I)     |
+----------------------+--------------------+--------------------+
| H\ :sub:`0` is false | error (type II)    | correct decision   |
+----------------------+--------------------+--------------------+

As a consequence there are actually *two* different types of error here.
If we reject a null hypothesis that is actually true then we have made a
**type I error**. On the other hand, if we retain the null hypothesis
when it is in fact false then we have made a **type II error**.

Remember how I said that statistical testing was kind of like a criminal
trial? Well, I meant it. A criminal trial requires that you establish
“beyond a reasonable doubt” that the defendant did it. All of the
evidential rules are (in theory, at least) designed to ensure that
there’s (almost) no chance of wrongfully convicting an innocent
defendant. The trial is designed to protect the rights of a defendant,
as the English jurist William Blackstone famously said, it is “better
that ten guilty persons escape than that one innocent suffer.” In other
words, a criminal trial doesn’t treat the two types of error in the same
way. Punishing the innocent is deemed to be much worse than letting the
guilty go free. A statistical test is pretty much the same. The single
most important design principle of the test is to *control* the
probability of a type I error, to keep it below some fixed probability.
This probability, which is denoted *α*, is called the
**significance level** of the test. And I’ll say it again, because it is
so central to the whole set-up, a hypothesis test is said to have
significance level *α* if the type I error rate is no larger
than *α*.

So, what about the type II error rate? Well, we’d also like to keep
those under control too, and we denote this probability by
*β*. However, it’s much more common to refer to the **power**
of the test, that is the probability with which we reject a null
hypothesis when it really is false, which is 1 - *β*. To help
keep this straight, here’s the same table again but with the relevant
numbers added:

+----------------------+----------------------+----------------------+
|                      | retain H\ :sub:`0`   | reject H\ :sub:`0`   |
+======================+======================+======================+
| H\ :sub:`0` is true  | 1 - *α*              | *α*                  |
|                      | (probability of      | (type I error rate)  |
|                      | correct retention)   |                      |
+----------------------+----------------------+----------------------+
| H\ :sub:`0` is false | *β*                  | 1 - *β*              |
|                      | (type II error rate) | (power of the test)  |
+----------------------+----------------------+----------------------+

A “powerful” hypothesis test is one that has a small value of
*β*, while still keeping *α* fixed at some (small)
desired level. By convention, scientists make use of three different
*α* levels: *.05*, *.01* and *.001*. Notice
the asymmetry here; the tests are designed to *ensure* that the
*α* level is kept small but there’s no corresponding
guarantee regarding *β*. We’d certainly *like* the type II
error rate to be small and we try to design tests that keep it small,
but this is typically secondary to the overwhelming need to control the
type I error rate. As Blackstone might have said if he were a
statistician, it is “better to retain 10 false null hypotheses than to
reject a single true one”. To be honest, I don’t know that I agree with
this philosophy. There are situations where I think it makes sense, and
situations where I think it doesn’t, but that’s neither here nor there.
It’s how the tests are built.

------

.. [#]
   An aside regarding the language you use to talk about hypothesis
   testing. First, one thing you really want to avoid is the word
   “prove”. A statistical test really doesn’t *prove* that a hypothesis
   is true or false. Proof implies certainty and, as the saying goes,
   statistics means never having to say you’re certain. On that point
   almost everyone would agree. However, beyond that there’s a fair
   amount of confusion. Some people argue that you’re only allowed to
   make statements like “rejected the null”, “failed to reject the
   null”, or possibly “retained the null”. According to this line of
   thinking you can’t say things like “accept the alternative” or
   “accept the null”. Personally I think this is too strong. In my
   opinion, this conflates null hypothesis testing with Karl Popper’s
   falsificationist view of the scientific process. Whilst there are
   similarities between falsificationism and null hypothesis testing,
   they aren’t equivalent. However, whilst I personally think it’s fine
   to talk about accepting a hypothesis (on the proviso that
   “acceptance” doesn’t actually mean that it’s necessarily true,
   especially in the case of the null hypothesis), many people will
   disagree. And more to the point, you should be aware that this
   particular weirdness exists so that you’re not caught unawares by it
   when writing up your own results.
