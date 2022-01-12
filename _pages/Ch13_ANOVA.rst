.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Comparing several means (one-way ANOVA)
=======================================

This chapter introduces one of the most widely used tools in
psychological statistics, known as “the analysis of variance”, but
usually referred to as ANOVA. The basic technique was developed by Sir
Ronald Fisher in the early 20th century and it is to him that we owe the
rather unfortunate terminology. The term ANOVA is a little misleading,
in two respects. Firstly, although the name of the technique refers to
variances, ANOVA is concerned with investigating differences in means.
Secondly, there are several different things out there that are all
referred to as ANOVAs, some of which have only a very tenuous connection
to one another. Later on in the book we’ll encounter a range of
different ANOVA methods that apply in quite different situations, but
for the purposes of this chapter we’ll only consider the simplest form
of ANOVA, in which we have several different groups of observations, and
we’re interested in finding out whether those groups differ in terms of
some outcome variable of interest. This is the question that is
addressed by a **one-way ANOVA**.

The structure of this chapter is as follows: in Section `An illustrative data
set <Ch13_ANOVA_01.html#an-illustrative-data-set>`__ I’ll introduce a
fictitious data set that we’ll use as a running example throughout the chapter.
After introducing the data, I’ll describe the mechanics of how a one-way
ANOVA actually works `How ANOVA works <Ch13_ANOVA_02.html#how-anova-works>`__
and then focus on `how you can run one in jamovi
<Ch13_ANOVA_03.html#running-an-anova-in-jamovi>`__. These two sections are the
core of the chapter. The remainder of the chapter discusses a range of
important topics that inevitably arise when running an ANOVA, namely how to
calculate `effect sizes <Ch13_ANOVA_04.html#effect-size>`__, and `post-hoc
tests and corrections for multiple comparisons
<Ch13_ANOVA_05.html#multiple-comparisons-and-post-hoc-tests>`__. Afterwards, we 
will talk about the `assumptions the ANOVA relies upon
<Ch13_ANOVA_06.html#assumptions-of-the-one-way-anova>`__, how to check those
assumptions and some of the things you can do if the assumptions are violated.
Then we’ll cover `repeated measures ANOVA
<Ch13_ANOVA_07.html#repeated-measures-one-way-anova>`__ and it's non-parametric
equivalent, the `Friedman test
<Ch13_ANOVA_08.html#the-friedman-non-parametric-repeated-measures-anova-test>`__. 

At the end of the chapter we’ll talk a little about the `relationship between
ANOVA and other statistical tools
<Ch13_ANOVA_09.html#on-the-relationship-between-anova-and-the-student-t-test>`__.

.. toctree::
   :hidden:
   
   Ch13_ANOVA_01
   Ch13_ANOVA_02
   Ch13_ANOVA_03
   Ch13_ANOVA_04
   Ch13_ANOVA_05
   Ch13_ANOVA_06
   Ch13_ANOVA_07
   Ch13_ANOVA_08
   Ch13_ANOVA_09
   Ch13_ANOVA_10
