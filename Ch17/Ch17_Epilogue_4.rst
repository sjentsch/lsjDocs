.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Other ways of doing inference
-----------------------------

A different sense in which this book is incomplete is that it focuses pretty
heavily on a very narrow and old-fashioned view of how inferential statistics
should be done. In chapter :doc:`../Ch08/Ch08_Estimation` I talked a little
bit about the idea of unbiased estimators, sampling distributions and so on.
In chapter :doc:`../Ch09/Ch09_HypothesisTesting` I talked about the theory of
null hypothesis significance testing and *p*-values. These ideas have been
around since the early 20th century, and the tools that I have talked about in
the book rely very heavily on the theoretical ideas from that time. I have felt
obligated to stick to those topics because the vast majority of data analysis
in science is also reliant on those ideas. However, the theory of statistics
is not restricted to those topics and, whilst everyone should know about them
because of their practical importance, in many respects those ideas do not
represent best practice for contemporary data analysis. One of the things that
I am especially happy with is that I have been able to go a little beyond this.
Chapter :doc:`../Ch16/Ch16_Bayes` now presents the Bayesian perspective in a
reasonable amount of detail, but the book overall is still pretty heavily
weighted towards the frequentist orthodoxy. Additionally, there are a number
of other approaches to inference that are worth mentioning:

-  **Bootstrapping.** Throughout the book, whenever I have introduced a
   hypothesis test, I have had a strong tendency just to make assertions like
   “the sampling distribution for BLAH is a *t*-distribution” or something like
   that. In some cases, I have actually attempted to justify this assertion. 
   For example, when talking about χ²-tests in chapter
   :doc:`../Ch10/Ch10_ChiSquare`, I made reference to the known relationship
   between normal distributions and χ²-distributions (see chapter
   :doc:`../Ch07/Ch07_Probability` to explain how we end up assuming that the
   sampling distribution of the goodness-of-fit statistic is χ². However, it is
   also the case that a lot of these sampling distributions are, well, wrong.
   The χ²-test is a good example. It is based on an assumption about the
   distribution of your data, an assumption which is known to be wrong for
   small sample sizes! Back in the early 20th century, there was not much you
   could do about this situation. Statisticians had developed mathematical
   results that said that “under assumptions BLAH about the data, the
   sampling distribution is approximately BLAH”, and that was about the best
   you could do. A lot of times they did not even have that. There are lots of
   data analysis situations for which no-one has found a mathematical solution
   for the sampling distributions that you need. And so up until the late
   20th century, the corresponding tests did not exist or did not work. 
   However, computers have changed all that now. There are lots of fancy 
   tricks, and some not-so-fancy, that you can use to get around it. The 
   simplest of these is bootstrapping, and in it is simplest form it is 
   incredibly simple. What you do is simulate the results of your experiment 
   lots and lots of times, under the twin assumptions that (a) the null 
   hypothesis is true and (b) the unknown population distribution actually 
   looks pretty similar to your raw data. In other words, instead of assuming 
   that the data are (for instance) normally distributed, just assume that the 
   population looks the same as your sample, and then use computers to simulate 
   the sampling distribution for your test statistic if that assumption holds. 
   Despite relying on a somewhat dubious assumption (i.e., the population
   distribution is the same as the sample!) bootstrapping is quick and easy
   method that works remarkably well in practice for lots of data analysis
   problems.

-  **Cross validation.** One question that pops up in my stats classes every
   now and then, usually by a student trying to be provocative, is “Why do we 
   care about inferential statistics at all? Why not just describe your 
   sample?” The answer to the question is usually something like this, “Because 
   our true interest as scientists is not the specific sample that we have 
   observed in the past, we want to make predictions about data we might 
   observe in the future”. A lot of the issues in statistical inference arise 
   because of the fact that we always expect the future to be similar to but a 
   bit different from the past. Or, more generally, new data will not be quite 
   the same as old data. What we do, in a lot of situations, is try to derive
   mathematical rules that help us to draw the inferences that are most likely 
   to be correct for new data, rather than to pick the statements that best 
   describe old data. For instance, given two models A and B, and a data set X 
   you collected today, try to pick the model that will best describe a new 
   data set Y that you are going to collect tomorrow. Sometimes it is 
   convenient to simulate the process, and that is what cross-validation does. 
   What you do is divide your data set into two subsets, X1 and X2. Use the 
   subset X1 to train the model (e.g., estimate regression coefficients, let us 
   say), but then assess the model performance on the other one X2. This gives 
   you a measure of how well the model *generalises* from an old data set to a
   new one, and is often a better measure of how good your model is than if you
   just fit it to the full data set X.

-  **Robust statistics.** Life is messy, and nothing really works the way it is
   supposed to. This is just as true for statistics as it is for anything else, 
   and when trying to analyse data we are often stuck with all sorts of 
   problems in which the data are just messier than they are supposed to be. 
   Variables that are supposed to be normally distributed are not *actually* 
   normally distributed, relationships that are supposed to be linear are not 
   *actually* linear, and some of the observations in your data set are almost 
   certainly junk (i.e., not measuring what they are supposed to). All of this 
   messiness is ignored in most of the statistical theory I developed in this 
   book. However, ignoring a problem does not always solve it. Sometimes, it is
   actually okay to ignore the mess, because some types of statistical tools 
   are “robust”, i.e., if the data do not satisfy your theoretical assumptions 
   they nevertheless still work pretty well. Other types of statistical tools 
   are not robust, and even minor deviations from the theoretical assumptions 
   cause them to break. Robust statistics is a branch of stats concerned with 
   this question, and they talk about things like the “breakdown point” of a 
   statistic. That is, how messy does your data have to be before the statistic 
   cannot be trusted? I touched on this in places. The mean is *not* a robust 
   estimator of the central tendency of a variable, but the median is. For 
   instance, suppose I told you that the ages of my five best friends are 34, 
   39, 31, 43 and 4003 years. How old do you think they are on average? That
   is, what is the true population mean here? If you use the sample mean as
   your estimator of the population mean, you get an answer of 830 years. If 
   you use the sample median as the estimator of the population mean, you get 
   an answer of 39 years. Notice that, even though you are “technically” doing 
   the wrong thing in the second case (using the median to estimate the mean!)
   you are actually getting a better answer. The problem here is that one of 
   the observations is clearly, obviously, a lie. I do not have a friend aged 
   4003 years. It is probably a typo, I probably meant to type 43. But what if 
   I had typed 53 instead of 43, or 34 instead of 43? Could you be sure if this 
   was a typo or not? Sometimes the errors in the data are subtle, so you can 
   not detect them just by eyeballing the sample, but they are still errors 
   that contaminate your data, and they still affect your conclusions. Robust 
   statistics is concerned with how you can make *safe* inferences even when 
   faced with contamination that you do not know about. It is pretty cool 
   stuff.
