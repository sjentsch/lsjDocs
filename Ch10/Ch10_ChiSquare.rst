.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Categorical data analysis
=========================

.. toctree::
   :maxdepth: 1
   :hidden:
   
   Ch10_ChiSquare_1
   Ch10_ChiSquare_2
   Ch10_ChiSquare_3
   Ch10_ChiSquare_4
   Ch10_ChiSquare_5
   Ch10_ChiSquare_6
   Ch10_ChiSquare_7
   Ch10_ChiSquare_8

Now that we have covered the basic theory behind hypothesis testing, it is time to
start looking at specific tests that are commonly used in psychology. So where
should we start? Not every textbook agrees on where to start, but I am going to
start with “χ² tests” (“Categorical data analysis”, this chapter) and
“*t*-tests” (chapter :doc:`../Ch11/Ch11_tTest`). Both of these tools are very
frequently used in scientific practice, and whilst they are not as powerful as
“regression” (chapter :doc:`../Ch12/Ch12_Regression`) and “Analysis of
Variance” (chapters :doc:`../Ch13/Ch13_ANOVA` and :doc:`../Ch14/Ch14_ANOVA2`)
they are much easier to understand. Finally, there is
:doc:`../Ch15/Ch15_FactorAnalysis` that aims to describe the  variability
among observed, correlated variables in terms of a lower number of unobserved
variables called factors or latent Variables.

The term “categorical data” in the title of this chapter is just another name
for “nominal scale data” |nominal|. It is nothing that we have not already
discussed, it is just that in the context of data analysis people tend to use
the term “categorical data” rather than “nominal scale data”. I do not know why.
In any case, **categorical data analysis** refers to a collection of tools that
you can use when your data are nominal scale |nominal|. Those tools are often
called “χ² tests” (pronounced “chi-square”, sometimes “chi-squared”). They
determine whether there is a statistically significant difference between
expected and observed frequencies and whether the observations follows a χ²
frequency distribution. However, there are a lot of different tools that can be
used for categorical data analysis, and this chapter covers only a few of the
more common ones.

.. ----------------------------------------------------------------------------

.. |nominal|                           image:: ../_images/variable-nominal.*
   :width: 16px
