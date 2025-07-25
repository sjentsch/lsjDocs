.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Skew and kurtosis
-----------------

There are two more descriptive statistics that you will sometimes see reported
in the psychological literature: skew and kurtosis. In practice, neither one is
used anywhere near as frequently as the measures of central tendency and
variability that we have been talking about. Skew is pretty important, so you
do see it mentioned a fair bit, but I have actually never seen kurtosis
reported in a scientific article to date.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig4-11.*
   :alt: Illustration of skewness
   :name: fig4-11

   Illustration of skewness. On the left we have a negatively skewed data set
   (skewness = -.93), in the middle we have a data set with no skew (well,
   hardly any: skewness = -.006), and on the right we have a positively skewed
   data set (skewness = 0.93).
   
.. ----------------------------------------------------------------------------

Since it is the more interesting of the two, let us start by talking about the
**skewness**. Skewness is basically a measure of asymmetry and the easiest way
to explain it is by drawing some pictures. As :numref:`fig4-11` illustrates, if
the data tend to have a lot of extreme small values (i.e., the lower tail is
“longer” than the upper tail) and not so many extremely large values (left
panel) then we say that the data are *negatively skewed*. On the other hand, if
there are more extremely large values than extremely small ones (right panel)
we say that the data are *positively skewed*. That is the qualitative idea
behind skewness. If there are relatively more values that are far greater than
the mean, the distribution is positively skewed or right skewed, with a tail
stretching to the right. Negative or left skew is the opposite. A symmetric
distribution has a skewness of 0. The skewness value for a positively skewed
distribution is positive, and a negative value for a negatively skewed
distribution.

One formula for the skewness of a data set is as follows:

.. math:: \mbox{skewness}(X) = \frac{1}{N \hat{\sigma} ^ 3} \sum_{i = 1} ^ N (X_i - \bar{X}) ^ 3

*N* is the number of observations, *X̄* is the sample mean, and
:math:`\hat{\sigma}` is the standard deviation (the “divide by *N - 1*”
version, that is).

Perhaps more helpfully, you can use jamovi to calculate skewness: set the check
box ``Skewness`` in the ``Statistics`` options under ``Exploration`` →
``Descriptives``. For the ``afl.margins`` variable, the skewness figure is
**0.780**. If you divide the skewness estimate by the Std. error for skewness
you have an indication of how skewed the data is. Especially in small samples
(*N* < 50), one rule of thumb suggests that a value of 2 or less can mean that
the data is not very skewed, and a value of over 2 that there is sufficient
skew in the data to possibly limit its use in some statistical analyses. Though
there is no clear agreement on this interpretation. That said, this does
indicate that the ``afl.margins`` variable is somewhat skewed (0.780 / 0.183 =
\4.262).

The final measure that is sometimes referred to, though very rarely in
practice, is the **kurtosis** of a data set. Put simply, kurtosis is a measure
of how thin or fat the tails of a distribution are, as illustrated in
:numref:`fig4-12`. By convention, we say that the “normal curve” (black lines)
has zero kurtosis, and the degree of kurtosis is assessed relative to this
curve.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig4-12.*
   :alt: Illustration of kurtosis
   :name: fig4-12

   An illustration of kurtosis. On the left, we have a “platykurtic” 
   distribution (kurtosis = -.95) meaning that the distribution has “thin” or 
   flat tails. In the middle we have a “mesokurtic” distribution (kurtosis is 
   almost exactly 0) which means that the tails are neither thin or fat. 
   Finally, on the right, we have a “leptokurtic” distribution (kurtosis = 2.12) 
   indicating that the distribution has “fat” tails. Note that kurtosis is 
   measured with respect to a normal distribution (black line).

.. ----------------------------------------------------------------------------

The data in the left panel of :numref:`fig4-12` have a pretty flat
distribution, with thin tails, so the kurtosis is negative and we call the data
*platykurtic*. The data in the right panel have a distribution with fat tails,
so the kurtosis is positive and we say that the data is *leptokurtic*. Only the
data in the middle panel have neither thin or fat tails, so we say that it is
*mesokurtic* and has kurtosis zero. This is summarised in the table below:

+-----------------------------+----------------+----------------+
| informal term               | technical name | kurtosis value |
+=============================+================+================+
| “tails to thin”             | platykurtic    | negative       |
+-----------------------------+----------------+----------------+
| “tails neither thin or fat” | mesokurtic     | zero           |
+-----------------------------+----------------+----------------+
| “tails too fat”             | leptokurtic    | positive       |
+-----------------------------+----------------+----------------+

The equation for kurtosis is pretty similar in spirit to the formulas we have
seen already for the variance and the skewness. Except that where the variance
involved squared deviations and the skewness involved cubed deviations, the
kurtosis involves raising the deviations to the fourth power:\ [#]_

.. math:: \mbox{kurtosis}(X) = \frac{1}{N \hat\sigma ^ 4} \sum_{i = 1} ^ N \left( X_i - \bar{X} \right) ^ 4  - 3

jamovi has a check box for ``Kurtosis`` just below the check box for
``Skewness``, and this gives a value for kurtosis of **0.101** with a standard
error of **0.364**. This means that the ``afl.margins`` variable has only a
small kurtosis, which is OK.

------

.. [#]
   The “-3” part is something that statisticians tack on to
   ensure that the normal curve has kurtosis zero. It looks a bit
   stupid, just sticking a “-3” at the end of the formula, but there are
   good mathematical reasons for doing this.
