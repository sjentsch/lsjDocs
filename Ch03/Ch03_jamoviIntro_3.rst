.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Changing data from one level to another
---------------------------------------

Sometimes you want to change the variable level. This can happen for all sorts
of reasons. Sometimes when you import data from files, it can come to you in
the wrong format. Numbers sometimes get imported as nominal |nominal|, text
values. Dates may get imported as text. Participant-ID values |ID| can
sometimes be read as continuous |continuous|: nominal values |nominal| can
sometimes be read as ordinal |ordinal| or even continuous |continuous|. There’s
a good chance that sometimes you’ll want to convert a variable from one
measurement level into another one. Or, to use the correct term, you want to
**coerce** the variable from one class into another.

In :doc:`The spreadsheet <../Ch03/Ch03_jamoviIntro_2>` we saw how to specify
different variable levels, and if you want to change a variable’s measurement
level then you can do this in the jamovi data view for that variable. Just
click the check box for the type level you want - continuous |continuous|,
ordinal |ordinal|, or nominal |nominal|.

Installing add-on modules into jamovi
-------------------------------------

A really great feature of jamovi is the ability to install add-on
modules from the jamovi library. These add-on modules have been
developed by the jamovi community, i.e., jamovi users and developers who
have created special software add-ons that do other, usually more
advanced, analyses that go beyond the capabilities of the base jamovi
program.

To install add-on modules, just click on the large ``+`` in the top right
of the jamovi window, select ``jamovi library`` and then browse through
the various add-on modules that are available. Choose the one(s) you
want, and then install them (as shown in :numref:`fig-modules`).

It’s that easy. The newly installed modules can then be accessed from the
``Analyses`` tab. Try it… useful add-on modules to install include
``scatr`` (added under ``Descriptives``) and |Rj|_.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_modules.*
   :alt: jamovi modules in the jamovi library
   :name: fig-modules

   Installing add-on modules in jamovi
   
.. ----------------------------------------------------------------------------


Quitting jamovi
---------------

There’s one last thing I should cover in this chapter: how to quit
jamovi. It’s not hard, just close the program the same way you would any
other program. However, what you might want to do before you quit is
save your work! There are two parts to this: saving any changes to the
data set, and saving the analyses that you ran.

It is good practice to save any changes to the data set as a *new* data
set. That way you can always go back to the original data. To save any
changes in jamovi, select ``Export`` → ``Data`` from the main jamovi menu
(``☰``; top left hand corner) and create a new file name for the changed
data set.

Alternatively, you can save *both* the changed data and any analyses you
have undertaken by saving as a jamovi file. To do this, from the main
jamovi menu select ``Save as`` and type in a file name for this
``jamovi file (.omv)``. Remember to save the file in a location where you can find
it again later. I usually create a new folder for specific data sets and
analyses.

----

.. |Rj|                                replace:: ``Rj``
.. _Rj:                                https://docs.jamovi.org/_pages/Rj_overview.html

.. |ID|                               image:: ../_images/variable-id.*
   :width: 16px
 
.. |continuous|                       image:: ../_images/variable-continuous.*
   :width: 16px
 
.. |nominal|                          image:: ../_images/variable-nominal.*
   :width: 16px
 
.. |ordinal|                          image:: ../_images/variable-ordinal.*
   :width: 16px
