.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

The spreadsheet
---------------

It is possible to simply begin typing values into the jamovi spreadsheet as
you would in any other spreadsheet software. Alternatively, existing data
sets can be opened in jamovi (see the section “Loading data in jamovi”
further down on the page).

In jamovi data is represented in a spreadsheet with each column representing
a “variable” and each row representing a “case” or “participant”.


Data Variables
~~~~~~~~~~~~~~

The most commonly used variables in jamovi are ``Data`` variables, these
variables simply contain data either loaded from a data file, or “typed in”
by the user. ``Data`` variables can be one of four measurement levels.
These levels are designated by the symbol in the header of the
variable’s column:

- The ``ID`` variable type |ID| is unique to jamovi. It’s intended for variables
  that contain identifiers that you would almost never want to analyse.
  For example, a persons name, or a participant ID. Specifying an ID
  variable type can improve performance when interacting with very large
  data sets.

- ``Nominal`` variables |nominal| are for categorical variables which are text
  labels, for example a column called Gender with the values ``Male`` and
  ``Female`` would be nominal. So would a person’s name. Nominal variable
  values can also have a numeric value. These variables are used most often
  when importing data which codes values with numbers rather than text. For
  example, a column in a dataset may contain the values 1 for ``Male``, and 2
  for ``Female``. It is possible to add nice “human-readable” labels to these
  values with the variable editor (more on this later).

- ``Ordinal`` variables |ordinal| are like ``Nominal`` variables, except the
  values have a specific order. An example is a Likert scale with 3 being
  “strongly agree” and -3 being “strongly disagree”.

- ``Continuous`` variables |continuous| are variables which exist on a continuous
  scale. Examples might be height or weight. This is also referred to as
  “interval scale” or “ratio scale”.

In addition, you can also specify different data types: variables have a
data type of either ``Text``, ``Integer`` or ``Decimal``.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_measurementlevels.*
   :alt: Measurement levels and data types in jamovi
   :name: fig-measurementlevels

   Window to set measurement levels and data types in jamovi.
   
.. ----------------------------------------------------------------------------

When starting with a blank spreadsheet and typing values in the variable type
will change automatically depending on the data you enter. This isa good way
to get a feel for which variable types go with which sorts of data. Similarly,
when opening a data file jamovi will try and guess the variable type from the
data in each column. In both cases this automatic approach may not be correct,
and it may be necessary to manually specify the variable type with the variable
editor.

.. _variable_editor:

The variable editor can be opened by selecting ``Setup`` from the ``Data``
ribbon or by double-clicking on the variable column header. The variable
editor allows you to change the name of the variable and, for data variables,
the measure type, the order of the value levels, and the label displayed for
each level. The variable editor can be dismissed by clicking ``↑``.

New variables can be inserted or appended to the data set using the ``Add``
button from the ``Data`` tab. The ``Add`` button also allows the addition
of computed variables.

Sometimes you want to change the variable level. This can happen for all sorts
of reasons. Sometimes when you import data from files, it can come to you in
the wrong format. Numbers sometimes get imported as nominal |nominal|, text
values. Dates may get imported as text. Participant-ID values |ID| can
sometimes be read as continuous |continuous|: nominal values |nominal| can
sometimes be read as ordinal |ordinal| or even continuous |continuous|. There’s
a good chance that sometimes you’ll want to convert a variable from one
measurement level into another one. Or, to use the correct term, you want to
**coerce** the variable from one class into another.

If you want to change a variable’s measurement level then you can do this in
the jamovi ``Data`` view. Click on the variable name in the top row of the data
table and then select the desired measurement level under ``Measure Type`` –
``continuous`` |continuous|, ``ordinal`` |ordinal| or ``nominal`` |nominal|.


Computed variables
~~~~~~~~~~~~~~~~~~

Computed Variables are those which take their value by performing a
computation on other variables. Computed Variables can be used for a range of
purposes, including log transforms, *z*-scores, sum-scores, negative scoring
and means. There is another variable type, Transformed variables, that can be
used to “recode” variables (e.g., when inverting items). This variable type is
briefly described at the end of the subsection :ref:`EFA_in_jamovi` and in
:numref:`fig-efa7`.

