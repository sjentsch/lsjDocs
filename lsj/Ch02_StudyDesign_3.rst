.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Assessing the reliability of a measurement
------------------------------------------

At this point we’ve thought a little bit about how to operationalise a
theoretical construct and thereby create a psychological measure. And
we’ve seen that by applying psychological measures we end up with
variables, which can come in many different types. At this point, we
should start discussing the obvious question: is the measurement any
good? We’ll do this in terms of two related ideas: *reliability* and
*validity*. Put simply, the **reliability** of a measure tells you how
*precisely* you are measuring something, whereas the validity of a
measure tells you how *accurate* the measure is. In this section I’ll
talk about reliability; we’ll talk about validity in Section `Assessing
the validity of a study <Ch02_StudyDesign_5.html#assessing-the-validity-of-a-study>`__.

Reliability is actually a very simple concept. It refers to the
repeatability or consistency of your measurement. The measurement of my
weight by means of a “bathroom scale” is very reliable. If I step on and
off the scales over and over again, it’ll keep giving me the same
answer. Measuring my intelligence by means of “asking my mum” is very
unreliable. Some days she tells me I’m a bit thick, and other days she
tells me I’m a complete idiot. Notice that this concept of reliability
is different to the question of whether the measurements are correct
(the correctness of a measurement relates to it’s validity). If I’m
holding a sack of potatos when I step on and off the bathroom scales the
measurement will still be reliable: it will always give me the same
answer. However, this highly reliable answer doesn’t match up to my true
weight at all, therefore it’s wrong. In technical terms, this is a
*reliable but invalid* measurement. Similarly, whilst my mum’s estimate
of my intelligence is a bit unreliable, she might be right. Maybe I’m
just not too bright, and so while her estimate of my intelligence
fluctuates pretty wildly from day to day, it’s basically right. That
would be an *unreliable but valid* measure. Of course, if my mum’s
estimates are too unreliable it’s going to be very hard to figure out
which one of her many claims about my intelligence is actually the right
one. To some extent, then, a very unreliable measure tends to end up
being invalid for practical purposes; so much so that many people would
say that reliability is necessary (but not sufficient) to ensure
validity.

Okay, now that we’re clear on the distinction between reliability and
validity, let’s have a think about the different ways in which we might
measure reliability:

-  **Test-retest reliability**. This relates to consistency over time.
   If we repeat the measurement at a later date do we get a the same
   answer?

-  **Inter-rater reliability**. This relates to consistency across
   people. If someone else repeats the measurement (e.g., someone else
   rates my intelligence) will they produce the same answer?

-  **Parallel forms reliability**. This relates to consistency across
   theoretically-equivalent measurements. If I use a different set of
   bathroom scales to measure my weight does it give the same answer?

-  **Internal consistency reliability**. If a measurement is constructed from
   lots of different parts that perform similar functions (e.g., a personality
   questionnaire result is added up across several questions) do the individual
   parts tend to give similar answers. We’ll look at this particular form of
   reliability later in the book, in Section `Internal consistency reliability
   analysis
   <Ch15_FactorAnalysis_5.html#internal-consistency-reliability-analysis>`__.

Not all measurements need to possess all forms of reliability. For
instance, educational assessment can be thought of as a form of
measurement. One of the subjects that I teach, *Computational Cognitive
Science*, has an assessment structure that has a research component and
an exam component (plus other things). The exam component is *intended*
to measure something different from the research component, so the
assessment as a whole has low internal consistency. However, within the
exam there are several questions that are intended to (approximately)
measure the same things, and those tend to produce similar outcomes. So
the exam on its own has a fairly high internal consistency. Which is as
it should be. You should only demand reliability in those situations
where you want to be measuring the same thing!

The “role” of variables: predictors and outcomes
------------------------------------------------

I’ve got one last piece of terminology that I need to explain to you
before moving away from variables. Normally, when we do some research we
end up with lots of different variables. Then, when we analyse our data,
we usually try to explain some of the variables in terms of some of the
other variables. It’s important to keep the two roles “thing doing the
explaining” and “thing being explained” distinct. So let’s be clear
about this now. First, we might as well get used to the idea of using
mathematical symbols to describe variables, since it’s going to happen
over and over again. Let’s denote the “to be explained” variable ``Y``,
and denote the variables “doing the explaining” as ``X_1``, ``X_2``, etc.

When we are doing an analysis we have different names for ``X`` and
``Y``, since they play different roles in the analysis. The classical names
for these roles are **independent variable** (IV) and **dependent variable**
(DV). The IV is the variable that you use to do the explaining (i.e., ``X``)
and the DV is the variable being explained (i.e., ``Y``). The logic behind
these names goes like this: if there really is a relationship between ``X``
and ``Y`` then we can say that ``Y`` depends on ``X``, and if we have
designed our study “properly” then ``X`` isn’t dependent on anything else.
However, I personally find those names horrible. They’re hard to remember and
they’re highly misleading because (a) the IV is never actually “independent of
everything else”, and (b) if there’s no relationship then the DV doesn’t
actually depend on the IV. And in fact, because I’m not the only person who
thinks that IV and DV are just awful names, there are a number of alternatives
that I find more appealing. The terms that I’ll use in this book are
**predictors** and **outcomes**. The idea here is that what you’re trying to
do is use ``X`` (the predictors) to make guesses about ``Y`` (the outcomes).\ [#]_
This is summarised in :numref:`tab-ivdv`.

.. _tab-ivdv:
.. table:: The terminology used to distinguish between different roles that a
   variable can play when analysing a data set. Note that this book will
   tend to avoid the classical terminology in favour of the newer names.

   ====================== ========================= ===========
   role of the variable   classical name            modern name
   ====================== ========================= ===========
   “to be explained”      dependent variable (DV)   outcome
   “to do the explaining” independent variable (IV) predictor
   ====================== ========================= ===========

------

.. [#]
   Annoyingly though, there’s a lot of different names used out there. I
   won’t list all of them – there would be no point in doing that –
   other than to note that “response variable” is sometimes used where
   I’ve used “outcome”. Sigh. This sort of terminological confusion is
   very common, I’m afraid.
