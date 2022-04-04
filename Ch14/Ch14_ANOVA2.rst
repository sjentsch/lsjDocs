.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Factorial ANOVA
===============

.. toctree::
   :maxdepth: 1
   :hidden:
   
   Ch14_ANOVA2_01
   Ch14_ANOVA2_02
   Ch14_ANOVA2_03
   Ch14_ANOVA2_04
   Ch14_ANOVA2_05
   Ch14_ANOVA2_06
   Ch14_ANOVA2_07
   Ch14_ANOVA2_08
   Ch14_ANOVA2_09
   Ch14_ANOVA2_10
   Ch14_ANOVA2_11


Over the course of the last few chapters we have done quite a lot. We have
looked at statistical tests you can use when you have one nominal predictor
variable |nominal| with two groups (e.g. the *t*-test, chapter :doc:`Comparing
two means <../Ch11/Ch11_tTest>`) or with three or more groups (e.g. in chapter
:doc:`Comparing several means: One-way ANOVA <../Ch13/Ch13_ANOVA>`). The
chapter on :doc:`Correlation and linear regression <../Ch12/Ch12_Regression>`
introduced a powerful new idea, that is building statistical models with
*multiple* continuous predictor variables |continuous| used to explain a single
outcome variable |continuous|. For instance, a regression model could be used
to predict the number of errors a student makes in a reading comprehension test
based on the number of hours they studied for the test and their score on a
standardised IQ test.

The goal in this chapter is to extend the idea of using multiple predictors
into the ANOVA framework. For instance, suppose we were interested in using the
reading comprehension test to measure student achievements in three different
schools, and we suspect that girls and boys are developing at different rates
(and so would be expected to have different performance on average). Each
student is classified in two different ways: on the basis of their gender and
on the basis of their school. What we’d like to do is analyse the reading
comprehension scores in terms of *both* of these grouping variables |nominal|.
The tool for doing so is generically referred to as **factorial ANOVA**.
However, since we have two grouping variables |nominal|, we sometimes refer to
the analysis as a two-way ANOVA, in contrast to the one-way ANOVAs that we ran
in chapter :doc:`Comparing several means (one-way ANOVA) <../Ch13/Ch13_ANOVA>`.

.. ----------------------------------------------------------------------------

.. |continuous|                       image:: ../_images/variable-continuous.*
   :width: 16px
 
.. |nominal|                          image:: ../_images/variable-nominal.*
   :width: 16px
