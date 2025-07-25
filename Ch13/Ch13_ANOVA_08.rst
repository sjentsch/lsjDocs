.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

The Friedman non-parametric repeated measures ANOVA test
--------------------------------------------------------

The Friedman test is a non-parametric version of a repeated measures ANOVA and
can be used instead of the Kruskall-Wallis test when testing for differences
between three or more groups |nominal| where the same participants are in each
group, or each participant is closely matched with participants in other
conditions. If the dependent variable is ordinal |ordinal|, or if the
assumption of normality is not met, then the Friedman test can be used.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig13-14.*
   :alt: ``Repeated Measures ANOVA (Non-parametric)`` dialogue box in jamovi
   :name: fig13-14

   ``Repeated Measures ANOVA (Non-parametric)`` dialogue box in jamovi
   
.. ----------------------------------------------------------------------------

As with the Kruskall-Wallis test, the underlying mathematics is complicated,
and will not be presented here. For the purpose of this book, it is sufficient
to note that jamovi calculates the tie-corrected version of the Friedman test,
and in :numref:`fig13-14` there is an example using the Broca’s Aphasia data we
have already looked at.

It is pretty straightforward to run a Friedman test in jamovi. Just select
``Analyses`` → ``ANOVA`` → ``Repeated Measures ANOVA (Non-parametric)``,
as in :numref:`fig13-14`. Then highlight and transfer the names of the repeated
measures variables you wish to compare (``Speech``, ``Conceptual``, ``Syntax``)
into the ``Measures:`` text box. To produce descriptive statistics (means and
medians) for the three repeated measures variables, click on the
``Descriptives`` button.

The jamovi results show descriptive statistics, χ²-value, degrees of freedom,
and the *p*-value (:numref:`fig13-14`). Since the *p*-value is less than the
level conventionally used to determine significance (*p* < 0.05), we can
conclude that Broca’s Aphasics perform reasonably well on speech production
(*Md* [median] = 7.5) and language comprehension (*Md* = 6.5) tasks. However,
their performance was considerably worse on the syntax task (*Md* = 4.5), with
a significant difference in post-hoc tests between Speech and Syntax task
performance.

.. ----------------------------------------------------------------------------

.. |nominal|                           image:: ../_images/variable-nominal.*
   :width: 16px
 
.. |ordinal|                           image:: ../_images/variable-ordinal.*
   :width: 16px
