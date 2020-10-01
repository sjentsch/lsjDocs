.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Different ways to specify contrasts
-----------------------------------

In the previous section, I showed you a method for converting a factor
into a collection of contrasts. In the method I showed you we specify a
set of binary variables in which we defined a table like this one:

============== ================ ================
``drug``       ``druganxifree`` ``drugjoyzepam``
============== ================ ================
``"placebo"``  0                0
``"anxifree"`` 1                0
``"joyzepam"`` 0                1
============== ================ ================

Each row in the table corresponds to one of the factor levels, and each column
corresponds to one of the contrasts. This table, which always has one more row
than columns, has a special name. It is called a **contrast matrix**. However,
there are lots of different ways to specify a contrast matrix. In this section
I discuss a few of the standard contrast matrices that statisticians use and
how you can use them in jamovi. If you’re planning to read the section on
unbalanced ANOVA later on (Section `Factorial ANOVA 3: unbalanced designs
<Ch14_ANOVA2_10.html#factorial-anova-3-unbalanced-designs>`__), it’s worth
reading this section carefully. If not, you can get away with skimming it,
because the choice of contrasts doesn’t matter much for balanced designs.

Treatment contrasts
~~~~~~~~~~~~~~~~~~~

In the particular kind of contrasts that I’ve described above, one level
of the factor is special, and acts as a kind of “baseline” category
(i.e., ``placebo`` in our example), against which the other two are
defined. The name for these kinds of contrasts is **treatment
contrasts**, also known as “dummy coding”. In this contrast each level
of the factor is compared to a base reference level, and the base
reference level is the value of the intercept.

The name reflects the fact that these contrasts are quite natural and
sensible when one of the categories in your factor really is special
because it actually does represent a baseline. That makes sense in our
clinical trial example. The ``placebo`` condition corresponds to the
situation where you don’t give people any real drugs, and so it’s
special. The other two conditions are defined in relation to the
placebo. In one case you replace the placebo with Anxifree, and in the
other case your replace it with Joyzepam.

The table shown above is a matrix of treatment contrasts for a factor
that has 3 levels. But suppose I want a matrix of treatment contrasts
for a factor with 5 levels? You would set this out like this:

.. code-block:: rout

   Level   2 3 4 5
     1     0 0 0 0
     2     1 0 0 0
     3     0 1 0 0
     4     0 0 1 0
     5     0 0 0 1

