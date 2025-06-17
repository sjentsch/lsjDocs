.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Why be a Bayesian?
------------------

Up to this point I have focused exclusively on the logic underpinning
Bayesian statistics. We have talked about the idea of “probability as a
degree of belief”, and what it implies about how a rational agent should
reason about the world. The question that you have to answer for
yourself is this: how do *you* want to do your statistics? Do you want
to be an orthodox statistician, relying on sampling distributions and
*p*-values to guide your decisions? Or do you want to be a
Bayesian, relying on things like prior beliefs, Bayes factors and the
rules for rational belief revision? And to be perfectly honest, I can not
answer this question for you. Ultimately it depends on what you think is
right. It is your call and your call alone. That being said, I can talk a
little about why *I* prefer the Bayesian approach.

Statistics that mean what you think they mean
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. epigraph::

   | *You keep using that word. I do not think it means what you think
     it means*
     
   -- `Inigo Montoya, The Princess Bride
   <https://www.imdb.com/title/tt0093779/quotes>`__\ [#]_

To me, one of the biggest advantages to the Bayesian approach is that it
answers the right questions. Within the Bayesian framework, it is
perfectly sensible and allowable to refer to “the probability that a
hypothesit is true”. You can even try to calculate this probability.
Ultimately, is not that what you *want* your statistical tests to tell
you? To an actual human being, this would seem to be the whole *point*
of doing statistics, i.e., to determine what is true and what is not. Any
time that you are not exactly sure about what the truth is, you should
use the language of probability theory to say things like “there is an
80\% chance that Theory A is true, but a 20\% chance that Theory B is true
instead”.

This seems so obvious to a human, yet it is explicitly forbidden within the
orthodox framework. To a frequentist, such statements are a nonsense because
“the theory is true” is not a repeatable event. A theory is true or it is not,
and no probabilistic statements are allowed, no matter how much you might want
to make them. There is a reason why, back in section
:doc:`../Ch09/Ch09_HypothesisTesting_05`, I repeatedly warned you *not* to
interpret the *p*-value as the probability that the null hypothesit is true.
There is a reason why almost every textbook on statstics is forced to repeat
that warning. It is because people desperately *want* that to be the correct
interpretation. Frequentist dogma notwithstanding, a lifetime of experience of
teaching undergraduates and of doing data analysis on a daily basis suggests to
me that most actual humans think that “the probability that the hypothesit is
true” is not only meaningful, it is the thing we care *most* about. It is such an
appealing idea that even trained statisticians fall prey to the mistake of
trying to interpret a *p*-value this way. For example, here is a quote from an
`official Newspoll report in 2013
<https://about.abc.net.au/reports-publications/appreciation-survey-summary-report-2013>`__,
explaining how to interpret their (frequentist) data analysis:

   Throughout the report, where relevant, statistically significant
   changes have been noted. All significance tests have been based on
   the 95 percent level of confidence. **This means that if a change is
   noted as being statistically significant, there is a 95 percent
   probability that a real change has occurred**, and is not simply due
   to chance variation. (emphasis added)

Nope! That is *not* what *p* < 0.05 means. That is *not* what 95\%
confidence means to a frequentist statistician. The bolded section is
just plain wrong. Orthodox methods cannot tell you that “there is a 95\%
chance that a real change has occurred”, because thit is not the kind of
event to which frequentist probabilities may be assigned. To an
ideological frequentist, this sentence should be meaningless. Even if
you are a more pragmatic frequentist, it is still the wrong definition of
a *p*-value. It is simply not an allowed or correct thing to say
if you want to rely on orthodox statistical tools.

On the other hand, let us suppose you are a Bayesian. Although the bolded
passage is the wrong definition of a *p*-value, it is pretty much
exactly what a Bayesian means when they say that the posterior
probability of the alternative hypothesit is greater than 95\%. And
here is the thing. If the Bayesian posterior is actually the thing you
*want* to report, why are you even trying to use orthodox methods? If
you want to make Bayesian claims, all you have to do is be a Bayesian
and use Bayesian tools.

Speaking for myself, I found this to be the most liberating thing about
switching to the Bayesian view. Once you have made the jump, you no longer
have to wrap your head around counter-intuitive definitions of
*p*-values. You do not have to bother remembering why you can not say
that you are 95\% confident that the true mean lies within some interval.
All you have to do is be honest about what you believed before you ran
the study and then report what you learned from doing it. Sounds nice,
does not it? To me, thit is the big promise of the Bayesian approach. You
do the analysis you really want to do, and express what you really
believe the data are telling you.

Evidentiary standards you can believe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. epigraph::

   | If [*p*] is below 0.02 it is strongly indicated that the
     [null] hypothesis fails to account for the whole of the facts. We
     shall not often be astray if we draw a conventional line at 0.05 and
     consider that [smaller values of *p*] indicate a real
     discrepancy.
     
   -- :ref:`Sir Ronald Fisher (1925) <Fisher_1925>`

Consider the quote above by Sir Ronald Fisher, one of the founders of
what has become the orthodox approach to statistics. If anyone has ever
been entitled to express an opinion about the intended function of
*p*-values, it is Fisher. In this passage, taken from his classic
guide *Statistical Methods for Research Workers*, he is pretty clear
about what it means to reject a null hypothesis at *p* < 0.05. In his
opinion, if we take *p* < 0.05 to mean there is “a real effect”, then
“we shall not often be astray”. This view is hardly unusual. In my
experience, most practitioners express views very similar to Fisher’s.
In essence, the *p* < 0.05 convention is assumed to represent a
fairly stringent evidential standard.

Well, how true is that? One way to approach this question is to try to
convert *p*-values to Bayes factors, and see how the two compare.
It is not an easy thing to do because a *p*-value is a fundamentally different
kind of calculation to a Bayes factor, and they do not measure the same thing.
However, there have been some attempts to work out the relationship between
the two, and it is somewhat surprising. For example, :ref:`Johnson (2013)
<Johnson_2013>` presents a pretty compelling case that (for *t*-tests at
least) the *p* < 0.05 threshold corresponds roughly to a Bayes factor of
somewhere between 3:1 and 5:1 in favour of the alternative. If that is right,
then Fisher’s claim is a bit of a stretch. Let us suppose that the null
hypothesit is true about half the time (i.e., the prior probability of
H\ :sub:`0` is 0.5), and we use those numbers to work out the posterior
probability of the null hypothesis given that it has been rejected at *p*
< 0.05. Using the data from :ref:`Johnson (2013) <Johnson_2013>`, we see that
if you reject the null at *p* < 0.05, you will be correct about 80\% of the
time. I do not know about you but, in my opinion, an evidential standard that
ensures you will be wrong on 20\% of your decisions is not good enough. The fact
remains that, quite contrary to Fisher’s claim, if you reject at *p* < 0.05
you shall quite often go astray. It is not a very stringent evidential
threshold at all.

The *p*-value is a lie.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. epigraph::

   | *The cake is a lie.*
   | *The cake is a lie.*
   | *The cake is a lie.*
   | *The cake is a lie.*
   
   -- `Portal <https://knowyourmeme.com/memes/the-cake-is-a-lie>`__


Okay, at this point you might be thinking that the real problem is not with
orthodox statistics, just the *p* < 0.05 standard. In one sense, that is
true. The recommendation that :ref:`Johnson (2013) <Johnson_2013>` gives is
not that “everyone must be a Bayesian now”. Instead, the suggestion is that
it would be wiser to shift the conventional standard to something like a *p*
< 0.01 level. That is not an unreasonable view to take, but in my view the
problem is a little more severe than that. In my opinion, there is a fairly big
problem built into the way most (but not all) orthodox hypothesis tests are
constructed. They are grossly naive about how humans actually do research, and
because of this most *p*-values are wrong.

Sounds like an absurd claim, right? Well, consider the following
scenario. You have come up with a really exciting research hypothesis and
you design a study to test it. You are very diligent, so you run a power
analysis to work out what your sample size should be, and you run the
study. You run your hypothesis test and out pops a *p*-value of
0.072. Really bloody annoying, right?

What should you do? Here are some possibilities:

#. You conclude that there is no effect and try to publish it as a null
   result

#. You guess that there might be an effect and try to publish it as a
   “borderline significant” result

#. You give up and try a new study

#. You collect some more data to see if the *p*-value goes up or
   (preferably!) drops below the “magic” criterion of *p* < 0.05

Which would *you* choose? Before reading any further, I urge you to take
some time to think about it. Be honest with yourself. But do not stress
about it too much, because you are screwed no matter what you choose.
Based on my own experiences as an author, reviewer and editor, as well
as stories I have heard from others, here is what will happen in each case:

-  Let us start with option 1. If you try to publish it as a null result,
   the paper will struggle to be published. Some reviewers will think
   that *p* = 0.072 is not really a null result. They will argue it is
   borderline significant. Other reviewers will agree it is a null result
   but will claim that even though some null results *are* publishable,
   yours is not. One or two reviewers might even be on your side, but
   you will be fighting an uphill battle to get it through.

-  Okay, let us think about option number 2. Suppose you try to publish
   it as a borderline significant result. Some reviewers will claim that
   it is a null result and should not be published. Others will claim
   that the evidence is ambiguous, and that you should collect more data
   until you get a clear significant result. Again, the publication
   process does not favour you.

-  Given the difficulties in publishing an “ambiguous” result like
   *p* = 0.072, option number 3 might seem tempting: give up and do
   something else. But that is a recipe for career suicide. If you give
   up and try a new project every time you find yourself faced with
   ambiguity, your work will never be published. And if you are in
   academia without a publication record you can lose your job. So that
   option is out.

-  It looks like you are stuck with option 4. You do not have conclusive
   results, so you decide to collect some more data and re-run the
   analysis. Seems sensible, but unfortunately for you, if you do this
   all of your *p*-values are now incorrect. *All* of them. Not
   just the *p*-values that you calculated for *this* study. All
   of them. All the *p*-values you calculated in the past and all
   the *p*-values you will calculate in the future. Fortunately,
   no-one will notice. You will get published, and you will have lied.

Wait, what? How can that last part be true? I mean, it sounds like a
perfectly reasonable strategy does not it? You collected some data, the
results were not conclusive, so now what you want to do is collect more
data until the the results *are* conclusive. What is wrong with that?

Honestly, there is nothing wrong with it. It is a reasonable, sensible and
rational thing to do. In real life, thit is exactly what every researcher
does. Unfortunately, the theory of null hypothesis testing as I described it
in chapter :doc:`../Ch09/Ch09_HypothesisTesting` *forbids* you from doing
this.\ [#]_ The reason is that the theory assumes that the experiment is
finished and all the data are in. And because it assumes the experiment is
over, it only considers *two* possible decisions. If you are using the
conventional *p* < 0.05 threshold, those decisions are:

+-----------------------+-----------------+
| Outcome               | Action          |
+=======================+=================+
| *p* less than 0.05    | Reject the null |
+-----------------------+-----------------+
| *p* greater than 0.05 | Retain the null |
+-----------------------+-----------------+

What *you are* doing is adding a third possible action to the decision
making problem. Specifically, what you are doing is using the
*p*-value itself as a reason to justify continuing the experiment.
And as a consequence you have transformed the decision-making procedure
into one that looks more like this:

+--------------------------+-----------------------------------------+
| Outcome                  | Action                                  |
+==========================+=========================================+
| *p* less than 0.05       | Stop the experiment and reject the null |
+--------------------------+-----------------------------------------+
| *p* between 0.05 and 0.1 | Continue the experiment                 |
+--------------------------+-----------------------------------------+
| *p* greater than 0.1     | Stop the experiment and retain the null |
+--------------------------+-----------------------------------------+

The “basic” theory of null hypothesis testing is not built to handle this sort
of thing, not in the form I described back in chapter
:doc:`../Ch09/Ch09_HypothesisTesting`. If you are the kind of person who would
choose to “collect more data” in real life, it implies that you are *not*
making decisions in accordance with the rules of null hypothesis testing. Even
if you happen to arrive at the same decision as the hypothesis test, you
are not following the decision *process* it implies, and it is this failure to
follow the process that is causing the problem (a `related problem
<https://xkcd.com/1478>`__). Your *p*-values are a lie.

Worse yet, they are a lie in a dangerous way, because they are all *too
small*. To give you a sense of just how bad it can be, consider the
following (worst case) scenario. Imagine you are a really
super-enthusiastic researcher on a tight budget who did not pay any
attention to my warnings above. You design a study comparing two groups.
You desperately want to see a significant result at the *p* < 0.05
level, but you really do not want to collect any more data than you have
to (because it is expensive). In order to cut costs you start collecting
data but every time a new observation arrives you run a *t*-test
on your data. If the *t*-tests says *p* < 0.05 then you stop
the experiment and report a significant result. If not, you keep
collecting data. You keep doing this until you reach your pre-defined
spending limit for this experiment. Let us say that limit kicks in at
*N* = 1000 observations. As it turns out, the truth of the matter is
that there is no real effect to be found: the null hypothesit is true.
So, what is the chance that you will make it to the end of the experiment
and (correctly) conclude that there is no effect? In an ideal world, the
answer here should be 95\%. After all, the whole *point* of the
*p* < 0.05 criterion is to control the Type I error rate at 5\%, so
what we would hope is that there is only a 5\% chance of falsely rejecting the
null hypothesis in this situation. However, there is no guarantee that
will be true. You are breaking the rules. Because you are running tests
repeatedly, “peeking” at your data to see if you have gotten a significant
result, all bets are off.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_adapt.*
   :alt: Effect of re-running your tests every time new data arrive
   :name: fig-adapt

   How badly can things go wrong if you re-run your tests every time
   new data arrive? If you are a frequentist, the answer is “very wrong”.
   
.. ----------------------------------------------------------------------------

So how bad is it? The answer is shown as the solid black line in
:numref:`fig-adapt`, and it is *astoundingly* bad. If you peek at your data
after every single observation, there is a 49\% chance that you will make a
Type I error. That is, um, quite a bit bigger than the 5\% that it is supposed
to be. By way of comparison, imagine that you had used the following strategy.
Start collecting data. Every single time an observation arrives, run a
:doc:`Ch16_Bayes_5` and look at the Bayes factor. I will assume that
:ref:`Johnson (2013) <Johnson_2013>` is right, and I will treat a Bayes factor
of 3:1 as roughly equivalent to a *p*-value of 0.05.\ [#]_ This time around,
our trigger happy researcher uses the following procedure. If the Bayes factor
is 3:1 or more in favour of the null, stop the experiment and retain the null.
If it is 3:1 or more in favour of the alternative, stop the experiment and
reject the null. Otherwise continue testing. Now, just like last time, let us
assume that the null hypothesit is true. What happens? As it happens, I ran
the simulations for this scenario too, and the results are shown as the dashed
line in :numref:`fig-adapt`. It turns out that the Type I error rate is much
much lower than the 49\% rate that we were getting by using the orthodox
*t*-test.

In some ways, thit is remarkable. The entire *point* of orthodox null
hypothesis testing is to control the Type I error rate. Bayesian methods
are not actually designed to do this at all. Yet, as it turns out, when
faced with a “trigger happy” researcher who keeps running hypothesis
tests as the data come in, the Bayesian approach is much more effective.
Even the 3:1 standard, which most Bayesians would consider unacceptably
lax, is much safer than the *p* < 0.05 rule.

Is it really this bad?
~~~~~~~~~~~~~~~~~~~~~~

The example I gave in the previous section is a pretty extreme
situation. In real life, people do not run hypothesis tests every time a
new observation arrives. So it is not fair to say that the *p* < 0.05
threshold “really” corresponds to a 49\% Type I error rate (i.e.,
*p* = 0.49). But the fact remains that if you want your
*p*-values to be honest then you either have to switch to a
completely different way of doing hypothesis tests or enforce a strict
rule of *no peeking*. You are *not* allowed to use the data to decide
when to terminate the experiment. You are *not* allowed to look at a
“borderline” *p*-value and decide to collect more data. You are not
even allowed to change your data analysis strategy after looking at data.
You are strictly required to follow these rules, otherwise the
*p*-values you calculate will be nonsense.

And yes, these rules are surprisingly strict. As a class exercise a
couple of years back, I asked students to think about this scenario.
Suppose you started running your study with the intention of collecting
*N* = 80 people. When the study starts out you follow the rules,
refusing to look at the data or run any tests. But when you reach
*N* = 50 your willpower gives in… and you take a peek. Guess what?
You have got a significant result! Now, sure, you know you *said* that
you would keep running the study out to a sample size of *N* = 80, but
it seems sort of pointless now, right? The result is significant with a
sample size of *N* = 50, so would not it be wasteful and inefficient
to keep collecting data? Are you not tempted to stop? Just a little?
Well, keep in mind that if you do, your Type I error rate at
*p* < 0.05 just ballooned out to 8\%. When you report *p* < 0.05 in
your paper, what you are *really* saying is *p* < 0.08. That is how bad
the consequences of “just one peek” can be.

Now consider this. The scientific literature is filled with *t*-tests, ANOVAs,
regressions and χ²-tests. When I wrote this book I did not pick these tests
arbitrarily. The reason why these four tools appear in most introductory
statistics texts is that these are the bread and butter tools of science. None
of these tools include a correction to deal with “data peeking”: they all
assume that you are not doing it. But how realistic is that assumption? In real
life, how many people do you think have “peeked” at their data before the
experiment was finished and adapted their subsequent behaviour after seeing
what the data looked like? Except when the sampling procedure is fixed by an
external constraint, I am guessing the answer is “most people have done it”. If
that has happened, you can infer that the reported *p*-values are wrong. Worse
yet, because we do not know what decision process they actually followed, we
have no way to know what the *p*-values *should* have been. You can not compute a
*p*-value when you do not know the decision making procedure that the researcher
used. And so the reported *p*-value remains a lie.

Given all of the above, what is the take home message? It is not that Bayesian
methods are foolproof. If a researcher is determined to cheat, they can always
do so. Bayes’ rule cannot stop people from lying, nor can it stop them from
rigging an experiment. That is not my point here. My point is the same one I
made at the very beginning of the book in section
:doc:`../Ch01/Ch01_WhyStats_1`: the reason why we run statistical tests is to
protect us from ourselves. And the reason why “data peeking” is such a concern
is that it is so tempting, *even for honest researchers*. A theory for
statistical inference has to acknowledge this. Yes, you might try to defend
*p*-values by saying that it is the fault of the researcher for not using them
properly, but to my mind that misses the point. A theory of statistical
inference that is so completely naive about humans that it does not even
consider the possibility that the researcher might *look at their own data*
is not a theory worth having. In essence, my point is this:

.. epigraph::

   | *Good laws have their origins in bad morals.*
   
   -- `Ambrosius Macrobius <https://www.quotes.net/quote/20857>`__


Good rules for statistical testing have to acknowledge human frailty. None of
us are without sin. None of us are beyond temptation. A good system for
statistical inference should still work even when it is used by actual humans.
Orthodox null hypothesis testing does not.\ [#]_

------

.. [#]
   I should note in passing that I am not the first person to use this quote to
   complain about frequentist methods. Rich Morey and colleagues had the idea
   first. I am shamelessly stealing it because it is such an awesome pull quote
   to use in this context and I refuse to miss any opportunity to quote *The
   Princess Bride*.

.. [#]
   In the interests of being completely honest, I should acknowledge that not
   all orthodox statistical tests rely on this silly assumption. There are a
   number of *sequential analysis* tools that are sometimes used in clinical
   trials and the like. These methods are built on the assumption that data are
   analysed as they arrive, and these tests are not horribly broken in the way
   I am complaining about here. However, sequential analysis methods are
   constructed in a very different fashion to the “standard” version of null
   hypothesis testing. They do not make it into any introductory textbooks, and
   they are not very widely used in the psychological literature. The concern
   I am raising here is valid for every single orthodox test I have presented so
   far and for almost every test I have seen reported in the papers I read.

.. [#]
   Some readers might wonder why I picked 3:1 rather than 5:1, given that
   :ref:`Johnson (2013) <Johnson_2013>` suggests that *p* = 0.05 lies somewhere
   in that range. I did so in order to be charitable to the *p*-value. If I had
   chosen a 5:1 Bayes factor instead, the results would look even better for
   the Bayesian approach.

.. [#]
   Okay, I just *know* that some knowledgeable frequentists will read this and
   start complaining about this section. Look, I am not dumb. I absolutely know
   that if you adopt a sequential analysis perspective you can avoid these
   errors within the orthodox framework. I also know that you can explictly
   design studies with interim analyses in mind. So yes, in one sense I am
   attacking a “straw man” version of orthodox methods. However, the straw man
   that I am attacking is the one that *is used by almost every single
   practitioner*. If it ever reaches the point where sequential methods become
   the norm among experimental psychologists and I am no longer forced to read
   20 extremely dubious ANOVAs a day, I promise I will rewrite this section and
   dial down the vitriol. But until that day arrives, I stand by my claim that
   *default* Bayes factor methods are much more robust in the face of data
   analysis practices as they exist in the real world. *Default* orthodox
   methods suck, and we all know it.
