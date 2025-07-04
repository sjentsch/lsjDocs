.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Learning the basics, and learning them in jamovi
------------------------------------------------

Okay, that was a long list. And even that listing is massively incomplete.
There really are a *lot* of big ideas in statistics that I have not covered. It
can seem pretty depressing to finish a textbook with about 500 pages only to be
told that this is only the beginning, especially when you start to suspect that
half of the stuff you have been taught is wrong. For instance, there are a lot
of people in the field who would strongly argue against the use of the
classical ANOVA model, yet I have devoted two whole chapters to it! Standard
ANOVA can be attacked from a Bayesian perspective, or from a robust statistics
perspective, or even from a “it is just plain wrong” perspective (people very
frequently use ANOVA when they should actually be using mixed models). So why
learn it at all?

As I see it, there are two key arguments. Firstly, there is the pure pragmatism
argument. Rightly or wrongly, ANOVA is widely used. If you want to understand
the scientific literature, you need to understand ANOVA. And secondly, there is
the “incremental knowledge” argument. In the same way that it was handy to have
seen one-way ANOVA before trying to learn factorial ANOVA, understanding ANOVA
is helpful for understanding more advanced tools, because a lot of those tools
extend on or modify the basic ANOVA setup in some way. For instance, although
mixed models are way more useful than ANOVA and regression, I have never heard
of anyone learning how mixed models work without first having worked through
ANOVA and regression. You have to learn to crawl before you can climb a
mountain.

Actually, I want to push this point a bit further. One thing that I have done a
lot of in this book is talk about fundamentals. I spent a lot of time on
probability theory. I talked about the theory of estimation and hypothesis
tests in more detail than I needed to. Why did I do all this? Looking back, you
might ask whether I really *needed* to spend all that time talking about what a
probability distribution is, or why there was even a section on probability
density. If the goal of the book was to teach you how to run a *t*-test or an
ANOVA, was all that really necessary? Was this all just a huge waste of
everyone’s time?

The answer, I hope you will agree, is no. The goal of an introductory stats is
*not* to teach ANOVA. It is not to teach *t*-tests, or regressions, or
histograms, or *p*-values. The goal is to start you on the path towards
becoming a skilled data analyst. And in order for you to become a skilled data
analyst, you need to be able to do more than ANOVA, more than *t*-tests,
regressions and histograms. You need to be able to *think properly* about data.
You need to be able to learn the more advanced statistical models that I talked
about in the last section, and to understand the theory upon which they are
based. And you need to have access to software that will let you use those
advanced tools. And this is where, in my opinion at least, all that extra time
I have spent on the fundamentals pays off. If you understand probability
theory, you will find it much easier to switch from frequentist analyses to
Bayesian ones.

In short, I think that the big payoff for learning statistics this way is
*extensibility*. For a book that only covers the very basics of data analysis,
this book has a massive overhead in terms of learning probability theory and so
on. There is a whole lot of other things that it pushes you to learn besides
the specific analyses that are covered here. So if your goal had been to learn
how to run an ANOVA in the minimum possible time, well, this book was not a
good choice. But as I say, I do not think that is your goal. *I* think you want
to learn how to do data analysis. And if that really is your goal, you want to
make sure that the skills you learn in your introductory stats class are
naturally and cleanly extensible to the more complicated models that you need
in real-world data analysis. You want to make sure that you learn to use the
same tools that real data analysts use, so that you can learn to do what they
do. And so yeah, okay, you are a beginner right now (or you were when you
started this book), but that does not mean you should be given a dumbed-down
story, a story in which I do not tell you about probability density, or a story
where I do not tell you about the nightmare that is factorial ANOVA with
unbalanced designs. And it does not mean that you should be given baby toys
instead of proper data analysis tools. Beginners are not dumb, they just lack
knowledge. What you need is *not* to have the complexities of real-world data
analysis hidden from from you. What you need are the skills and tools that will
let you handle those complexities when they inevitably ambush you in the real
world.

And what I hope is that this book is able to help you with that.

Author’s note – If you see anything clever sounding in this book that does not
seem to have a reference, I can absolutely promise you that the idea was
someone else’s. This is an introductory textbook: none of the ideas are
original. I will take responsibility for all the errors, but I can not take
credit for any of the good stuff. Everything smart in this book came from
someone else.
