.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Quantifying the fit of the regression model
-------------------------------------------

So we now know how to estimate the coefficients of a linear regression
model. The problem is, we do not yet know if this regression model is any
good. For example, the ``regression.1`` model *claims* that every hour
of sleep will improve my mood by quite a lot, but it might just be
rubbish. Remember, the regression model only produces a prediction
*Ŷ*\ :sub:`i` about what my mood is like, but my actual mood is
*Y*\ :sub:`i`. If these two are very close, then the regression model has
done a good job. If they are very different, then it has done a bad job.

The *R*\² (R-squared) value
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Once again, let us wrap a little bit of mathematics around this. Firstly, we
have got the sum of the squared residuals:

.. math:: \mbox{SS}_{res} = \sum_i (Y_i - \hat{Y}_i)^2

which we would hope to be pretty small. Specifically, what we would like is
for it to be very small in comparison to the total variability in the outcome
variable:

.. math:: \mbox{SS}_{tot} = \sum_i (Y_i - \bar{Y})^2

While we are here, let us calculate these values ourselves, not by hand though.
Let us use jamovi instead. Open up the |parenthood|_ data set in so that we can
work in it. The first thing to do is calculate the *Ŷ* values, and for the
simple model that uses only a single predictor we would do the following:

#. Go to an empty column (at the end of the data set) and double click on the
   column header, choose ``New computed variable`` and enter ``Y_pred`` in the 
   first line and the formula ``125.97 + (-8.94 * dani.sleep)`` in the line
   starting with ``=`` (next to the *f*\ :sub:`x`).

Okay, now that we have got a variable which stores the regression model
predictions for how grumpy I will be on any given day, let us calculate
our sum of squared residuals. We would do that using the following
formula:

#. Calculate the squared residuals by creating a new column called
   ``sq_resid`` using the formula ``(dani.grump - Y_pred) ^ 2``. The values
   in this column are later summed up to obtain *SS*\ :sub:`res`.

#. Calculate the squared deviation from the mean by creating yet another
   column called ``sq_total`` using the formula
   ``(dani.grump - VMEAN(dani.grump)) ^ 2``. The values in this column are
   later summed up to obtain *SS*\ :sub:`tot`.

To calculate the sum of these values, click ``Descriptives`` → ``Descriptive
Statistics`` and move ``sq_resid`` and ``sq_total`` to the ``Variables`` box.
You will then need to select ``Sum`` from the ``Statistics`` drop-down menu
below. The sum of ``sq_resid`` has a value of **1838.722**. This is a big
number, however, that does not mean very much. The sum of ``sq_total`` has a
value of **9998.590**. Well, it is a much (about five times) bigger number
than the last one, so this does suggest that our regression model was making
good predictions (that is, it has greatly reduced the residual error compared
to the model that uses the mean as a single predictor). But it is not very
interpretable.

