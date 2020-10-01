.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Miscellaneous topics
--------------------

-  **Missing data.** Suppose you’re doing a survey, and you’re
   interested in exercise and weight. You send data to four people. Adam
   says he exercises a lot and is not overweight. Briony says she
   exercises a lot and is not overweight. Carol says she does not
   exercise and is overweight. Dan says he does not exercise and refuses
   to answer the question about his weight. Elaine does not return the
   survey. You now have a missing data problem. There is one entire
   survey missing, and one question missing from another one, What do
   you do about it? Ignoring missing data is not, in general, a safe
   thing to do. Let’s think about Dan’s survey here. Firstly, notice
   that, on the basis of my other responses, I appear to be more similar
   to Carol (neither of us exercise) than to Adam or Briony. So if you
   were forced to guess my weight, you’d guess that I’m closer to her
   than to them. Maybe you’d make some correction for the fact that Adam
   and I are males and Briony and Carol are females. The statistical
   name for this kind of guessing is “imputation”. Doing imputation
   safely is hard, but it’s important, especially when the missing data
   are missing in a systematic way. Because of the fact that people who
   are overweight are often pressured to feel poorly about their weight
   (often thanks to public health campaigns), we actually have reason to
   suspect that the people who are not responding are more likely to be
   overweight than the people who do respond. Imputing a weight to Dan
   means that the number of overweight people in the sample will
   probably rise from 1 out of 3 (if we ignore Dan), to 2 out of 4 (if
   we impute Dan’s weight). Clearly this matters. But doing it sensibly
   is more complicated than it sounds. Earlier, I suggested you should
   treat me like Carol, since we gave the same answer to the exercise
   question. But that’s not quite right. There is a systematic
   difference between us. She answered the question, and I didn’t. Given
   the social pressures faced by overweight people, isn’t it likely that
   I’m *more* overweight than Carol? And of course this is still
   ignoring the fact that it’s not sensible to impute a *single* weight
   to me, as if you actually knew my weight. Instead, what you need to
   do it is impute a range of plausible guesses (referred to as multiple
   imputation), in order to capture the fact that you’re more uncertain
   about my weight than you are about Carol’s. And let’s not get started
   on the problem posed by the fact that Elaine didn’t send in the
   survey. As you can probably guess, dealing with missing data is an
   increasingly important topic. In fact, I’ve been told that a lot of
   journals in some fields will not accept studies that have missing
   data unless some kind of sensible multiple imputation scheme is
   followed.

-  **Power analysis.** In Chapter `Hypothesis testing
   <Ch09_HypothesisTesting.html#hypothesis-testing>`__ I discussed the concept
   of power (i.e., how likely are you to be able to detect an effect if it
   actually exists) and referred to power analysis, a collection of tools that
   are useful for assessing how much power your study has. Power analysis can
   be useful for planning a study (e.g., figuring out how large a sample you’re
   likely to need), but it also serves a useful role in analysing data that you
   already collected. For instance, suppose you get a significant result, and
   you have an estimate of your effect size. You can use this information to
   estimate how much power your study actually had. This is kind of useful,
   especially if your effect size is not large. For instance, suppose you
   reject the null hypothesis at p < 0.05, but you use power analysis to figure
   out that your estimated power was only 0.08. The significant result means
   that, if the null hypothesis was in fact true, there was a 5% chance of
   getting data like this. But the low power means that, even if the null
   hypothesis is false and the effect size was really as small as it looks,
   there was only an 8% chance of getting data like you did. This suggests that
   you need to be pretty cautious, because luck seems to have played a big part
   in your results, one way or the other!

-  **Data analysis using theory-inspired models.** In a few places in
   this book I’ve mentioned response time (RT) data, where you record
   how long it takes someone to do something (e.g., make a simple
   decision). I’ve mentioned that RT data are almost invariably
   non-normal, and positively skewed. Additionally, there’s a thing
   known as the speed-accuracy trade-off: if you try to make decisions
   too quickly (low RT) then you’re likely to make poorer decisions
   (lower accuracy). So if you measure both the accuracy of a
   participant’s decisions and their RT, you’ll probably find that speed
   and accuracy are related. There’s more to the story than this, of
   course, because some people make better decisions than others
   regardless of how fast they’re going. Moreover, speed depends on both
   cognitive processes (i.e., time spent thinking) but also
   physiological ones (e.g., how fast can you move your muscles). It’s
   starting to sound like analysing this data will be a complicated
   process. And indeed it is, but one of the things that you find when
   you dig into the psychological literature is that there already exist
   mathematical models (called “sequential sampling models”) that
   describe how people make simple decisions, and these models take into
   account a lot of the factors I mentioned above. You won’t find any of
   these theoretically-inspired models in a standard statistics
   textbook. Standard stats textbooks describe standard tools, tools
   that could meaningfully be applied in lots of different disciplines,
   not just psychology. ANOVA is an example of a standard tool that is
   just as applicable to psychology as to pharmacology. Sequential
   sampling models are not, they are psychology-specific, more or less.
   This doesn’t make them less powerful tools. In fact, if you’re
   analysing data where people have to make choices quickly you should
   really be using sequential sampling models to analyse the data. Using
   ANOVA or regression or whatever won’t work as well, because the
   theoretical assumptions that underpin them are not well-matched to
   your data. In contrast, sequential sampling models were explicitly
   designed to analyse this specific type of data, and their theoretical
   assumptions are *extremely* well-matched to the data.
