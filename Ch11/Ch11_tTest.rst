.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Comparing two means
===================

.. toctree::
   :hidden:

   Ch11_tTest_01
   Ch11_tTest_02
   Ch11_tTest_03
   Ch11_tTest_04
   Ch11_tTest_05
   Ch11_tTest_06
   Ch11_tTest_07
   Ch11_tTest_08
   Ch11_tTest_09
   Ch11_tTest_10


In chapter :doc:`Categorical data analysis <../Ch10/Ch10_ChiSquare>` we covered
the situation when your outcome variable is nominal scale |nominal| and your
predictor variable is also nominal scale |nominal|. Lots of real world
situations have that character, and so you’ll find that χ²-tests in particular
are quite widely used. However, you’re much more likely to find yourself in a
situation where your outcome variable is interval scale or higher |continuous|,
and what you’re interested in is whether the average value of the outcome
variable is higher in one group or another. For instance, a psychologist might
want to know if anxiety levels are higher among parents than non-parents, or if
working memory capacity is reduced by listening to music (relative to not
listening to music). In a medical context we might want to know if a new drug
increases or decreases blood pressure. An agricultural scientist might want to
know whether adding phosphorus to Australian native plants will kill
them.\ [#]_ In all these situations our outcome variable is a fairly continuous
|continuous|, interval or ratio scale variable, and our predictor is a binary
“grouping” variable |nominal|. In other words, we want to compare the means of
the two groups.

The standard answer to the problem of comparing means is to use a *t*-test, of
which there are several varieties depending on exactly what question you want
to solve. As a consequence, the majority of this chapter focuses on different
types of *t*-test: :doc:`one sample *t*-tests <Ch11_tTest_02>` are discussed
first, followed by two different flavours of the independent samples *t*-test:
The :doc:`Student test <Ch11_tTest_03>` assumes that the groups have the same
standard deviation, the :doc:`Welch test <Ch11_tTest_04>` does not. Afterwards,
:doc:`paired samples *t*-tests <Ch11_tTest_05>` are discussed. We’ll then talk
about :doc:`One-sided tests <Ch11_tTest_06>` and, after that, we’ll talk a bit
about Cohen’s *d*, which is the standard measure of :doc:`effect size
<Ch11_tTest_07>` for a *t*-test. The later sections of the chapter focus on the
assumptions of the *t*-tests, especially :doc:`normality <Ch11_tTest_08>` and
possible :doc:`remedies <Ch11_tTest_09>` if they are violated. However, before
discussing any of these useful things, we’ll start with a discussion of the
*z*-test.
   
------

.. [#]
   Informal experimentation in my garden suggests that yes, it does. Australian
   natives are adapted to low phosphorus levels relative to everywhere else on
   Earth, so if you’ve bought a house with a bunch of exotics and you want to
   plant natives, keep them separate; nutrients to European plants are poison
   to Australian ones.

.. ----------------------------------------------------------------------------

.. |continuous|                       image:: ../_images/variable-continuous.*
   :width: 16px
 
.. |nominal|                          image:: ../_images/variable-nominal.*
   :width: 16px   
