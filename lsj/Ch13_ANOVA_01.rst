.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

An illustrative data set
------------------------

Suppose you’ve become involved in a clinical trial in which you are
testing a new antidepressant drug called *Joyzepam*. In order to
construct a fair test of the drug’s effectiveness, the study involves
three separate drugs to be administered. One is a placebo, and the other
is an existing antidepressant / anti-anxiety drug called *Anxifree*. A
collection of 18 participants with moderate to severe depression are
recruited for your initial testing. Because the drugs are sometimes
administered in conjunction with psychological therapy, your study
includes 9 people undergoing cognitive behavioural therapy (CBT) and 9
who are not. Participants are randomly assigned (doubly blinded, of
course) a treatment, such that there are 3 CBT people and 3 no-therapy
people assigned to each of the 3 drugs. A psychologist assesses the mood
of each person after a 3 month run with each drug, and the overall
*improvement* in each person’s mood is assessed on a scale ranging from
-5 to +5. With that as the study design, let’s now load
up the data file in ``clinicaltrial.csv``. We can see that this data set
contains the three variables ``drug``, ``therapy`` and ``mood.gain``.

For the purposes of this chapter, what we’re really interested in is the
effect of ``drug`` on ``mood.gain``. The first thing to do is calculate
some descriptive statistics and draw some graphs. In `Descriptive statistics
<Ch04_Descriptives.html#descriptive-statistics>`__ we showed you how to do
this, and some of the descriptive statistics we can calculate in jamovi
are shown in :numref`fig-anova1`.

.. ----------------------------------------------------------------------------

.. _fig-anova1:
.. figure:: ../_images/lsj_anova1.*
   :alt: Descriptives for mood.gain, and box plots by drug administered

   Descriptives for ``mood.gain``, and box plots by ``drug`` administered
   
.. ----------------------------------------------------------------------------

As the plot makes clear, there is a larger improvement in mood for
participants in the Joyzepam group than for either the Anxifree group or
the placebo group. The Anxifree group shows a larger mood gain than the
control group, but the difference isn’t as large. The question that we
want to answer is are these difference “real”, or are they just due to
chance?