Computed variables can be added to the data set with the ``Add`` button
available on the ``Data`` tab. This will produce a formula box where you can
specify the formula. The usual arithmetic operators are available. Some
examples of formulas are:

.. code-block:: text

   A + B
   LOG10(len)
   MEAN(A, B)
   (dose - VMEAN(dose)) / VSTDEV(dose)

In order, these are the sum of ``A`` and ``B``, a log (base 10) transform
of ``len``, the mean of ``A`` and ``B``, and the *z*-score of the variable
``dose``. :numref:`fig-computedvariable` shows the jamovi screen for the
new variable computed as the *z*-score of ``dose`` (from the ``Tooth Growth``
example data set).

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_computedvariable.*
   :alt: Computed variable: *z*-score of ``dose``
   :name: fig-computedvariable

   A newly computed variable, the *z*-score of ``dose``.
   
.. ----------------------------------------------------------------------------

*V-functions*

Several functions are already available in jamovi and available from the
drop down box labelled *f*\ :sub:`x`. A number of functions appear in pairs,
one prefixed with a V and the other not. V functions perform their
calculation on a variable as a whole, where as non-V functions perform
their calculation row by row. For example, ``MEAN(A, B)`` will produce the
mean of ``A`` and ``B`` for each row. Where as ``VMEAN(A)`` gives the mean of
all the values in ``A``.


Loading data in jamovi
~~~~~~~~~~~~~~~~~~~~~~

There are several different types of files that are likely to be
relevant to us when doing data analysis. There are two in particular
that are especially important from the perspective of this book:

-  *jamovi files* are those with a ``.omv`` file extension. This is the
   standard kind of file that jamovi uses to store data, and variables
   and analyses.

-  *Comma separated value (CSV) files* are those with a ``.csv`` file
   extension. These are just regular old text files and they can be
   opened with many different software programs. It’s quite typical for
   people to store data in CSV files, precisely because they’re so
   simple.

There are also several other kinds of data file that you might want to
import into jamovi. For instance, you might want to open Microsoft Excel
spreadsheets (``.xlsx`` files), or data files that have been saved in the
native file formats for other statistics software, such as SPSS or SAS.

Whichever file formats you are using, it’s a good idea to create a folder or
folders especially for your jamovi data sets and analyses and to make sure
you keep these backed up regularly.

To open a file select the main jamovi menu (``☰``; top left hand corner),
select ``Open`` and then choose from the files listed under ``This PC`` if you
want to open an file stored on your computer or select an example data set by
choosing ``Data Library``. The example files in this book can be found within
the ``Data Library`` → ``learning statistics with jamovi`` (or ``lsj-data``).


Importing data from CSV files
*****************************

One quite commonly used data format is the humble “comma separated value”
file, also called a CSV file, and usually bearing the file extension ``.csv``.
CSV files are just plain old-fashioned text files and what they store is
basically just a table of data. This is illustrated in
:numref:`fig-booksalescsv`, which shows a file called |booksales|_ that I’ve
created. As you can see, each row represents the book sales data for one
month. The first row doesn’t contain actual data though, it has the names of
the variables.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_booksalescsv.*
   :alt: |booksales| data file
   :name: fig-booksalescsv

   The |booksales|_ data file. On the left I’ve opened the file using a spreadsheet
   program (LibreOffice), which shows that the file is basically a table. On the right
   the same file is open in a standard text editor (the TextEdit program on a Mac),
   which shows how the file is formatted. The entries in the table are wrapped in quote
   marks and separated by commas.

.. ----------------------------------------------------------------------------

It’s easy to open CSV files in jamovi. From the jamovi main menu (``☰``; top
left hand corner) choose ``Open`` and browse to where you have stored the CSV
file on your computer. If you’re on a Mac, it’ll look like the usual Finder
window that you use to choose a file; on Windows it looks like an Explorer
window. I’m assuming that you’re familiar with your own computer, so you
should have no problem finding the CSV-file that you want to import! Find the
one you want, then click on the ``Open`` button.

There are a few things that you can check to make sure that the data
gets imported correctly:

-  Heading. Does the first row of the file contain the names for each
   variable - a “header” row? The |booksales|_ file has a header,
   so that’s a yes.

