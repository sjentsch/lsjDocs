.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

The “role” of variables: predictors and outcomes
------------------------------------------------

I’ve got one last piece of terminology that I need to explain to you
before moving away from variables. Normally, when we do some research we
end up with lots of different variables. Then, when we analyse our data,
we usually try to explain some of the variables in terms of some of the
other variables. It’s important to keep the two roles “thing doing the
explaining” and “thing being explained” distinct. So let’s be clear
about this now. First, we might as well get used to the idea of using
mathematical symbols to describe variables, since it’s going to happen
over and over again. Let’s denote the “to be explained” variable ``Y``,
and denote the variables “doing the explaining” as ``X_1``, ``X_2``, etc.

When we are doing an analysis we have different names for ``X`` and
``Y``, since they play different roles in the analysis. The classical names
for these roles are **independent variable** (IV) and **dependent variable**
(DV). The IV is the variable that you use to do the explaining (i.e., ``X``)
and the DV is the variable being explained (i.e., ``Y``). The logic behind
these names goes like this: if there really is a relationship between ``X``
and ``Y`` then we can say that ``Y`` depends on ``X``, and if we have
designed our study “properly” then ``X`` isn’t dependent on anything else.
However, I personally find those names horrible. They’re hard to remember and
they’re highly misleading because (a) the IV is never actually “independent of
everything else”, and (b) if there’s no relationship then the DV doesn’t
actually depend on the IV. And in fact, because I’m not the only person who
thinks that IV and DV are just awful names, there are a number of alternatives
that I find more appealing. The terms that I’ll use in this book are
**predictors** and **outcomes**. The idea here is that what you’re trying to
do is use ``X`` (the predictors) to make guesses about ``Y`` (the outcomes).\ [#]_
This is summarised in :numref:`tab-ivdv`.

.. table:: The terminology used to distinguish between different roles that a
   variable can play when analysing a data set. Note that this book will
   tend to avoid the classical terminology in favour of the newer names.
   :name: tab-ivdv

   +------------------------+---------------------------+-------------+
   | role of the variable   | classical name            | modern name |
   +========================+===========================+=============+
   | “to be explained”      | dependent variable (DV)   | outcome     |
   +------------------------+---------------------------+-------------+
   | “to do the explaining” | independent variable (IV) | predictor   |
   +------------------------+---------------------------+-------------+

------

.. [#]
   Annoyingly though, there’s a lot of different names used out there. I
   won’t list all of them – there would be no point in doing that –
   other than to note that “response variable” is sometimes used where
   I’ve used “outcome”. Sigh. This sort of terminological confusion is
   very common, I’m afraid.
