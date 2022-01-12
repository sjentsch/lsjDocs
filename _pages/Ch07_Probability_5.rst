.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

The normal distribution
-----------------------

While the binomial distribution is conceptually the simplest
distribution to understand, it’s not the most important one. That
particular honour goes to the **normal distribution**, also referred to
as “the bell curve” or a “Gaussian distribution”. A normal distribution
is described using two parameters: the mean of the distribution *µ* and
the standard deviation of the distribution *σ*.

The notation that we sometimes use to say that a variable *X* is
normally distributed is as follows:

X ~ Normal(µ, σ)

Of course, that’s just notation. It doesn’t tell us anything interesting
about the normal distribution itself. As was the case with the binomial
distribution, I have included the formula for the normal distribution in
this book, because I think it’s important enough that everyone who
learns statistics should at least look at it, but since this is an
introductory text I don’t want to focus on it, so I’ve tucked it away in
:numref:`tab-distformulas`.

.. ----------------------------------------------------------------------------

.. _fig-standardNormal:
.. figure:: ../_images/lsj_standardNormal.*
   :alt: Binomial distribution: θ = 1/2 and N = 20 (left) or N = 1000 (right) 

   The normal distribution with mean μ = 0 and standard deviation σ = 1. The
   x-axis corresponds to the value of some variable, and the y-axis tells us
   something about how likely we are to observe that value. However, notice
   that the y-axis is labelled “Probability Density” and not “Probability”.
   There is a subtle and somewhat frustrating characteristic of continuous
   distributions that makes the y axis behave a bit oddly: the height of the
   curve here isn’t actually the probability of observing a particular x value.
   On the other hand, it is true that the heights of the curve tells you which
   x values are more likely (the higher ones!; see `Probability density   
   <Ch07_Probability_5.html#probability-density>`__ for all the annoying
   details).
  
.. ----------------------------------------------------------------------------

