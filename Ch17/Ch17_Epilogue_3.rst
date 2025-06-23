.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Statistical models missing from the book
----------------------------------------

Statistics is a huge field. The core tools that I have described in this book
(χ²-tests, *t*-tests, regression and ANOVA) are basic tools that are widely
used in everyday data analysis, and they form the core of most books on
introductory statistics. However, there are a lot of other tools out there.
There are so very many data analysis situations that these tools do not cover,
and it would be great to give you a sense of just how much more there is, for
example:

-  **Non-linear regression.** When discussing regression in chapter
   :doc:`../Ch12/Ch12_Regression`, we saw that regression assumes that the
   relationship between predictors and outcomes is linear. On the other hand,
   when we talked about the simpler problem of correlation, we saw that there
   exist tools (e.g., Spearman correlations) that are able to assess non-linear 
   relationships between variables. There are a number of tools in statistics 
   that can be used to do non-linear regression. For instance, some non-linear 
   regression models assume that the relationship between predictors and 
   outcomes is monotonic (e.g., isotonic regression), while others assume that 
   it is smooth but not necessarily monotonic (e.g., Lowess regression), while 
   others assume that the relationship is of a known form that happens to be 
   non-linear (e.g., polynomial regression).

-  **Logistic regression.** Yet another variation on regression occurs when the
   outcome variable is binary |nominal|, multinomial |nominal| (several groups)
   or ordinal |ordinal|, but the predictors are continuous |continuous|. For
   instance, suppose you are investigating social media, and you want to know 
   if it is possible to predict whether or not someone is on Twitter as a 
   function of their income, their age, and a range of other variables. This is
   basically a regression model, but you can not use regular linear regression
   because the outcome variable is categorical (e.g., whether you are either on
   Twitter or you are not). Because the outcome variable is categorical, there 
   is no way that the residuals could possibly be normally distributed. There 
   are a number of tools that statisticians can apply to this situation, the 
   most prominent of which is logistic regression.

-  **The General Linear Model (GLM).** The GLM is actually a family of models
   that includes logistic regression, linear regression, (some) non-linear 
   regression, ANOVA and many others. The basic idea in the GLM is essentially 
   the same idea that underpins linear models, but it allows for the idea that 
   your data might not be normally distributed, and allows for non-linear
   relationships between predictors and outcomes. There are a lot of very handy 
   analyses that you can run that fall within the GLM, so it is a very useful
   thing to know about.

-  **Survival analysis.** In chapter :doc:`../Ch02/Ch02_StudyDesign`, I talked
   about “differential attrition”, the tendency for people to leave the study
   in a non-random fashion. Back then, I was talking about it as a potential
   methodological concern, but there are a lot of situations in which
   differential attrition is actually the thing you are interested in. Suppose,
   for instance, you are interested in finding out how long people play
   different kinds of computer games in a single session. Do people tend to
   play RTS (real time strategy) games for longer stretches than FPS (first
   person shooter) games? You might design your study like this. People come
   into the lab, and they can play for as long or as little as they like. Once
   they are finished, you record the time they spent playing. However, due to
   ethical restrictions, let us suppose that you cannot allow them to keep
   playing longer than two hours. A lot of people will stop playing before the
   wo hour limit, so you know exactly how long they played. But some people
   will run into the two hour limit, and so you do not know how long they would
   have kept playing if you would been able to continue the study. As a
   consequence, your data are systematically *censored*: you are missing all of
   the very long times. How do you analyse this data sensibly? This is the
   problem that survival analysis solves. It is specifically designed to handle 
   this situation, where you are systematically missing one “side” of the data 
   because the study ended. It is very widely used in health research,  and in 
   that context it is often literally used to analyse survival. For  instance, 
   you may be tracking people with a particular type of cancer, some  who have 
   received treatment A and others who have received treatment B, but  you only 
   have funding to track them for five years. At the end of the study period 
   some people are alive, others are not. In this context, survival  analysis 
   is useful for determining which treatment is more effective, and  telling
   you about the risk of death that people face over time.

