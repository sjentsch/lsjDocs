.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Hypothesis tests for regression models
--------------------------------------

So far we have talked about what a regression model is, how the coefficients of
a regression model are estimated, and how we quantify the performance of the
model (the last of these, incidentally, is basically our measure of effect
size). The next thing we need to talk about is hypothesis tests. There are two
different (but related) kinds of hypothesis tests that we need to talk about:
those in which we test whether the regression model as a whole is performing
significantly better than a null model, and those in which we test whether a
particular regression coefficient is significantly different from zero.

Testing the model as a whole
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Okay, suppose you have estimated your regression model. The first hypothesis
test you might try is the null hypothesis that there is *no relationship*
between the predictors and the outcome, and the alternative hypothesis that
*the data are distributed in exactly the way that the regression model
predicts*.

Formally, our “null model” corresponds to the fairly trivial “regression” model
in which we include 0 predictors and only include the intercept term
*b*\ :sub:`0`:

| *H*\ :sub:`0`: *Y*\ :sub:`i` = b\ :sub:`0` + ε\ :sub:`i`

If our regression model has *K* predictors, the “alternative model” is
described using the usual formula for a multiple regression model:

| *H*\ :sub:`1`: *Y*\ :sub:`i` = b\ :sub:`0` + math:`\left( \sum_{k = 1} ^ K b_{k} X_{ik} \right)` + ε\ :sub:`i`

How can we test these two hypotheses against each other? The trick is to
understand that it is possible to divide up the total variance *SS*\ :sub:`tot`
into the sum of the residual variance *SS*\ :sub:`res` and the regression model
variance *SS*\ :sub:`mod`. We will get to the technicalities later when we look
at ANOVA in chapter :doc:`../Ch13/Ch13_ANOVA`. But just note that:

| *SS*\ :sub:`mod` = *SS*\ :sub:`tot` - *SS*\ :sub:`res`

And we can convert the sums of squares into mean squares by dividing by the
degrees of freedom.

| *MS*\ :sub:`mod` = *SS*\ :sub:`mod` / *df*\ :sub:`mod`
| *MS*\ :sub:`res` = *SS*\ :sub:`res` / *df*\ :sub:`res` 

So, how many degrees of freedom do we have? As you might expect the *df*
associated with the model is closely tied to the number of predictors that we
have included. In fact, it turns out that *df*\ :sub:`mod` = *K*. For the
residuals the total degrees of freedom is *df*\ :sub:`res` = *N* - *K* - 1.

Now that we have got our mean square values we can calculate an *F*-statistic
like this (with *K* and *N* - *K* - 1 as associated *df*):

| *F* = *MS*\ :sub:`mod` / *MS*\ :sub:`res`

We will see much more of the *F*-statistic in chapter :doc:`../Ch13/Ch13_ANOVA`,
but for now just know that we can interpret large *F*-values as indicating
that the null hypothesis is performing poorly in comparison to the alternative
hypothesis. Before I show you how to do the test in jamovi the easy way, let us
first have a look at the tests for the individual regression coefficients.

Tests for individual coefficients
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The *F*-test that we have just introduced is useful for checking that the model
as a whole is performing better than chance. If your regression model does not
produce a significant result for the *F*-test then you probably do not have a
very good regression model (or, quite possibly, you do not have very good data).
However, while failing this test is a pretty strong indicator that the model
has problems, *passing* the test (i.e., rejecting the null hypothesis) does not
imply that the model is good! Why is that, you might be wondering? The answer
to that can be found by looking at the coefficients for the multiple regression
model we have already looked at :numref:`tab-parent_coeff` in section
:doc:`Ch12_Regression_05` above, where the coefficients we got were 125.966
(for the intercept), -8.950 (for ``dani.sleep``) and 0.011 (for
``baby.sleep``). I can not help but notice that the estimated regression
coefficient for the ``baby.sleep`` variable is tiny, relative to the value that
we get for ``dani.sleep``. Given that these two variables are absolutely on the
same scale (they are both measured in “hours slept”), I find this illuminating.
In fact, I am beginning to suspect that it is really only the amount of sleep
that *I* get that matters in order to predict my grumpiness.

We can re-use a hypothesis test that we discussed earlier, the *t*-test. The
test that we are interested in has a null hypothesis that the true regression
coefficient is zero (*b* = 0), which is to be tested against the alternative
hypothesis that it is not (*b* ≠ 0). That is:

| *H*\ :sub:`0`: *b* = 0
| *H*\ :sub:`1`: *b* ≠ 0 

