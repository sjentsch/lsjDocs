.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Drawing graphs
==============

.. epigraph::

   | *Above all else show the data.*
   
   -- Edward Tufte\ [#]_

Visualising data is one of the most important tasks facing the data
analyst. It’s important for two distinct but closely related reasons.
Firstly, there’s the matter of drawing “presentation graphics”,
displaying your data in a clean, visually appealing fashion makes it
easier for your reader to understand what you’re trying to tell them.
Equally important, perhaps even more important, is the fact that drawing
graphs helps *you* to understand the data. To that end, it’s important
to draw “exploratory graphics” that help you learn about the data as you
go about analysing it. These points might seem pretty obvious but I
cannot count the number of times I’ve seen people forget them.

To give a sense of the importance of this chapter, I want to start with
a classic illustration of just how powerful a good graph can be. To that
end, :numref:`fig-snowMap` shows a redrawing of one of the most famous data
visualisations of all time. This is John Snow’s 1854 map of cholera deaths.
The map is elegant in its simplicity. In the background we have a street map
which helps orient the viewer. Over the top we see a large number of small
dots, each one representing the location of a cholera case. The larger
symbols show the location of water pumps, labelled by name. Even the most
casual inspection of the graph makes it very clear that the source of the
outbreak is almost certainly the Broad Street pump. Upon viewing this graph
Dr Snow arranged to have the handle removed from the pump and ended the
outbreak that had killed over 500 people. Such is the power of a good data
visualisation.

.. ----------------------------------------------------------------------------

.. _fig-snowMap:
.. figure:: ../_images/lsj_snowMap.*
   :alt: Redrawing of Snow’s original cholera map

   Stylised redrawing of John Snow’s original cholera map. Each small dot
   represents the location of a cholera case and each large circle shows the
   location of a well. As the plot makes clear, the cholera outbreak is centred
   very closely on the Broad St pump.
   
.. ----------------------------------------------------------------------------

The goals in this chapter are twofold. First, to discuss several fairly
standard graphs that we use a lot when analysing and presenting data,
and second to show you how to create these graphs in jamovi. The graphs
themselves tend to be pretty straightforward, so in one respect this
chapter is pretty simple. Where people usually struggle is learning how
to produce graphs, and especially learning how to produce good graphs.
Fortunately, learning how to draw graphs in jamovi is reasonably simple
as long as you’re not too picky about what your graph looks like. What I
mean when I say this is that jamovi has a lot of *very* good default
graphs, or plots, that most of the time produce a clean, high-quality
graphic. However, on those occasions when you do want to do something
non-standard, or if you need to make highly specific changes to the
figure, then the graphics functionality in jamovi is not yet capable of
supporting advanced work or detail editing.

.. toctree::
   :hidden:

   Ch05_Graphics_1
   Ch05_Graphics_2
   Ch05_Graphics_3
   Ch05_Graphics_4
   
------

.. [#]
   The origin of this quote is Tufte’s lovely book *The Visual Display
   of Quantitative Information*.
