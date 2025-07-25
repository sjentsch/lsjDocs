.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Descriptive statistics separately for each group
------------------------------------------------

It is very commonly the case that you find yourself needing to look at 
descriptive statistics broken down by some grouping variable |nominal|. This is
pretty easy to do in jamovi. For instance, let us say I want to look at the
descriptive statistics for some clinical trial data, broken down separately by
``therapy`` type. This is a new data set, one that you have never seen before.
The data is stored in the |clinicaltrial|_ data set and we will use it a lot in
chapter :doc:`../Ch13/Ch13_ANOVA` (you can find a complete description of the
data at the start of that chapter). Let us load it and see what we have got
(:numref:`fig4-13`).

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig4-13.*
   :alt: Variables in |clinicaltrial|
   :name: fig4-13

   Screenshot of jamovi showing the variables stored in the
   |clinicaltrial|_ data set
      
.. ----------------------------------------------------------------------------

Evidently there were three drugs: a ``placebo``, something called ``anxifree``
and something called ``joyzepam``, and there were six people administered each
drug. There were nine people treated using cognitive behavioural therapy
(``CBT``) and nine people who received no psychological treatment
(``no.therapy``). And we can see from looking at the ``Descriptives`` of the
``mood.gain`` variable that most people did show a mood gain (mean = 0.88),
though without knowing what the scale is here it is hard to say much more than
that.

We can also go ahead and look at some other descriptive statistics, and this
time separately for each type of therapy. In jamovi, check ``Std. deviation``,
``Skewness`` and ``Kurtosis`` in the ``Statistics`` options. At the same
time, transfer the ``therapy`` variable into the ``Split by`` box, and you
should get something like :numref:`fig4-14`.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig4-14.*
   :alt: Variables in |clinicaltrial| split by therapy type
   :name: fig4-14

   Screenshot of jamovi showing ``Descriptives`` of the variables in the 
   |clinicaltrial|_ data set split by therapy type
      
.. ----------------------------------------------------------------------------

What if you have multiple grouping variables |nominal|? Suppose you want to
look at the average mood gain separately for all possible combinations of
``drug`` and ``therapy``. It is possible to do this by adding another variable,
``drug``, into the ``Split by`` box. Easy peasy, though sometimes if you split
too much there is not enough data in each breakdown combination to make
meaningful calculations. In this case jamovi tells you this by stating
something like ``NaN`` or ``Inf``.\ [#]_

------

.. [#]
   Sometimes jamovi will also present numbers in an unusual way. If a
   number is very small, or very large, then jamovi switches to an
   exponential form for numbers. For example **6.51e-4** is the same as
   saying that the decimal point is moved four places to the left, so the
   actual number is **0.000651**. If there is a plus sign, i.e., **6.51e+4**
   then the decimal point is moved to the right, i.e., **65 100.00**. Usually
   only very small or very large numbers are expressed in this way, for
   example **6.51e-16**, which would be quite unwieldy to write out in
   the normal way.

.. ----------------------------------------------------------------------------

.. |clinicaltrial|                     replace:: ``clinicaltrial``
.. _clinicaltrial:                     ../../_static/data/clinicaltrial.omv

.. |nominal|                           image:: ../_images/variable-nominal.*
   :width: 16px