How can we test this? Well, if the central limit theorem is kind to us we might
be able to guess that the sampling distribution of :math:`\hat{b}`, the
estimated regression coefficient, is a normal distribution with mean centred on
*b*. What that would mean is that if the null hypothesis were true, then the
sampling distribution of :math:`\hat{b}` has mean zero and unknown standard
deviation. Assuming that we can come up with a good estimate for the standard
error of the regression coefficient, :math:`SE(\hat{b})`, then we are in luck.
That is *exactly* the situation for which we introduced the one-sample *t*-test
way back in chapter :doc:`../Ch11/Ch11_tTest`. So let us define a *t*-statistic
like this:

.. math:: t = \frac{\hat{b}}{SE(\hat{b})}

I will skip over the reasons why, but our degrees of freedom in this case are
*df* = *N* - *K* - 1. Irritatingly, the estimate of the standard error of the
regression coefficient, :math:`SE(\hat{b})`, is not as easy to calculate as the
standard error of the mean that we used for the simpler *t*-tests in chapter
:doc:`../Ch11/Ch11_tTest`. In fact, the formula is somewhat ugly, and not
terribly helpful to look at.\ [#]_ For our purposes it is sufficient to point
out that the standard error of the estimated regression coefficient depends on
both the predictor and outcome variables, and it is somewhat sensitive to
violations of the homogeneity of variance assumption (discussed shortly).

In any case, this *t*-statistic can be interpreted in the same way as the
*t*-statistics that we discussed in chapter :doc:`../Ch11/Ch11_tTest`.
Assuming that you have a two-sided alternative (i.e., you do not really care if
*b* > 0 or *b* < 0), then it is the extreme values of *t* (i.e., a lot less
than zero or a lot greater than zero) that suggest that you should reject the
null hypothesis.

.. _coefficients_in_jamovi:

Running the hypothesis tests in jamovi
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To compute all of the statistics that we have talked about so far, all you need
to do is make sure the relevant options are checked in jamovi and then run the
regression. If we do that, as in :numref:`fig12-15`, we get a whole bunch of
useful output.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig12-15.*
   :alt: jamovi screenshot showing a multiple linear regression
   :name: fig12-15

   jamovi screenshot showing a multiple linear regression analysis, with some
   useful options checked.
   
.. ----------------------------------------------------------------------------

The ``Model Coefficients`` at the bottom of the jamovi analysis results shown
in :numref:`fig12-15` provides the coefficients of the regression model. Each
row in this table refers to one of the coefficients in the regression model.
The first row is the intercept term, and the later ones look at each of the
predictors. The columns give you all of the relevant information. The first
column is the actual estimate of *b* (e.g., 125.97 for the intercept, and -8.95
for the ``dani.sleep`` predictor). The second column is the standard error
estimate :math:`\hat\sigma_b`. The third and fourth columns provide the lower
and upper values for the 95\% confidence interval around the *b* estimate (more
on this later). The fifth column gives you the *t*-statistic, and it is worth
noticing that in this table :math:`t = \hat{b} / SE(\hat{b})` every time.
Finally, the last column gives you the actual *p*-value for each of these
tests.\ [#]_

The only thing that the coefficients table itself does not list is the degrees
of freedom used in the *t*-test, which is always *N* - *K* - 1 and is listed in
the table at the top of the output, labelled ``Model Fit Measures``. We can see
from this table that the model performs significantly better than you would
expect by chance (*F*\(2,97) = 215.24, *p* < 0.001), which is not all that
surprising: the *R*\² = 0.81 value indicate that the regression model accounts
for 81\% of the variability in the outcome measure (and 82\% for the adjusted
*R*\²). However, when we look back up at the *t*-tests for each of the
individual coefficients, we have pretty strong evidence that the ``baby.sleep``
variable has no significant effect. All the work in this model is being done by
the ``dani.sleep`` variable. Taken together, these results suggest that this
regression model is actually the wrong model for the data. You would probably
be better off dropping the ``baby.sleep`` predictor entirely. In other words,
the simple regression model that we started with is the better model.

------

.. [#]
   For advanced readers only. The vector of residuals is
   :math:`\epsilon = y - X \hat{b}`. For *K* predictors plus the intercept, the 
   estimated residual variance is
   :math:`\hat\sigma ^ 2 = \epsilon^\prime\epsilon / (N - K - 1)`. The
   estimated covariance matrix of the coefficients is
   :math:`\hat\sigma ^ 2 (\mathbf{X} ^ \prime\mathbf{X}) ^ {-1}`, the main
   diagonal of which is :math:`SE(\hat{b})`, our estimated standard errors.

.. [#]
   Note that, although jamovi has done multiple tests here, it has not done a 
   Bonferroni correction or anything. These are standard one-sample *t*-tests 
   with a two-sided alternative. If you want to make corrections for multiple 
   tests, you need to do that yourself.
