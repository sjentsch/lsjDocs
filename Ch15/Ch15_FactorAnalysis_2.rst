.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Principal Component Analysis
----------------------------

In the previous section we saw that EFA works to identify underlying latent
factors. And, as we saw, in one scenario the smaller number of latent factors
can be used in further statistical analysis using some sort of combined factor
scores.

In this way EFA is being used as a “data reduction” technique. Another type of
data reduction technique, sometimes seen as part of the EFA family, is 
**principal component analysis (PCA)**. However, PCA does not identify
underlying latent factors. Instead it creates a linear composite score from a
larger set of measured variables.

PCA simply produces a mathematical transformation to the original data with no
assumptions about how the variables covary. The aim of PCA is to calculate a
few linear combinations (components) of the original variables that can be used
to summarize the observed data set without losing much information. However, if
identification of underlying structure is a goal of the analysis, then EFA is
to be preferred. And, as we saw, EFA produces factor scores that can be used
for data reduction purposes just like principal component scores
(:ref:`Fabrigar et al., 1999 <Fabrigar_1999>`).

PCA has been popular in Psychology for a number of reasons, and therefore it is
worth covering, although nowadays EFA is just as easy to do given the power of
desktop computers and can be less susceptible to bias than PCA, especially with
a small number of factors and variables. Much of the procedure is similar to
EFA, so although there are some conceptual differences, practically the steps
are the same, and with large samples and a sufficient number of factors and
variables, the results from PCA and EFA should be fairly similar.

To run a PCA in jamovi, all you need to do is select ``Factor`` → ``Principal
Component Analysis`` from the main jamovi button bar to open the PCA analysis
panel. Then you can follow the same steps as for the EFA in jamovi in the
previous section. The only differences are that what is called factors for the
EFA is called components here, and that there is no choice of ``Extraction``
method and no ``Model fit measures``.

Generally, the results are quite similar to those obtained with the EFA. There
are also five components extracted, similar to the five factors extracted by
the EFA. However, the five component solution accounts for a little over half
of the variance in the observed data (56\% vs. 46\% in the EFA). We can also
recognize that components loading are slightly higher, and that the uniqueness
values are slightly lower. For the PCA the whole variance of each item is
considered whereas for the EFA the variance is split into common variance
(i.e., to what degree the variation in one questionnaire item can be predicted
by the other items, and can therefore be assumed to measure some common
underlying construct) and variance that is unique to that particular item.

.. ----------------------------------------------------------------------------

.. |bfi_sample|                        replace:: ``bfi_sample``
.. _bfi_sample:                        ../../_statics/data/bfi_sample.omv
