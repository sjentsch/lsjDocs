.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

The normal distribution
-----------------------

While the binomial distribution is conceptually the simplest
distribution to understand, it is not the most important one. That
particular honour goes to the **normal distribution**, also referred to
as “the bell curve” or a “Gaussian distribution”. A normal distribution
is described using two parameters: the mean of the distribution µ and
the standard deviation of the distribution σ.

The notation that we sometimes use to say that a variable *X* is
normally distributed is as follows:

X ~ Normal(µ, σ)

Of course, that is just notation. It does not tell us anything interesting
about the normal distribution itself. As was the case with the binomial
distribution, I have included the formula for the normal distribution in
this book, because I think it is important enough that everyone who
learns statistics should at least look at it, but since this is an
introductory text I do not want to focus on it, so I have tucked it away in
:numref:`tab-distformulas`.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_standardNormal.*
   :alt: Normal distribution with mean μ = 0 and standard deviation σ = 1 
   :name: fig-standardNormal

   The normal distribution with mean μ = 0 and standard deviation σ = 1. The
   x-axis corresponds to the value of some variable, and the y-axis tells us
   something about how likely we are to observe that value. However, notice
   that the y-axit is labelled “Probability Density” and not “Probability”.
   There is a subtle and somewhat frustrating characteristic of continuous
   distributions that makes the y axis behave a bit oddly: the height of the
   curve here is not actually the probability of observing a particular x value.
   On the other hand, it is true that the heights of the curve tells you which
   x values are more likely (the higher ones!; see :ref:`Probability density
   <probability_density>` for all the annoying details).
  
.. ----------------------------------------------------------------------------

