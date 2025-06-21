.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

On the relationship between ANOVA and the Student *t*-test
----------------------------------------------------------

There is one last thing I want to point out before finishing. It is something
that a lot of people find kind of surprising, but it is worth knowing about. An
ANOVA with two groups is identical to the Student *t*-test. No, really. It is
not just that they are similar, but they are actually equivalent in every
meaningful way. I will not try to prove that this is always true, but I will
show you a single concrete demonstration. Suppose that, instead of running an
ANOVA on our ``mood.gain ~ drug`` model, let us instead do it using ``therapy``
as the predictor. If we run this ANOVA we get an *F*-statistic of F(1,16) =
1.708, and a *p*-value = 0.210. Since we only have two groups, I did not
actually need to resort to an ANOVA, I could have just decided to run a Student
*t*-test. So let us see what happens when I do that: I get a *t*-statistic of
*t*(16) = -1.307 and a *p*-value = 0.210. Curiously, the *p*-values are
identical. Once again we obtain a value of *p* = 0.210. But what about the test
statistic? Having run a *t*-test instead of an ANOVA, we get a somewhat
different answer, namely *t*(16) = -1.307. However, there is a fairly
straightforward relationship here. If we square the *t*-statistic then we get
the *F*-statistic from before: -1.307² = 1.708.
