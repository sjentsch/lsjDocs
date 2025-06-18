.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

An illustrative data set
------------------------

Suppose you have become involved in a clinical trial in which you are
testing a new antidepressant drug called *Joyzepam*. In order to
construct a fair test of the drug’s effectiveness, the study involves
three separate drugs to be administered. One is a placebo, and the other
is an existing antidepressant / anti-anxiety drug called *Anxifree*. A
collection of 18 participants with moderate to severe depression are
recruited for your initial testing. Because the drugs are sometimes
administered in conjunction with psychological therapy, your study
includes nine people undergoing cognitive behavioural therapy (CBT) and
nine who are not. Participants are randomly assigned (doubly blinded, of
course) a treatment, such that there are three CBT people and three
no-therapy people assigned to each of the three drugs. A psychologist
assesses the mood of each person after a three-month run with each drug,
and the overall *improvement* in each person’s mood is assessed on a scale
ranging from -5 to +5. With that as the study design, let us now load
|clinicaltrial|_ data set. It contains the three variables ``drug``
|nominal|, ``therapy`` |nominal| and ``mood.gain`` |continuous|.

For the purposes of this chapter, what we are really interested in is the
effect of ``drug`` on ``mood.gain``. The first thing to do is calculate
some descriptive statistics and draw some graphs. In
:doc:`../Ch04/Ch04_Descriptives` we showed you how to do this, and some of the
descriptive statistics we can calculate in jamovi are shown in
:numref:`fig-anova1`.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_anova1.*
   :alt: Descriptives for ``mood.gain``, and box plots by ``drug`` administered
   :name: fig-anova1

   Descriptives for ``mood.gain``, and box plots by ``drug`` administered
   
.. ----------------------------------------------------------------------------

As the plot makes clear, there is a larger improvement in mood for participants
in the ``joyzepam`` group than for either the ``anxifree`` group or the
``placebo`` group. The ``anxifree`` group shows a larger mood gain than the
``placebo`` group, but the difference is not as large. The question that we want
to answer is are these difference “real”, or are they just due to chance?

.. ----------------------------------------------------------------------------

.. |clinicaltrial|                     replace:: ``clinicaltrial``
.. _clinicaltrial:                     ../../_statics/data/clinicaltrial.omv

.. |continuous|                        image:: ../_images/variable-continuous.*
   :width: 16px
 
.. |nominal|                           image:: ../_images/variable-nominal.*
   :width: 16px
