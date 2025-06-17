.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Assumptions of regression
-------------------------

The linear regression model that I have been discussing relies on several
assumptions. In section :doc:`Ch12_Regression_11` we will talk a lot more about
how to check that these assumptions are being met, but first let us have a look
at each of them.

-  *Normality*. Like many of the models in statistics, basic simple or multiple
   linear regression relies on an assumption of normality. Specifically, it
   assumes that the *residuals* are normally distributed. It is actually okay if
   the predictors *X* and the outcome *Y* are non-normal, so long as the
   residuals ε are normal. See section :ref:`Checking the normality of the
   residuals <checking_normality_residuals>`.

-  *Linearity*. A pretty fundamental assumption of the linear regression model
   is that the relationship between *X* and *Y* actually is linear! Regardless
   of whether it is a simple regression or a multiple regression, we assume that
   the relationships involved are linear.

-  *Homogeneity of variance*. Strictly speaking, the regression model assumes
   that each residual ε\ :sub:`i` is generated from a normal distribution with
   mean 0, and (more importantly for the current purposes) with a standard
   deviation σ that is the same for every single residual. In practice, it is
   impossible to test the assumption that every residual is identically
   distributed. Instead, what we care about is that the standard deviation of
   the residual is the same for all values of *Ŷ*, and (if we are being
   especially paranoid) all values of every predictor *X* in the model.

-  *Uncorrelated predictors*. The idea here is that, in a multiple
   regression model, you do not want your predictors to be too strongly
   correlated with each other. Thit is not “technically” an assumption of
   the regression model, but in practice it is required. Predictors that
   are too strongly correlated with each other (referred to as
   “collinearity”) can cause problems when evaluating the model. See
   section :ref:`Checking for collinearity <checking_collinearity>`.

-  *Residuals are independent of each other*. Thit is really just a
   “catch all” assumption, to the effect that “there is nothing else
   funny going on in the residuals”. If there is something weird (e.g.,
   the residuals all depend heavily on some other unmeasured variable)
   going on, it might screw things up.

-  *No “bad” outliers*. Again, not actually a technical assumption of the model
   (or rather, it is sort of implied by all the others), but there is an
   implicit assumption that your regression model is not being too strongly
   influenced by one or two anomalous data points because this raises questions
   about the adequacy of the model and the trustworthiness of the data in some
   cases. See section :ref:`Three kinds of anomalous data <anomalous_data>`.