Instead of focusing on the maths, let’s try to get a sense for what it
means for a variable to be normally distributed. To that end, have a
look at :numref:`fig-standardNormal` which plots a normal distribution with
mean *µ* = 0 and standard deviation *σ* = 1. You can see where the name “bell
curve” comes from; it looks a bit like a bell. Notice that, unlike the plots
that I drew to illustrate the binomial distribution, the picture of the normal
distribution in :numref:`fig-standardNormal` shows a smooth
curve instead of “histogram-like” bars. This isn’t an arbitrary choice,
the normal distribution is continuous whereas the binomial is discrete.
For instance, in the die rolling example from the last section it was
possible to get 3 skulls or 4 skulls, but impossible to get 3.9 skulls.
The figures that I drew in the previous section reflected this fact. In
:numref:`fig-binomSkulls20`, for instance, there’s a bar
located at *X* = 3 and another one at *X* = 4 but there’s
nothing in between. Continuous quantities don’t have this constraint.
For instance, suppose we’re talking about the weather. The temperature
on a pleasant Spring day could be 23 degrees, 24 degrees, 23.9 degrees,
or anything in between since temperature is a continuous variable. And
so a normal distribution might be quite appropriate for describing
Spring temperatures.\ [#]_

.. ----------------------------------------------------------------------------

.. _fig-meanShiftNormal:
.. figure:: ../_images/lsj_meanShiftNormal.*
   :alt: Normal distribution: σ = 1 and µ = 4 (solid) or µ = 7 (dashed)

   Illustration of what happens when you change the mean of a normal
   distribution. The solid line depicts a normal distribution with a mean of
   μ = 4. The dashed line shows a normal distribution with a mean of μ = 7. In
   both cases, the standard deviation is σ = 1. Not surprisingly, the two
   distributions have the same shape, but the dashed line is shifted to the
   right.
  
.. ----------------------------------------------------------------------------

With this in mind, let’s see if we can’t get an intuition for how the
normal distribution works. First, let’s have a look at what happens when
we play around with the parameters of the distribution. To that end,
:numref:`fig-meanShiftNormal` plots normal distributions
that have different means but have the same standard deviation. As you
might expect, all of these distributions have the same “width”. The only
difference between them is that they’ve been shifted to the left or to
the right. In every other respect they’re identical. In contrast, if we
increase the standard deviation while keeping the mean constant, the
peak of the distribution stays in the same place but the distribution
gets wider, as you can see in :numref:`fig-scaleShiftNormal`.

.. ----------------------------------------------------------------------------

.. _fig-scaleShiftNormal:
.. figure:: ../_images/lsj_scaleShiftNormal.*
   :alt: Normal distribution: µ = 5 and σ = 1 (solid) or σ = 2 (dashed)

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
actual mean and standard deviation are, 68.3% of the area falls within 1
standard deviation of the mean. Similarly, 95.4% of the distribution
falls within 2 standard deviations of the mean, and 99.7% of the
distribution is within 3 standard deviations. This idea is illustrated
in :numref:`fig-normAreaSD`.

.. ----------------------------------------------------------------------------

.. _fig-normAreaSD:
.. figure:: ../_images/lsj_normAreaSD.*
   :alt: Normal distribution: area under the curve for 1 and 2 SD

   The area under the curve tells you the probability that an observation falls
   within a particular range. The solid lines plot normal distributions with
   mean μ = 0 and standard deviation σ = 1. The shaded areas illustrate “areas
   under the curve” for two important cases. In panel a, we can see that there
   is a 68.3% chance that an observation will fall within one standard
   deviation of the mean. In panel b, we see that there is a 95.4% chance that
   an observation will fall within two standard deviations of the mean.
     
.. ----------------------------------------------------------------------------

.. _fig-normAreaOther:
.. figure:: ../_images/lsj_normAreaOther.*
   :alt: Normal distribution: area under the curve for 1 SD bordering the mean
         and below 1 SD to the tails of the distribution

   Two more examples of the “area under the curve” idea. There is a 15.9%
   chance that an observation is one standard deviation below the mean or
   smaller (left panel), and a 34.1% chance that the observation is somewhere
   between one standard deviation below the mean and the mean (right panel).
   Notice that if you add these two numbers together you get 15.9% + 34.1% = 
   50%. For normally distributed data, there is a 50% chance that an
   observation falls below the mean. And of course that also implies that there
   is a 50% chance that it falls above the mean.

.. ----------------------------------------------------------------------------

Probability density 
~~~~~~~~~~~~~~~~~~~

There’s something I’ve been trying to hide throughout my discussion of
the normal distribution, something that some introductory textbooks omit
completely. They might be right to do so. This “thing” that I’m hiding
is weird and counter-intuitive even by the admittedly distorted
standards that apply in statistics. Fortunately, it’s not something that
you need to understand at a deep level in order to do basic statistics.
Rather, it’s something that starts to become important later on when you
move beyond the basics. So, if it doesn’t make complete sense, don’t
worry too much, but try to make sure that you follow the gist of it.

Throughout my discussion of the normal distribution there’s been one or
two things that don’t quite make sense. Perhaps you noticed that the
*y*-axis in these figures is labelled “Probability Density” rather
than density. Maybe you noticed that I used *p*\ (X) instead of
*P*\ (X) when giving the formula for the normal distribution.

As it turns out, what is presented here isn’t actually a probability,
it’s something else. To understand what that something is you have to
spend a little time thinking about what it really *means* to say that
*X* is a continuous variable. Let’s say we’re talking about the
temperature outside. The thermometer tells me it’s 23 degrees, but I
know that’s not really true. It’s not *exactly* 23 degrees. Maybe it’s
\23.1 degrees, I think to myself. But I know that that’s not really true
either because it might actually be 23.09 degrees. But I know that...
well, you get the idea. The tricky thing with genuinely continuous
quantities is that you never really know exactly what they are.

Now think about what this implies when we talk about probabilities.
Suppose that tomorrow’s maximum temperature is sampled from a normal
distribution with mean 23 and standard deviation 1. What’s the
probability that the temperature will be *exactly* 23 degrees? The
answer is “zero”, or possibly “a number so close to zero that it might
as well be zero”. Why is this? It’s like trying to throw a dart at an
infinitely small dart board. No matter how good your aim, you’ll never
hit it. In real life you’ll never get a value of exactly 23. It’ll
always be something like 23.1 or 22.99998 or suchlike. In other words,
it’s completely meaningless to talk about the probability that the
temperature is exactly 23 degrees. However, in everyday language if I
told you that it was 23 degrees outside and it turned out to be 22.9998
degrees you probably wouldn’t call me a liar. Because in everyday
language “23 degrees” usually means something like “somewhere between
\22.5 and 23.5 degrees”. And while it doesn’t feel very meaningful to ask
about the probability that the temperature is exactly 23 degrees, it
does seem sensible to ask about the probability that the temperature
lies between 22.5 and 23.5, or between 20 and 30, or any other range of
temperatures.

The point of this discussion is to make clear that when we’re talking
about continuous distributions it’s not meaningful to talk about the
probability of a specific value. However, what we *can* talk about is
the probability that the value lies within a particular range of values.
To find out the probability associated with a particular range what you
need to do is calculate the “area under the curve”. We’ve seen this
concept already, in :numref:`fig-normAreaSD` the shaded areas shown depict
genuine probabilities (e.g., in the left panel of :numref:`fig-normAreaSD`
it shows the probability of observing a value that falls within 1 standard
deviation of the mean).

Okay, so that explains part of the story. I’ve explained a little bit
about how continuous probability distributions should be interpreted
(i.e., area under the curve is the key thing). But what does the formula
for *p*\ (x) that I described earlier actually mean? Obviously,
p*\ (x) doesn’t describe a probability, but what is it? The name
for this quantity *p*\ (x) is a **probability density**, and in
terms of the plots we’ve been drawing it corresponds to the *height* of
the curve. The densities themselves aren’t meaningful in and of
themselves, but they’re “rigged” to ensure that the *area* under the
curve is always interpretable as genuine probabilities. To be honest,
that’s about as much as you really need to know for now.\ [#]_

------

.. [#]
   In practice, the normal distribution is so handy that people tend to
   use it even when the variable isn’t actually continuous. As long as
   there are enough categories (e.g., Likert scale responses to a
   questionnaire), it’s pretty standard practice to use the normal
   distribution as an approximation. This works out much better in
   practice than you’d think.
   
.. [#]
   For those readers who know a little calculus, I’ll give a slightly
   more precise explanation. In the same way that probabilities are
   non-negative numbers that must sum to 1, probability densities are
   non-negative numbers that must integrate to 1 (where the integral is
   taken across all possible values of *X*). To calculate the
   probability that *X* falls between *a* and *b* we
   calculate the definite integral of the density function over the
   corresponding range, :math:`\int_a^b p(x) \ dx`. If you don’t
   remember or never learned calculus, don’t worry about this. It’s not
   needed for this book.