In this example, the first contrast is level 2 compared with level 1,
the second contrast is level 3 compared with level 1, and so on. Notice
that, by default, the *first* level of the factor is always treated as
the baseline category (i.e., it’s the one that has all zeros and doesn’t
have an explicit contrast associated with it). In jamovi you can change
which category is the first level of the factor by manipulating the
order of the levels of the variable shown in the ‘Data Variable’ window
(double click on the name of the variable in the spreadsheet column to
bring up the ‘Data Variable’ view.

Helmert contrasts
~~~~~~~~~~~~~~~~~

Treatment contrasts are useful for a lot of situations. However, they
make most sense in the situation when there really is a baseline
category, and you want to assess all the other groups in relation to
that one. In other situations, however, no such baseline category
exists, and it may make more sense to compare each group to the mean of
the other groups. This is where we meet **Helmert contrasts**, generated
by the ‘helmert’ option in the jamovi ‘ANOVA’ - ‘Contrasts’ selection
box. The idea behind Helmert contrasts is to compare each group to the
mean of the “previous” ones. That is, the first contrast represents the
difference between group 2 and group 1, the second contrast represents
the difference between group 3 and the mean of groups 1 and 2, and so
on. This translates to a contrast matrix that looks like this for a
factor with five levels:

.. code-block:: rout

   1   -1   -1   -1   -1
   2    1   -1   -1   -1
   3    0    2   -1   -1
   4    0    0    3   -1
   5    0    0    0    4

One useful thing about Helmert contrasts is that every contrast sums to zero
(i.e., all the columns sum to zero). This has the consequence that, when we
interpret the ANOVA as a regression, the intercept term corresponds to the
grand mean µ\ :sub:`..` if we are using Helmert contrasts. Compare this to
treatment contrasts, in which the intercept term corresponds to the group mean
for the baseline category. This property can be very useful in some situations.
It doesn’t matter very much if you have a balanced design, which we’ve been
assuming so far, but it will turn out to be important later when we consider
unbalanced designs in Section `Factorial ANOVA 3: unbalanced designs
<Ch14_ANOVA2_10.html#factorial-anova-3-unbalanced-designs>`__. In fact, the
main reason why I’ve even bothered to include this section is that contrasts
become important if you want to understand unbalanced ANOVA.

Sum to zero contrasts
~~~~~~~~~~~~~~~~~~~~~

The third option that I should briefly mention are “sum to zero” contrasts,
called “Simple” contrasts in jamovi, which are used to construct pairwise
comparisons between groups. Specifically, each contrast encodes the difference
between one of the groups and a baseline category, which in this case
corresponds to the first group:

.. code-block:: rout

   1   -1   -1   -1   -1
   2    1    0    0    0
   3    0    1    0    0
   4    0    0    1    0
   5    0    0    0    1

Much like Helmert contrasts, we see that each column sums to zero, which
means that the intercept term corresponds to the grand mean when ANOVA
is treated as a regression model. When interpreting these contrasts, the
thing to recognise is that each of these contrasts is a pairwise
comparison between group 1 and one of the other four groups.
Specifically, contrast 1 corresponds to a “group 2 minus group 1”
comparison, contrast 2 corresponds to a “group 3 minus group 1”
comparison, and so on.\ [#]_

Optional contrasts in jamovi
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

jamovi also comes with a variety of options that can generate different
kinds of contrasts in ANOVA. These can be found in the ‘Contrasts’
option in the main ANOVA analysis window, where the following contrast
types are listed:

+---------------+-----------------------------------------------------+
| Contrast type |                                                     |
+===============+=====================================================+
| Deviation     | Compares the mean of each level (except a reference |
|               | category) to the mean of all of the levels (grand   |
|               | mean).                                              |
+---------------+-----------------------------------------------------+
| Simple        | Like the treatment contrasts, the simple contrast   |
|               | compares the mean of each level to the mean of a    |
|               | specified level.                                    |
+---------------+-----------------------------------------------------+
|               | This type of contrast is useful when there is a     |
|               | control group. By default the first category is the |
|               | reference. However, with a simple contrast the      |
|               | intercept is the grand mean of all the levels of    |
|               | the factors.                                        |
+---------------+-----------------------------------------------------+
| Difference    | Compares the mean of each level (except the first)  |
|               | to the mean of previous levels. (Sometimes called   |
|               | reverse Helmert contrasts).                         |
+---------------+-----------------------------------------------------+
| Helmert       | Compares the mean of each level of the factor       |
|               | (except the last) to the mean of subsequent levels. |
+---------------+-----------------------------------------------------+
| Repeated      | Compares the mean of each level (except the last)   |
|               | to the mean of the subsequent level.                |
+---------------+-----------------------------------------------------+
| Polynomial    | Compares the linear effect and quadratic effect.    |
|               | The first degree of freedom contains the linear     |
|               | effect across all categories;                       |
+---------------+-----------------------------------------------------+
|               | the second degree of freedom, the quadratic effect. |
|               | These contrasts are often used to estimate          |
|               | polynomial trends.                                  |
+---------------+-----------------------------------------------------+

------

.. [#]
   What’s the difference between treatment and simple contrasts, I hear
   you ask? Well, as a basic example consider a gender main effect, with
   m=0 and f=1. The coefficient corresponding to the treatment contrast
   will measure the difference in mean between females and males, and
   the intercept would be the mean of the males. However, with a simple
   contrast, i.e., m=-1 and f=1, the intercept is the average of the
   means and the main effect is the difference of each group mean from
   the intercept.

