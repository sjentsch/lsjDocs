.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Multi-Trait Multi-Method CFA
----------------------------

In this section we’re going to consider how different measurement techniques
or questions can be an important source of data variability, known as
**method variance**. To do this, we’ll use another psychological data set, one
that contains data on “attributional style”.

The Attributional Style Questionnaire (ASQ; `Hewitt et al. (2004)
<References.html#hewitt-2004>`__\ ) collected psychological well-being data
from young people in the United Kingdom and New Zealand. They measured
attributional style for negative events, which is how people habitually explain
the cause of bad things that happen to them (`Peterson & Seligman, 1999
<References.html#peterson-1984>`__\ ).The attributional style questionnaire
(ASQ) measures three aspects of attributional style:

-  Internality is the extent to which a person believes that the cause of a bad
   event is due to his/her own actions.

-  Stability refers to the extent to which a person habitually believes the
   cause of a bad event is stable across time.

-  Globality refers to the extent to which a person habitually believes that
   the cause of a bad event in one area will affect other areas of their lives.

There are six hypothetical scenarios and for each scenario respondents answer a
question aimed at (a) internality, (b) stability and (c) globality. So there
are 6 x 3 = 18 items overall (see :numref:`fig-MTMM1` for more details).

.. ----------------------------------------------------------------------------

.. _fig-MTMM1:
.. figure:: ../_images/lsj_MTMM1.*
   :alt: The Attributional Style Questionnaire (ASQ) for negative events

   The Attributional Style Questionnaire (ASQ) for negative events
      
.. ----------------------------------------------------------------------------

Researchers are interested in checking their data to see whether there are some
underlying latent factors that are measured reasonably well by the 18 observed
variables in the ASQ.

First, they try EFA with these 18 variables (not shown), but no matter how they
extract or rotate, they can’t find a good factor solution. Their attempt to
identify underlying latent factors in the Attributional Style Questionnaire
(ASQ) proved fruitless. If you get results like this then either your theory is
wrong (there is no underlying latent factor structure for attributional style,
which is possible), the sample is not relevant (which is unlikely given the
size and characteristics of this sample of young adults from the United Kingdom
and New Zealand), or the analysis was not the right tool for the job. We’re
going to look at this third possibility.

Remember that there were three dimensions measured in the ASQ: Internality,
Stability and Globality, each measured by six questions as shown in
:numref:`fig-MTMM2`.

.. ----------------------------------------------------------------------------

.. _fig-MTMM2:
.. figure:: ../_images/lsj_MTMM2.*
   :alt: Six ASQ questions, dimensions: Internality, Stability, Globality

   Six questions on the ASQ for each of the Internality, Stability and
   Globality dimensions
      
.. ----------------------------------------------------------------------------

What if, instead of doing an analysis where we see how the data goes together
in an exploratory sense, we instead impose a structure, like in
:numref:`fig-MTMM2`, on the data and see how well the data fits our
pre-specified structure. In this sense, we are undertaking a confirmatory
analysis, to see how well a pre-specified model is confirmed by the observed
data.

A straightforward confirmatory factor analysis (CFA) of the ASQ would therefore
specify three latent factors as shown in the columns of :numref:`fig-MTMM2`,
each measured by six observed variables.

We could depict this as in the diagram in :numref:`fig-MTMM3`, which shows that
each variable is a measure of an underlying latent factor. For example ``INT1``
is predicted by the underlying latent factor Internality. And because ``INT1``
is not a perfect measure of the Internality factor, there is an error term, 
*e1*, associated with it. In other words, *e1* represents the variance in 
``INT1`` that is not accounted for by the Internality factor. This is sometimes
called “measurement error”.

.. ----------------------------------------------------------------------------

.. _fig-MTMM3:
.. figure:: ../_images/lsj_MTMM3.*
   :alt: Initial pre-specification of latent factor structure for the ASQ

   Initial pre-specification of latent factor structure for the ASQ
      
.. ----------------------------------------------------------------------------

The next step is to consider whether the latent factors should be allowed to
correlate in our model. As mentioned earlier, in the psychological and
behavioural sciences constructs are often related to each other, and we also
think that Internality, Stability, and Globality might be correlated with each
other, so in our model we should allow these latent factors to co-vary, as
shown in :numref:`fig-MTMM4`.

.. ----------------------------------------------------------------------------

