.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Assumption checking
-------------------

As with one-way ANOVA, the key assumptions of factorial ANOVA are
homogeneity of variance (all groups have the same standard deviation),
normality of the residuals, and independence of the observations. The
first two are things we can check for. The third is something that you
need to assess yourself by asking if there are any special relationships
between different observations, for example repeated measures where the
independent variable is time so there is a relationship between the
observations at time one and time two: observations at different time
points are from the *same* people. Additionally, if you are not using a
saturated model (e.g., if you have omitted the interaction terms) then
you are also assuming that the omitted terms are not important. Of course,
you can check this last one by running an ANOVA with the omitted terms
included and see if they are significant, so that is pretty easy. What
about homogeneity of variance and normality of the residuals? As it
turns out, these are pretty easy to check. It is no different to the
checks we did for a one-way ANOVA.

Homogeneity of variance
~~~~~~~~~~~~~~~~~~~~~~~

As mentioned in subsection :ref:`Checking the homogeneity of variance
assumption <homogeneity_of_variance_anova>`, it is a good idea to visually
inspect a plot of the standard deviations compared across different groups /
categories, and also see if the Levene test is consistent with the visual
inspection. The theory behind the Levene test was discussed in that section,
so I will not discuss it again. This test expects that you have a saturated model
(i.e., including all of the relevant terms), because the test is primarily
concerned with the within-group variance, and it does not really make a lot of
sense to calculate this any way other than with respect to the full model. The
Levene test can be specified under the ANOVA ``Assumption Checks`` →
``Homogeneity Tests`` option in jamovi, with the result shown as in
:numref:`fig14-10`. The fact that the Levene test is non-significant means
that, providing it is consistent with a visual inspection of the plot of
standard deviations, we can safely assume that the homogeneity of variance
assumption is not violated.

Normality of residuals
~~~~~~~~~~~~~~~~~~~~~~

As with one-way ANOVA we can test for the normality of residuals in a
straightforward fashion (see :ref:`Checking the normality assumption
<normality_anova>`). It is generally a good idea to examine the residuals
graphically using a QQ-plot (see :numref:`fig14-10`).

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig14-10.*
   :alt: Checking assumptions in an ANOVA model
   :name: fig14-10

   Checking assumptions in an ANOVA model
   
.. ----------------------------------------------------------------------------