To fix this, we would like to convert these two fairly meaningless numbers into
one number. A nice, interpretable number, which for no particular reason we
will call *R*\². What we would like is for the value of *R*\² to be equal to 1
if the regression model makes no errors in predicting the data. In other words,
if it turns out that the residual errors are zero. That is, if *SS*\ :sub:`res`
= 0 then we expect *R*\² = 1. Similarly, if the model is completely useless, we
would like *R*\² to be equal to 0. What do I mean by “useless”? Tempting as it
is to demand that the regression model move out of the house, cut its hair and
get a real job, I am probably going to have to pick a more practical
definition. In this case, all I mean is that the residual sum of squares is no
smaller than the total sum of squares, *SS*\ :sub:`res` = *SS*\ :sub:`tot`.
Wait, why do not we do exactly that? The formula that provides us with our
*R*\² value is pretty simple to write down, and equally simple to calculate by
hand:\ [#]_

| *R*\² = 1 - (*SS*\ :sub:`res` / *SS*\ :sub:`tot`)
| *R*\² = 1 - (1838.722 / 9998.590)
| *R*\² = 1 - 0.184
             
This gives a value for *R*\² of **0.816**. The *R*\² value, sometimes called the
**coefficient of determination**\ [#]_ has a simple interpretation: it is the
*proportion* of the variance in the outcome variable that can be accounted for
by the predictor. So, in this case the fact that we have obtained *R*\² = 0.816
means that the predictor (``dani.sleep``) explains 81.6\% of the variance in the
outcome (``dani.grump``).\ [#]_

Naturally, you do not actually need to do all these calculations yourself if
you want to obtain the *R*\² value for your regression model. As we will see
later in :ref:`Running the hypothesis tests in jamovi <coefficients_in_jamovi>`,
all you need to do is specify this as an option in jamovi. However, let us put
that to one side for the moment. There is another property of *R*\² that I want
to point out.

The relationship between regression and correlation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

At this point we can revisit my earlier claim that regression, in this very
simple form that I have discussed so far, is basically the same thing as a
correlation. Previously, we used the symbol *r* to denote a Pearson
correlation. Might there be some relationship between the value of the
correlation coefficient *r* and the *R*\² value from linear regression? Of
course there is: the squared correlation *R*\² is identical to the *R*\² value
for a linear regression with only a single predictor. In other words, running a
Pearson correlation is more or less equivalent to running a linear regression
model that uses only one predictor variable.

The adjusted *R*\² (R-squared) value
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

One final thing to point out before moving on. It is quite common for people
to report a slightly different measure of model performance, known a
“adjusted *R*\²”. The motivation behind calculating the adjusted *R*\² value
is the observation that adding more predictors into the model will *always*
cause the *R*\² value to increase (or at least not decrease).

The adjusted *R*\² value introduces a slight change to the calculation, as
follows. For a regression model with *K* predictors, fit to a data set
containing *N* observations, the adjusted *R*\² is:

.. math:: \mbox{adj. } R^2 = 1 - \left(\frac{\mbox{SS}_{res}}{\mbox{SS}_{tot}} \times \frac{N - 1}{N - K - 1} \right)

This adjustment is an attempt to take the degrees of freedom into account. The
big advantage of the adjusted *R*\² value is that when you add more predictors
to the model, the adjusted *R*\² value will only increase if the new variables
improve the model performance more than you would expect by chance. The big
disadvantage is that the adjusted *R*\² value *can not* be interpreted in the
elegant way that *R*\² can. *R*\² has a simple interpretation as the proportion
of variance in the outcome variable that is explained by the regression model.
To my knowledge, no equivalent interpretation exists for adjusted *R*\².

An obvious question then is whether you should report *R*\² or adjusted *R*\².
This is probably a matter of personal preference. If you care more about
interpretability, then *R*\² is better. If you care more about correcting for
bias, then adjusted *R*\² is probably better. Speaking just for myself, I
prefer *R*\². My feeling is that it is more important to be able to interpret
your measure of model performance. Besides, as we will see in section
:doc:`Ch12_Regression_07`, if you are worried that the improvement in *R*\²
that you get by adding a predictor is just due to chance and not because it is
a better model, well we have got hypothesis tests for that.

------

.. [#]
   If you don't want to do these calculations by hand, just create another
   computed variable called, e.g., ``R2``, and containing the formula
   ``1 - VSUM(sq_resid) / VSUM(sq_total)``. But then you have a whole column
   containing *R*\².

.. [#]
   And by “sometimes” I mean “almost never”. In practice everyone just calls it
   “*R*-squared”.

.. [#]
   If you made a mistake or could not follow the explanations, you can simply
   download and open the |parenthood_r2|_ data set.

.. ----------------------------------------------------------------------------

.. |parenthood|                        replace:: ``parenthood``
.. _parenthood:                        ../../_statics/data/parenthood.omv

.. |parenthood_r2|                     replace:: ``parenthood_r2``
.. _parenthood_r2:                     ../../_statics/data/parenthood_r2.omv
