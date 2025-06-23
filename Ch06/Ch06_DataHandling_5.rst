.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_, and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_, and `Sebastian Jentschke <https://www4.uib.no/en/find-employees/Sebastian.Jentschke>_`

Extracting a subset of the data
-------------------------------

One very important kind of data handling is being able to extract a particular
subset of the data. For instance, you might be interested only in analysing the
data from one experimental condition, or you may want to look closely at the
data from people over 50 years in age. To achieve this, one could either use
a filter or create a new computed variable using the ``FILTER()`` function.
Regardless of the similar names, the two approaches work slightly differently.
Whereas filters apply to the whole data set (i.e., the same filter expression
is applied to all analyses), the ``FILTER()`` function permits you to generate
a new variable that permits you to decide for which analyses you would use
that variable (e.g., to conduct only some analyses separately for certain
subgroups).

Using filters in jamovi
~~~~~~~~~~~~~~~~~~~~~~~

To get jamovi to filter the subset of the data corresponding to the
observations that you are interested in, we will use the |nightgarden|_ data
set. If you are reading the whole chapter in one sitting, then you should
already have this data set loaded into a jamovi window. Let us focus on the
two variables ``speaker`` and ``utterance`` (see :doc:`Ch06_DataHandling_1`
if you have forgotten what those variables look like). Suppose that what I
want to do is pull out only those utterances that were made by
``makka-pakka``. To that end, we need to specify a filter in jamovi. First
open up a filter window by clicking on ``Filters`` on the main jamovi ``Data``
toolbar. Then, in the ``Filter 1`` text box, next to the ``=`` sign, type the
following, including the single quote marks:

.. code-block:: text

   speaker == "makka-pakka"

When you have done this, you will see that a new column has been added to the
spreadsheet window (see :numref:`fig6-10`), labelled ``Filter 1``, with the
cases where ``speaker`` is not ``makka-pakka`` greyed-out (i.e., filtered out)
and, conversely, the cases where ``speaker`` is ``makka-pakka`` have a green
check mark indicating they are filtered in. You can test this by running
``Exploration`` → ``Descriptives``, assigning ``speaker`` to the ``Variables``-
box and checking ``Frequency tables``. Go on, try it!

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig6-10.*
   :alt: Creating a subset using ``Filters``
   :name: fig6-10

   Creating a subset of the |nightgarden|_ data set using the jamovi
   ``Filters`` option
   
.. ----------------------------------------------------------------------------

Following on from this simple example, you can also build up more complex
filters using logical expressions in jamovi. For instance, suppose I wanted to
keep only those cases when the utterance is either ``pip`` or ``oo``. In this
case in the ``Filter 1`` text box, next to the ``=`` sign, you would type the
following:

.. code-block:: text

   utterance == "pip" or utterance == "oo"


Creating filtered variables
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Quite often one may want to run separate analyses for certain subgroups
without affecting all analyses contained in your jamovi data set. To achieve
that one needs to split a variable up into several different variables, each
corresponding to one subgroup. For instance, in our |nightgarden|_ data set,
I might want to create subsets of the ``utterance`` variable for every
character. One can achieve this by creating new computed variables that makes
use of the ``FILTER()`` function with two arguments, the variable that needs
to be split into groups and a filter expression (like the one that we used
above) for selecting a particular subgroup:

.. code-block:: text

   FILTER(utterance, speaker == "upsy-daisy")
   FILTER(utterance, speaker == "tombliboo")
   FILTER(utterance, speaker == "makka-pakka")

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig6-11.*
   :alt: Using a computed variable for creating a filtered variable
   :name: fig6-11

   Using a computed variable for creating a filtered variable
   
.. ----------------------------------------------------------------------------

How a computed variable can be used to create a filtered variable is shown in
:numref:`fig6-11`. Ideally, one would name those variables using a combination
of the variable that was split (``utterance``) with an indicator of which
subgroup was selected (e.g., ``utterance_upsy-daisy``).

.. ----------------------------------------------------------------------------

.. figure:: ../_images/fig6-12.*
   :alt: Filtered variables in the spreadsheet created using the functions
         above
   :name: fig6-12

   Filtered variables in the spreadsheet created using the functions above

.. ----------------------------------------------------------------------------

Once these variables have been created (see :numref:`fig6-12`), one can use
them to run separate analyses for each of the subgroups. However, the
|nightgarden|_ dataset that we used here was merely a demonstration. It is
perhaps not the most useful data set for this purpose…

   
.. ----------------------------------------------------------------------------

.. |nightgarden|                       replace:: ``nightgarden``
.. _nightgarden:                       ../../_statics/data/nightgarden.omv