.. _fig-MTMM4:
.. figure:: ../_images/lsj_MTMM4.*
   :alt: Final pre-specification of latent factor structure for the ASQ

   Final pre-specification of latent factor structure for the ASQ, including
   latent factor correlations, and shared method error term correlations for
   the observed variable INT1, STAB1 and GLOB1, in a CFA MTMM model. For
   clarity, other pre-specified error term correlations are not shown.
      
.. ----------------------------------------------------------------------------

At the same time, we should consider whether there is any good, systematic,
reason for some of the error terms to be correlated with each other. Thinking
back to the ASQ questions, there were three different sub-questions (a, b and
c) for each main question (1-6). Q1 was about unsuccessful job hunting and it
is plausible that this question has some distinctive artefactual or
methodological aspects over and above the other questions (2-5), something to
do with job hunting perhaps. Similarly, Q2 was about not helping a friend with
a problem, and there may be some distinctive artefactual or methodological
aspects to do with not helping a friend that is not present in the other
questions (1, and 3-5).

So, as well as multiple factors, we also have multiple methodological features
in the ASQ, where each of Questions 1-6 has a slightly different “method”, but
each “method” is shared across the sub-questions a, b and c. In order to
incorporate these different methodological features into the model we can
specify that certain error terms are correlated with each other. For example,
the errors associated with ``INT1``, ``STAB1`` and ``GLOB1`` should be
correlated with each other to reflect the distinct and shared methodological
variance of Q1a, Q1b and Q1c. Looking at :numref:`fig-MTMM2`, this means that
as well as the latent factors represented by the columns, we will have
correlated measurement errors for the variables in each row of the Table.

Whilst a basic CFA model like the one shown in :numref:`fig-MTMM3` could be
tested against our observed data, we have in fact come up with a more
sophisticated model, as shown in the diagram in :numref:`fig-MTMM4`. This more
sophisticated CFA model is known as a **Multi-Trait Multi-Method (MTMM)**
model, and it is the one we will test in jamovi.

MTMM CFA in jamovi
~~~~~~~~~~~~~~~~~~

Open up the ``ASQ`` data set and check that the 18 variables (six 
“Internality”, six “Stability” and six “Globality” variables) are specified as
continuous variables.

To perform MTMM CFA in jamovi:

-  Select ``Factor`` → ``Confirmatory Factor Analysis`` from the ``Analyses``
   ribbon menu in jamovi to open the analysis panel where you can determine
   the setttings for the CFA (:numref:`fig-MTMM5`).

-  Select the 6 ``INT`` variables and transfer them into the ``Factors`` box
   and give them the label “Internality”.

-  Create a new Factor in the ``Factors`` box and label it “Stability”.
   Select the 6 ``STAB`` variables and transfer them into the ``Factors`` box
   under the “Stability” label.

-  Create another new Factor in the ``Factors`` box and label it “Globality”.
   Select the 6 ``GLOB`` variables and transfer them into the ``Factors`` box
   under the “Globality” label.

-  Open up the Residual Covariances options, and for each of our pre-specified
   correlations move the associated variables across into the ``Residual
   Covariances`` box on the right. For example, highlight both ``INT1`` and
   ``STAB1`` and then click the arrow to move these across. Now do the same
   for ``INT1`` and ``GLOB1``, for ``STAB1`` and ``GLOB1``, for ``INT2`` and
   ``STAB2``, for ``INT2`` and ``GLOB2``, for ``STAB2`` and ``GLOB2``, for
   ``INT3`` and ``STAB3``, and so on.

-  Check other appropriate options, the defaults are OK for this initial
   work through, though you might want to check the ``Path diagram`` option
   under ``Plots`` to see jamovi produce a (fairly) similar diagram to our
   :numref:`fig-MTMM4`, but including all the error term correlations that we
   have added above.

.. ----------------------------------------------------------------------------

.. _fig-MTMM5:
.. figure:: ../_images/lsj_MTMM5.*
   :alt: Settings for conducting a Confirmatory Factor Analysis

   Analysis panel with the settings for conducting a Confirmatory Factor
   Analysis (CFA) in jamovi
      
.. ----------------------------------------------------------------------------

Once we have set up the analysis we can turn our attention to the jamovi
results window and see what’s what. The first thing to look at is “Model fit”
as this tells us how good a fit our model is to the observed data (NB: in our
model only the pre-specified covariances are estimated, everything else is set
to zero, so model fit is testing both whether the pre-specified “free”
parameters are not zero, and conversely whether the other relationships in the
data – the ones we have not specified in the model – can be held at zero).

