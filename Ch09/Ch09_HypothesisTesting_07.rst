.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Running the hypothesis test in practice
---------------------------------------

At this point some of you might be wondering if this is a “real” hypothesis
test, or just a toy example that I made up. It is real. In the previous
discussion I built the test from first principles, thinking that it was the
simplest possible problem that you might ever encounter in real life. However,
this test already exists. It is called the *binomial test*, and it is
implemented by jamovi as one of the statistical analyses available when you hit
the ``Frequencies`` button. To test the null hypothesis that the response
probability is one-half ``p = 0.5``,\ [#]_ and using data in which ``x = 62``
of ``n = 100`` people made the correct response, available in the
|binomialtest|_ data set, we get the results shown in :numref:`fig9-4`.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig9-4.*
   :alt: Binomial test analysis and results in jamovi
   :name: fig9-4

   Binomial test analysis and results in jamovi
      
.. ----------------------------------------------------------------------------

Right now, this output looks pretty unfamiliar to you, but you can see that it
is telling you more or less the right things. Specifically, the *p*-value of
\0.02 is less than the usual choice of α = 0.05, so you can reject the null. We
will talk a lot more about how to read this sort of output as we go along, and
after a while you will hopefully find it quite easy to read and understand.

------

.. [#]
   Note that the ``p`` here has nothing to do with a *p*-value. The ``p`` 
   argument in the jamovi binomial test corresponds to the probability of 
   making a correct response, according to the null hypothesis. In other words, 
   it is the *θ* value.

.. ----------------------------------------------------------------------------

.. |binomialtest|                      replace:: ``binomialtest``
.. _binomialtest:                      ../../_static/data/binomialtest.omv
