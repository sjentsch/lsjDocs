.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Histograms
----------

Let us begin with the humble **histogram**. Histograms are one of the simplest
and most useful ways of visualising data. They make most sense when you have an
interval or ratio scale variable (e.g., the ``afl.margins`` variable from the
|aflsmall_finalists|_ data set that we used in
:doc:`../Ch04/Ch04_Descriptives`) and what you want to do is get an overall
impression of the variable. Most of you probably know how histograms work,
since they are so widely used, but for the sake of completeness I will describe
them. All you do is divide up the possible values into **bins** and then count
the number of observations that fall within each bin. This count is referred
to as the frequency or density of the bin and is displayed as a vertical bar.
The ``afl.margins`` variable contains 33 games in which the winning margin was
less than 10 points and it is this fact that is represented by the height of
the leftmost bar that we showed earlier in :doc:`../Ch04/Ch04_Descriptives`,
and :numref:`fig4-2`. With these earlier graphs we used an advanced plotting
package in R which, for now, is beyond the capability of jamovi. But jamovi
gets us close, and drawing this histogram in jamovi is pretty straightforward.
Open up the ``Plots`` options under ``Exploration`` →  ``Descriptives`` and
click the ``Histogram`` check box, as shown in :numref:`fig5-2`. jamovi
defaults to labelling the y-axis as ``density`` and the x-axis with the
variable name. The **bins** are selected automatically, and there is no scale,
or count, information on the y-axis unlike the previous :numref:`fig4-2`. But
this does not matter too much because after all what we are really interested
in is our impression of the shape of the distribution: is it normally
distributed or is there a skew or kurtosis? Our first impressions of these
characteristics come from drawing a **histogram**.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig5-2.*
   :alt: Histogram check box in jamovi and the resulting output
   :name: fig5-2

   jamovi screen showing the histogram check box and the resulting output
   
.. ----------------------------------------------------------------------------

One additional feature that jamovi provides is the ability to plot a density
curve. You can do this by clicking the ``Density`` check box under the
``Plots`` options (and unchecking ``Histogram``), and this gives us the plot
shown in :numref:`fig5-3`. A density plot visualises the distribution of data
over a continuous interval or time period. This chart is a variation of a 
histogram that uses **kernel smoothing** to plot values, allowing for smoother
distributions by smoothing out the noise. The peaks of a density plot help
display where values are concentrated over the interval. An advantage density
plots have over histograms is that they are better at determining the
distribution shape because they are not affected by the number of bins used
(each bar used in a typical histogram). A histogram comprising of only four
bins would not produce a distinguishable enough shape of distribution as a
20-bin histogram would. However, with density plots, this is not an issue.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig5-3.*
   :alt: Density plot for the ``afl.margins`` variable
   :name: fig5-3

   Density plot for the ``afl.margins`` variable plotted in jamovi
   
.. ----------------------------------------------------------------------------

Although this image would need a lot of cleaning up in order to make a good
presentation graphic (i.e., one you would include in a report), it nevertheless
does a pretty good job of describing the data. In fact, the big strength of a
histogram or density plot is that (properly used) it does show the entire
spread of the data, so you can get a pretty good sense about what it looks
like. The downside to histograms is that they are not very compact. Unlike some
of the other plots I will talk about it is hard to cram 20-30 histograms into a
single image without overwhelming the viewer. And of course, if your data are
nominal scale |nominal| then histograms are useless.

.. ----------------------------------------------------------------------------

.. |aflsmall_finalists|                replace:: ``aflsmall_finalists``
.. _aflsmall_finalists:                ../../_static/data/aflsmall_finalists.omv

.. |nominal|                           image:: ../_images/variable-nominal.*
   :width: 16px
