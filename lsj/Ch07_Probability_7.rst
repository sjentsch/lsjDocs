.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Summary
-------

In this chapter we’ve talked about probability. We’ve talked about what
probability means and why statisticians can’t agree on what it means. We
talked about the rules that probabilities have to obey. And we
introduced the idea of a probability distribution and spent a good chunk
of the chapter talking about some of the more important probability
distributions that statisticians work with. The section by section
breakdown looks like this:

-  `Probability theory versus statistics 
   <Ch07_Probability_1.html#how-are-probability-and-statistics-different>`__  

-  `Frequentist versus Bayesian views of probability 
   <Ch07_Probability_2.html#what-does-probability-mean>`__

-  `Basics of probability theory 
   <Ch07_Probability_3.html#basic-probability-theory>`__

-  `Binomial distribution <Ch07_Probability_4.html#the-binomial-distribution>`__,
   `Normal distribution <Ch07_Probability_5.html#the-normal-distribution>`__, and
   `Other useful distributions <Ch07_Probability_6.html#other-useful-distributions>`__

As you’d expect, my coverage is by no means exhaustive. Probability theory is
a large branch of mathematics in its own right, entirely separate from its
application to statistics and data analysis. As such, there are thousands of
books written on the subject and universities generally offer multiple classes
devoted entirely to probability theory. Even the “simpler” task of documenting
standard probability distributions is a big topic. I’ve described five standard
probability distributions in this chapter, but sitting on my bookshelf I have a
45-chapter book called “Statistical Distributions” (`Evans, 2000 
<References.html#evans-2000>`__\ ) that lists a *lot* more than that.
Fortunately for you, very little of this is necessary. You’re unlikely to need
to know dozens of statistical distributions when you go out and do real world
data analysis, and you definitely won’t need them for this book, but it never
hurts to know that there’s other possibilities out there.

Picking up on that last point, there’s a sense in which this whole chapter is
something of a digression. Many undergraduate psychology classes on statistics
skim over this content very quickly (I know mine did), and even the more
advanced classes will often “forget” to revisit the basic foundations of the
field. Most academic psychologists would not know the difference between
probability and density, and until recently very few would have been aware of
the difference between Bayesian and frequentist probability. However, I think
it’s important to understand these things before moving onto the applications.
For example, there are a lot of rules about what you’re “allowed” to say when
doing statistical inference and many of these can seem arbitrary and weird.
However, they start to make sense if you understand that there is this Bayesian
/ frequentist distinction. Similarly, in Chapter `Comparing two means
<Ch11_tTest.html#comparing-two-means>`__ we’re going to talk about something
called the *t*-test, and if you really want to have a grasp of the mechanics
of the *t*-test it really helps to have a sense of what a *t*-distribution
actually looks like. You get the idea, I hope.