There are several ways of assessing model fit. The first is a χ²-statistic,
which if small indicates that the model is a good fit to the data. However,
the χ²-statistic used for assessing model fit is very sensitive to sample size,
meaning that with a large sample (more than 300-400 cases) a good enough fit
between the model and the data almost always produces a large and significant
χ²-value.

So, we need some other ways of assessing model fit. In jamovi several are
provided by default. These are the Comparative Fit Index (CFI), the Tucker Fit
Index (TFI) and the Root Mean Square Error of Approximation (RMSEA) together
with the 90% confidence interval for the RMSEA. As we mentioned previously,
some useful rules of thumb are that a satisfactory fit is indicated by CFI >
\0.9, TFI > 0.9, and RMSEA of about 0.05 to 0.08. A good fit is CFI > 0.95,
TFI > 0.95, and RMSEA and upper CI for RMSEA < 0.05.

So, looking at :numref:`fig-MTMM6` we can see that the χ²-value is highly
significant, which is not a surprise given the large sample size (*N* = 2748).
The CFI is 0.98 and the TLI is also \0.98, indicating a very good fit. The
RMSEA is 0.02 with a 90% confidence interval from 0.02 to 0.02 – pretty tight!

.. ----------------------------------------------------------------------------

.. _fig-MTMM6:
.. figure:: ../_images/lsj_MTMM6.*
   :alt: Model Fit results for the specified CFA MTMM model in jamovi

   Table with Model Fit results for the specified CFA MTMM model in jamovi
      
.. ----------------------------------------------------------------------------

Overall, I think we can be satisfied that our pre-specified model is a very
good fit to the observed data, lending support to our MTMM model for the ASQ.

We can now go on to look at the factor loadings and the factor covariance
estimates, as in :numref:`fig-MTMM7`. Often the standardized estimates are
easier to interpret, and these can be specified under the ‘Estimates’ option.
These tables can usefully be incorporated into a written report or scientific
article.

.. ----------------------------------------------------------------------------

.. _fig-MTMM7:
.. figure:: ../_images/lsj_MTMM7.*
   :alt: Factor Loadings and Covariances for the specified CFA MTMM model

   Tables with Factor Loadings and Covariances for the specified CFA MTMM
   model in jamovi
      
.. ----------------------------------------------------------------------------

You can see from :numref:`fig-MTMM7` that all of our pre-specified factor
loadings and factor covariances are significantly different from zero. In
other words, they all seem to be making a useful contribution to the model.

We’ve been pretty lucky with this analysis, getting a very good fit on our
first attempt. That’s pretty unusual, and often in CFA additional *post-hoc*
tweaks are made to the model to improve the fit. One way of doing this is to
use “modification indices”, specified as an ``Additional output`` option in
jamovi.

What we are looking for is the highest modification index (MI) value. We would
then judge whether it makes sense to add that additional term into the model,
using a *post-hoc* rationalisation. For example, we can see in
:numref:`fig-MTMM8` that the largest MI for the factor loadings that are not
already in the model is a value of 24.52 for the loading of ``INT6`` onto the
latent factor Globality.
This indicates that if we add this path into the model then the χ²-value will
reduce by about 25. But in our model adding this path doesn’t really make any
theoretical or methodological sense, and therefore we won’t be including this
path in a revised model.

.. ----------------------------------------------------------------------------

.. _fig-MTMM8:
.. figure:: ../_images/lsj_MTMM8.*
   :alt: Factor Modification Indices for the specified CFA MTMM model

   Tables with Factor Modification Indices for the specified CFA MTMM model
   in jamovi
      
.. ----------------------------------------------------------------------------

Likewise, when we look at the MIs for the residual terms (:numref:`fig-MTMM9`)
the highest MI is 13.48 for allowing the errors between INT1 and INT3 to
co-vary – i.e. to be included – in the model. But, this isn’t a particularly
high MI, there is no reasonable justification for including this parameter in
the model, and we already have a good fit; so again our answer is no
modification.

.. ----------------------------------------------------------------------------

.. _fig-MTMM9:
.. figure:: ../_images/lsj_MTMM9.*
   :alt: Table with the Residual Covariances Modification Indices: MTMM-CFA

   Table with the Residual Covariances Modification Indices for the specified
   CFA MTMM model in jamovi

.. ----------------------------------------------------------------------------

If you do find yourself adding new parameters to a model using the MI then
always re-check the MI tables after each new addition (or exclusion – in some
software a MI can also suggest parameters to be removed from a model to
improve model fit), as the MIs are refreshed each time.