-  **Mixed models.** Repeated measures ANOVA is often used in situations where
   you have observations clustered within experimental units. A good example of 
   this is when you track individual people across multiple time points. Let us 
   say you are tracking happiness over time, for two people. Aaron’s happiness 
   starts at 10, then drops to 8, and then to 6. Belinda’s happiness starts at 
   6, then rises to 8 and then to 10. Both of these two people have the same 
   “overall” level of happiness (the average across the three time points is 
   8), so a repeated measures ANOVA analysis would treat Aaron and Belinda the
   same way. But that is clearly wrong. Aaron’s happiness is decreasing,
   whereas Belinda’s is increasing. If you want to optimally analyse data from 
   an experiment where people can change over time, then you need a more 
   powerful tool than repeated measures ANOVA. The tools that people use to 
   solve this problem are called “mixed” models, because they are designed to 
   learn about individual experimental units (e.g., happiness of individual 
   people over time) as well as overall effects (e.g., the effect of money on 
   happiness over time). Repeated measures ANOVA is perhaps the simplest 
   example of a mixed model, but there is a lot you can do with mixed models 
   that you can not do with repeated measures ANOVA.

-  **Multidimensional scaling.** Factor analysis is an example of an
   “unsupervised learning” model. What this means is that, unlike most of the 
   “supervised learning” tools I have mentioned, you can not divide up your 
   variables into predictors and outcomes. Regression is supervised learning 
   whereas factor analysis is unsupervised learning. It is not the only type of 
   unsupervised learning model however. For example, in factor analysis one is 
   concerned with the analysis of correlations between variables. However, 
   there are many situations where you are actually interested in analysing 
   similarities or dissimilarities between objects, items or people. There are 
   a number of tools that you can use in this situation, the best known of 
   which is multidimensional scaling (MDS). In MDS, the idea is to find a
   “geometric” representation of your items. Each item is “plotted” as a point 
   in some space, and the distance between two points is a measure
   of how dissimilar those items are.

-  **Clustering.** Another example of an unsupervised learning model is
   clustering (also referred to as classification), in which you want to
   organise all of your items into meaningful groups, such that similar items 
   are assigned to the same groups. A lot of clustering is unsupervised, 
   meaning that you do not know anything about what the groups are, you just 
   have to guess. There are other “supervised clustering” situations where you 
   need to predict group memberships on the basis of other variables, and those 
   group memberships are actually observables. Logistic regression is a good 
   example of a tool that works this way. However, when you do not actually 
   know the group memberships, you have to use different tools (e.g., *k*-means 
   clustering). There are even situations where you want to do something 
   called “semi-supervised clustering”, in which you know the group memberships
   for some items but not others. As you can probably guess, clustering is a 
   pretty big topic, and a pretty useful thing to know about.

-  **Causal models.** One thing that I have not talked about much is how you
   can use statistical modelling to learn about the causal relationships 
   between variables. For instance, consider the following three variables 
   which might be of interest when thinking about how someone died in a firing 
   squad. We might want to measure whether or not an execution order was given 
   (variable A), whether or not a marksman fired their gun (variable B), and 
   whether or not the person got hit with a bullet (variable C). These three 
   variables are all correlated with one another (e.g., there is a correlation 
   between guns being fired and people getting hit with bullets), but we
   actually want to make stronger statements about them than merely talking 
   about correlations. We want to talk about causation. We want to be able to 
   say that the execution order (A) causes the marksman to fire (B) which 
   causes someone to get shot (C). We can express this by a directed arrow 
   notation: we write it as A → B → C. This “causal chain” is a fundamentally 
   different explanation for events than one in which the marksman fires first, 
   which causes the shooting B → C, and then causes the executioner to 
   “retroactively” issue the execution order, B → A. This “common effect” model 
   says that A and C are both caused by B. You can see why these are different. 
   In the first causal model, if we had managed to stop the executioner from 
   issuing the order (intervening to change A), then no shooting would have 
   happened. In the second model, the shooting would have happened any way 
   because the marksman was *not* following the execution order. There is a big
   literature in statistics on trying to understand the causal relationships 
   between variables, and a number of different tools exist to help you test 
   different causal stories about your data. The most widely used of these 
   tools (in psychology at least) is structural equations modelling (SEM), and 
   at some point I would like to extend the book to talk about it.

Of course, even this listing is incomplete. I have not mentioned time series
analysis, item response theory, market basket analysis, classification and
regression trees, or any of a huge range of other topics. However, the list
that I have given above is essentially my wish list. Sure, it would double the
length of the book, but it would mean that the scope has become broad enough to
cover most things that applied researchers in psychology would need to use.

.. ----------------------------------------------------------------------------

.. |continuous|                        image:: ../_images/variable-continuous.*
   :width: 16px
 
.. |nominal|                           image:: ../_images/variable-nominal.*
   :width: 16px

.. |ordinal|                           image:: ../_images/variable-ordinal.*
   :width: 16px
