.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Tabulating and cross-tabulating data
------------------------------------

A very common task when analysing data is the construction of frequency
tables, or cross-tabulation of one variable against another. These tasks
can be achieved in jamovi and I will show you how in this section.

Creating tables for single variables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Let us start with a simple example. As a parent of a small child I naturally
spend a lot of time watching TV shows like *In the Night Garden*. In the
|nightgarden|_ data set, I have transcribed a short section of the dialogue.
The file contains two variables of interest, ``speaker`` and ``utterance``.
Open up this data set in jamovi and take a look at the data in the ``Data``
view. You will see that the data looks something like this:

``speaker`` variable

.. code-block:: text

   upsy-daisy upsy-daisy upsy-daisy upsy-daisy tombliboo tombliboo makka-pakka makka-pakka makka-pakka makka-pakka

``utterance`` variable

.. code-block:: text

   pip pip onk onk ee oo pip pip onk onk


Looking at this it becomes very clear what happened to my sanity! With these as
my data, one task I might find myself needing to do is construct a frequency
count of the number of words each character speaks during the show. The jamovi
``Descriptives`` screen has a check box called ``Frequency tables`` which
produces a table similar to this one:

+-------------+--------+------------+--------------+
| Levels      | Counts | % of Total | Cumulative % |
+=============+========+============+==============+
| makka-pakka |	     4 |         40 |           40 |
+-------------+--------+------------+--------------+
| tombliboo   |      2 |         20 |           60 |
+-------------+--------+------------+--------------+
| upsy-daisy  |      4 |         40 |          100 |
+-------------+--------+------------+--------------+

The output here tells us on the first line that what we are looking at is a
tabulation of the ``speaker`` variable. In the ``Levels`` column it lists all
the different speakers that exist in the data, and in the ``Counts`` column it
tells you how many times that speaker appears in the data. In other words, it
is a frequency table.

In jamovi, the ``Frequency tables`` check box will only produce a table for
single variables. For a table of two variables, for example combining
``speaker`` and ``utterance`` so that we can see how many times each speaker
said a particular utterance, we need a cross-tabulation or contingency table.
In jamovi you can do this by selecting the ``Frequencies`` → ``Contingency
Tables`` → ``Independent Samples`` analysis, and moving the ``speaker``
variable into the ``Rows`` box, and the ``utterance`` variable into the
``Columns`` box. You then should have a contingency table like the one shown
in :numref:`fig6-1`.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig6-1.*
   :alt: Contingency table for ``speaker`` and ``utterance``
   :name: fig6-1

   Contingency table for the ``speaker`` and ``utterance`` variables
   
.. ----------------------------------------------------------------------------

Do not worry about the ``χ² Tests`` table that is produced. We are going to
cover this later on in chapter :doc:`../Ch10/Ch10_ChiSquare`. When interpreting
the contingency table remember that these are counts, so the fact that the
first row and second column of numbers corresponds to a value of 2 indicates
that ``makka-pakka`` (row 1) says ``onk`` (column 2) twice in this data set.

Adding percentages to a contingency table
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The contingency table shown in :numref:`fig6-1` shows a table of raw
frequencies. That is, a count of the total number of cases for different
combinations of levels of the specified variables. However, often you want your
data to be organised in terms of percentages as well as counts. You can find
the check boxes for different percentages under the ``Cells`` option in the
``Contingency Tables`` window. First, click on the ``Row`` check box and the
Contingency Table in the output window will change to the one in
:numref:`fig6-2`.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig6-2.*
   :alt: Contingency table with row percentages for ``speaker`` and 
         ``utterance``
   :name: fig6-2

   Contingency table for the ``speaker`` and ``utterance`` variables, with row
   percentages
   
.. ----------------------------------------------------------------------------

What we are looking at here is the percentage of utterances made by each 
character. In other words, 50\% of ``makka-pakka``’s utterances are ``pip``,
and the other 50\% are ``onk``. Let us contrast this with the table we get when
we calculate column percentages (uncheck ``Row`` and check ``Column`` in the
``Cells`` options window), see :numref:`fig6-3`. In this version, what we are
seeing is the percentage of characters associated with each utterance. For
instance, whenever the utterance ``ee`` is made (in this data set), 100\% of
the time it is a Tombliboo saying it.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig6-3.*
   :alt: Contingency table with column percentages for ``speaker`` and ``utterance``
   :name: fig6-3

   Contingency table for the ``speaker`` and ``utterance`` variables, with
   column percentages
   
.. ----------------------------------------------------------------------------

.. |nightgarden|                       replace:: ``nightgarden``
.. _nightgarden:                       ../../_static/data/nightgarden.omv