-  Separator. What character is used to separate different entries? In
   most CSV files this will be a comma (it is “comma separated” after
   all).

-  Decimal. What character is used to specify the decimal point? In
   English speaking countries this is almost always a period (i.e.,
   ``.``). That’s not universally true though, many European countries
   use a comma.

-  Quote. What character is used to denote a block of text? That’s
   usually going to be a double quote mark (``"``). It is for the
   |booksales|_ file.

Throughout this book I’ve assumed that your data are stored as a jamovi
``.omv`` file or as a “properly” formatted CSV file. However, in real
life that’s not a terribly plausible assumption to make so I’d better
talk about some of the other possibilities that you might run into.

The first thing I should point out is that if your data are saved as a
text file but aren’t *quite* in the proper CSV format then there’s still
a pretty good chance that jamovi will be able to open it. You just need
to try it and see if it works. Sometimes though you will need to change
some of the formatting. The ones that I’ve often found myself needing to
change are:

-  ``header``. A lot of the time when you’re storing data as a CSV file
   the first row actually contains the column names and not data. If
   that’s not true then it’s a good idea to open up the CSV file in a
   spreadsheet programme such as LibreOffice and add the header row
   manually.

-  ``sep``. As the name “comma separated value” indicates, the values in
   a row of a CSV file are usually separated by commas. This isn’t
   universal, however. In Europe the decimal point is typically written
   as ``,`` instead of ``.`` and as a consequence it would be somewhat
   awkward to use ``,`` as the separator. Therefore it is not unusual to
   use ``;`` instead of ``,`` as the separator. At other times, I’ve
   seen a TAB character used.

-  ``quote``. It’s conventional in CSV files to include a quoting
   character for textual data. As you can see by looking at the
   |booksales|_ file, this is usually a double quote character,
   ``"``. But sometimes there is no quoting character at all, or you
   might see a single quote mark ``'`` used instead.

-  ``skip``. It’s actually very common to receive CSV files in which the
   first few rows have nothing to do with the actual data. Instead, they
   provide a human readable summary of where the data came from, or
   maybe they include some technical info that doesn’t relate to the
   data.

-  ``missing values``. Often you’ll get given data with missing values.
   For one reason or another, some entries in the table are missing. The
   data file needs to include a “special” value to indicate that the
   entry is missing. By default jamovi assumes that this value is
   ``NA``,\ [#]_ for both numeric and text data, so you should make
   sure that, where necessary, all missing values in the CSV file are
   replaced with ``99`` (or ``-9999``; whichever you choose) before
   opening / importing the file into jamovi. Once you have opened /
   imported the file into jamovi all the missing values are converted to
   blank or greyed out cells in the jamovi spreadsheet view. You can
   also change the missing value for each variable as an option in the
   ``Data`` → ``Setup`` view.

Importing data from other statistics packages
*********************************************

The commands listed above are the main ones we’ll need for data files in
this book. But in real life we have many more possibilities. For
example, you might want to read data files in from other statistics
programs. Since SPSS is probably the most widely used statistics package
in psychology, it’s worth mentioning that jamovi can also import SPSS
data files (file extension ``.sav``). Just follow the instructions above
for how to open a CSV file, but this time navigate to the ``.sav`` file
you want to import.

As far as other statistical software goes, jamovi can also directly open
/ import a wealth of other formats such as R, SAS, STATA, Excel,
LibreOffice, and JSON.

------

.. [#]
   You can change the default value for missing values in jamovi from the
   settings menu (``⋮``, top right corner), but this only works at the time
   of importing data files into jamovi. The default missing value in the 
   dataset should not be a valid number or value associated with any of the
   variables, e.g. you could use ``-9999`` as this is unlikely to be a valid
   value.
   
.. |booksales|                         replace:: ``booksales.csv``
.. _booksales:                         ../_static/data/booksales.csv

.. |ID|                               image:: ../_images/variable-id.*
   :width: 16px

.. |continuous|                       image:: ../_images/variable-continuous.*
   :width: 16px

.. |nominal|                          image:: ../_images/variable-nominal.*
   :width: 16px

.. |ordinal|                          image:: ../_images/variable-ordinal.*
   :width: 16px