Instead of focusing on the maths, let us try to get a sense for what it
means for a variable to be normally distributed. To that end, have a
look at :numref:`fig-standardNormal` which plots a normal distribution with
mean µ = 0 and standard deviation σ = 1. You can see where the name “bell
curve” comes from; it looks a bit like a bell. Notice that, unlike the plots
that I drew to illustrate the binomial distribution, the picture of the normal
distribution in :numref:`fig-standardNormal` shows a smooth
curve instead of “histogram-like” bars. This is not an arbitrary choice,
the normal distribution is continuous whereas the binomial is discrete.
For instance, in the dice rolling example from the last section it was
possible to get three skulls or four skulls, but impossible to get 3.9 skulls.
The figures that I drew in the previous section reflected this fact. In
:numref:`fig-binomSkulls20`, for instance, there is a bar
located at *X* = 3 and another one at *X* = 4 but there is
nothing in between. Continuous quantities do not have this constraint.
For instance, suppose we are talking about the weather. The temperature
on a pleasant Spring day could be 23 degrees, 24 degrees, 23.9 degrees,
or anything in between since temperature is a continuous variable |continuous|.
And so a normal distribution might be quite appropriate for describing
Spring temperatures.\ [#]_

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_meanShiftNormal.*
   :alt: Normal distribution: σ = 1 and µ = 4 (solid) or µ = 7 (dashed)
   :name: fig-meanShiftNormal

   Illustration of what happens when you change the mean of a normal
   distribution. The solid line depicts a normal distribution with a mean of
   μ = 4. The dashed line shows a normal distribution with a mean of μ = 7. In
   both cases, the standard deviation is σ = 1. Not surprisingly, the two
   distributions have the same shape, but the dashed line is shifted to the
   right.
  
.. ----------------------------------------------------------------------------

With this in mind, let us see if we can not get an intuition for how the
normal distribution works. First, let us have a look at what happens when
we play around with the parameters of the distribution. To that end,
:numref:`fig-meanShiftNormal` plots normal distributions
that have different means but have the same standard deviation. As you
might expect, all of these distributions have the same “width”. The only
difference between them is that they have been shifted to the left or to
the right. In every other respect they are identical. In contrast, if we
increase the standard deviation while keeping the mean constant, the
peak of the distribution stays in the same place but the distribution
gets wider, as you can see in :numref:`fig-scaleShiftNormal`.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_scaleShiftNormal.*
   :alt: Normal distribution: µ = 5 and σ = 1 (solid) or σ = 2 (dashed)
   :name: fig-scaleShiftNormal

   Illustration of what happens when you change the standard deviation of a
   normal distribution. Both distributions plotted in this figure have a mean
   of μ = 5, but they have different standard deviations. The solid line plots
   a distribution with standard deviation σ = 1, and the dashed line shows a
   distribution with standard deviation σ = 2. As a consequence, both
   distributions are “centred” on the same spot, but the dashed line is wider
   than the solid one.
  
.. ----------------------------------------------------------------------------

Notice, though, that when we widen the distribution the height of the
peak shrinks. This has to happen, in the same way that the heights of
the bars that we used to draw a discrete binomial distribution have to
*sum* to 1, the total *area under the curve* for the normal distribution
must equal 1. Before moving on, I want to point out one important
characteristic of the normal distribution. Irrespective of what the
actual mean and standard deviation are, 68.3\% of the area falls within 1
standard deviation of the mean. Similarly, 95.4\% of the distribution
falls within two standard deviations of the mean, and 99.7\% of the
distribution is within three standard deviations. This idea is illustrated
in :numref:`fig-normAreaSD`.

.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_normAreaSD.*
   :alt: Normal distribution: area under the curve for 1 and 2 SD
   :name: fig-normAreaSD

   The area under the curve tells you the probability that an observation falls
   within a particular range. The solid lines plot normal distributions with
   mean μ = 0 and standard deviation σ = 1. The shaded areas illustrate “areas
   under the curve” for two important cases. In the left panel, we can see that
   there is a 68.3\% chance that an observation will fall within one standard
   deviation of the mean. In the right panel, we see that there is a 95.4\%
   chance that an observation will fall within two standard deviations of the
   mean.
     
.. ----------------------------------------------------------------------------

.. figure:: ../_images/lsj_normAreaOther.*
   :alt: Area under the curve for 1 SD bordering the mean and at the tails
   :name: fig-normAreaOther

   Two more examples of the “area under the curve” idea. There is a 15.9\%
   chance that an observation is one standard deviation below the mean or
   smaller (left panel), and a 34.1\% chance that the observation is somewhere
   between one standard deviation below the mean and the mean (right panel).
   Notice that if you add these two numbers together you get 15.9\% + 34.1\% = 
   50\%. For normally distributed data, there is a 50\% chance that an
   observation falls below the mean. And of course that also implies that there
   is a 50\% chance that it falls above the mean.

.. ----------------------------------------------------------------------------

.. _probability_density:

Probability density
~~~~~~~~~~~~~~~~~~~

There is something I have been trying to hide throughout my discussion of
the normal distribution, something that some introductory textbooks omit
completely. They might be right to do so. This “thing” that I am hiding
is weird and counter-intuitive even by the admittedly distorted
standards that apply in statistics. Fortunately, it is not something that
you need to understand at a deep level in order to do basic statistics.
Rather, it is something that starts to become important later on when you
move beyond the basics. So, if it does not make complete sense, do not
worry too much, but try to make sure that you follow the gist of it.

Throughout my discussion of the normal distribution there is been one or
two things that do not quite make sense. Perhaps you noticed that the
*y*-axis in these figures is labelled “Probability Density” rather
than “Density”. Maybe you noticed that I used *p*\ (X) instead of
*P*\ (X) when giving the formula for the normal distribution.

As it turns out, what is presented here is not actually a probability,
it is something else. To understand what that something is you have to
spend a little time thinking about what it really *means* to say that
*X* is a continuous variable |continuous|. Let us say we are talking about
the temperature outside. The thermometer tells me it is 23 degrees, but I
know that is not really true. It is not *exactly* 23 degrees. Maybe it is
\23.1 degrees, I think to myself. But I know that that is not really true
either because it might actually be 23.09 degrees. But I know that…
well, you get the idea. The tricky thing with genuinely continuous
quantities is that you never really know exactly what they are.

Now think about what this implies when we talk about probabilities.
Suppose that tomorrow’s maximum temperature is sampled from a normal
distribution with mean 23 and standard deviation 1. What is the
probability that the temperature will be *exactly* 23 degrees? The
answer is “zero”, or possibly “a number so close to zero that it might
as well be zero”. Why is this? It is like trying to throw a dart at an
infinitely small dart board. No matter how good your aim, you will never
hit it. In real life you will never get a value of exactly 23. It will
always be something like 23.1 or 22.99998 or suchlike. In other words,
it is completely meaningless to talk about the probability that the
temperature is exactly 23 degrees. However, in everyday language if I
told you that it was 23 degrees outside and it turned out to be 22.9998
degrees you probably would not call me a liar. Because in everyday
language “23 degrees” usually means something like “somewhere between
\22.5 and 23.5 degrees”. And while it does not feel very meaningful to ask
about the probability that the temperature is exactly 23 degrees, it
does seem sensible to ask about the probability that the temperature
lies between 22.5 and 23.5, or between 20 and 30, or any other range of
temperatures.

The point of this discussion is to make clear that when we are talking
about continuous distributions it is not meaningful to talk about the
probability of a specific value. However, what we *can* talk about is
the probability that the value lies within a particular range of values.
To find out the probability associated with a particular range what you
need to do is calculate the “area under the curve”. We have seen this
concept already, in :numref:`fig-normAreaSD` the shaded areas shown depict
genuine probabilities (e.g., in the left panel of :numref:`fig-normAreaSD`
it shows the probability of observing a value that falls within one standard
deviation of the mean).

Okay, so that explains part of the story. I have explained a little bit
about how continuous probability distributions should be interpreted
(i.e., area under the curve is the key thing). But what does the formula
for *p*\ (x) that I described earlier actually mean? Obviously,
p*\ (x) does not describe a probability, but what is it? The name
for this quantity *p*\ (x) is a **probability density**, and in
terms of the plots we have been drawing it corresponds to the *height* of
the curve. The densities themselves are not meaningful in and of
themselves, but they are “rigged” to ensure that the *area* under the
curve is always interpretable as genuine probabilities. To be honest,
that is about as much as you really need to know for now.\ [#]_

------

.. [#]
   In practice, the normal distribution is so handy that people tend to
   use it even when the variable is not actually continuous. As long as
   there are enough categories (e.g., Likert scale responses to a
   questionnaire), it is pretty standard practice to use the normal
   distribution as an approximation. This works out much better in
   practice than you would think.
   
.. [#]
   For those readers who know a little calculus, I will give a slightly
   more precise explanation. In the same way that probabilities are
   non-negative numbers that must sum to 1, probability densities are
   non-negative numbers that must integrate to 1 (where the integral is
   taken across all possible values of *X*). To calculate the
   probability that *X* falls between *a* and *b* we
   calculate the definite integral of the density function over the
   corresponding range, :math:`\int_a^b p(x) \ dx`. If you do not
   remember or never learned calculus, do not worry about this. It is not
   needed for this book.

.. ----------------------------------------------------------------------------

.. |continuous|                        image:: ../_images/variable-continuous.*
   :width: 16px
