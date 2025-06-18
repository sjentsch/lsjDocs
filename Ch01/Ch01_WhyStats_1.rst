.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

On the psychology of statistics
-------------------------------

To the surprise of many students, statistics is a fairly significant
part of a psychological education. To the surprise of no-one, statistics
is very rarely the *favourite* part of one’s psychological education.
After all, if you really loved the idea of doing statistics, you would
probably be enrolled in a statistics class right now, not a psychology
class. So, not surprisingly, there is a pretty large proportion of the
student base that is not happy about the fact that psychology has so much
statistics in it. In view of this, I thought that the right place to
start might be to answer some of the more common questions that people
have about stats.

A big part of this issue at hand relates to the very idea of statistics.
What is it? What is it there for? And why are scientists so bloody
obsessed with it? These are all good questions, when you think about it.
So let us start with the last one. As a group, scientists seem to be
bizarrely fixated on running statistical tests on everything. In fact,
we use statistics so often that we sometimes forget to explain to people
why we do. It is a kind of article of faith among scientists – and
especially social scientists – that your findings can not be trusted until
you have done some stats. Undergraduate students might be forgiven for
thinking that we are all completely mad, because no-one takes the time to
answer one very simple question:

   *Why do you do statistics? Why do not scientists just use common
   sense?*

It is a naive question in some ways, but most good questions are. There is
a lot of good answers to it,\ [#]_ but for my money, the best answer is a
really simple one: we do not trust ourselves enough. We worry that we are
human, and susceptible to all of the biases, temptations and frailties
that humans suffer from. Much of statistics is basically a safeguard.
Using “common sense” to evaluate evidence means trusting gut instincts,
relying on verbal arguments and on using the raw power of human reason
to come up with the right answer. Most scientists do not think this
approach is likely to work.

In fact, come to think of it, this sounds a lot like a psychological
question to me, and since I do work in a psychology department, it seems
like a good idea to dig a little deeper here. Is it really plausible to
think that this “common sense” approach is very trustworthy? Verbal
arguments have to be constructed in language, and all languages have
biases – some things are harder to say than others, and not necessarily
because they are false (e.g., quantum electrodynamics is a good theory,
but hard to explain in words). The instincts of our “gut” are not
designed to solve scientific problems, they are designed to handle day-to-day
inferences – and given that biological evolution is slower than
cultural change, we should say that they are designed to solve the day-to-day
problems for a *different world* than the one we live in. Most
fundamentally, reasoning sensibly requires people to engage in
“induction”, making wise guesses and going beyond the immediate evidence
of the senses to make generalisations about the world. If you think that
you can do that without being influenced by various distractors, well, I
have a bridge in London I would like to sell you. Heck, as the next section
shows, we can not even solve “deductive” problems (ones where no guessing
is required) without being influenced by our pre-existing biases.

The curse of belief bias
~~~~~~~~~~~~~~~~~~~~~~~~

People are mostly pretty smart. We are smarter than the other
species that we share the planet with (though many people might
disagree). Our minds are quite amazing things, and we seem to be capable
of the most incredible feats of thought and reason. That does not make us
perfect though. And among the many things that psychologists have shown
over the years is that we really do find it hard to be neutral, to
evaluate evidence impartially and without being swayed by pre-existing
biases. A good example of this is the **belief bias effect** in logical
reasoning: if you ask people to decide whether a particular argument is
logically valid (i.e., the conclusion would be true if the premises were
true), we tend to be influenced by the believability of the conclusion,
even when we should not. For instance, here is a valid argument where the
conclusion is believable:

   | All cigarettes are expensive (Premise 1)
   | Some addictive things are inexpensive (Premise 2)
   | Therefore, some addictive things are not cigarettes (Conclusion)

And here is a valid argument where the conclusion is not believable:

   | All addictive things are expensive (Premise 1)
   | Some cigarettes are inexpensive (Premise 2)
   | Therefore, some cigarettes are not addictive (Conclusion)

The logical *structure* of argument #2 is identical to the structure of
argument #1, and they are both valid. However, in the second argument,
there are good reasons to think that premise 1 is incorrect, and as a
result it is probably the case that the conclusion is also incorrect. But
that is entirely irrelevant to the topic at hand; an argument is
deductively valid if the conclusion is a logical consequence of the
premises. That is, a valid argument does not have to involve true
statements.

On the other hand, here is an invalid argument that has a believable
conclusion:

   | All addictive things are expensive (Premise 1)
   | Some cigarettes are inexpensive (Premise 2)
   | Therefore, some addictive things are not cigarettes (Conclusion)

And finally, an invalid argument with an unbelievable conclusion:

   | All cigarettes are expensive (Premise 1)
   | Some addictive things are inexpensive (Premise 2)
   | Therefore, some cigarettes are not addictive (Conclusion)

Now, suppose that people really are perfectly able to set aside their
pre-existing biases about what is true and what is not, and purely
evaluate an argument on its logical merits. We would expect 100\% of people
to say that the valid arguments are valid, and 0\% of people to say that
the invalid arguments are valid. So if you ran an experiment looking at
this, you would expect to see data like this:

+-------------------------+-----------------------+------------------------+
|                         | conclusion feels true | conclusion feels false |
+=========================+=======================+========================+
| **argument is valid**   | 100\% say “valid”     | 100\% say “valid”      |
+-------------------------+-----------------------+------------------------+
| **argument is invalid** | 0\% say “valid”       | 0\% say “valid”        |
+-------------------------+-----------------------+------------------------+

If the psychological data looked like this (or even a good approximation
to this), we might feel safe in just trusting our gut instincts. That
is, it would be perfectly okay just to let scientists evaluate data based on
their common sense, and not bother with all this murky statistics stuff.
However, you guys have taken psych classes, and by now you probably know
where this is going.

In a classic study, :ref:`Evans et al. (1983) <Evans_1983>` ran an experiment
looking at exactly this. What they found is that when pre-existing biases
(i.e., beliefs) were in agreement with the structure of the data, everything
went the way you would hope:

+-------------------------+-----------------------+------------------------+
|                         | conclusion feels true | conclusion feels false |
+=========================+=======================+========================+
| **argument is valid**   | 92\% say “valid”      |                        |
+-------------------------+-----------------------+------------------------+
| **argument is invalid** |                       | 8\% say “valid”        |
+-------------------------+-----------------------+------------------------+

Not perfect, but that is pretty good. But look what happens when our
intuitive feelings about the truth of the conclusion run against the
logical structure of the argument:

+-------------------------+-----------------------+------------------------+
|                         | conclusion feels true | conclusion feels false |
+=========================+=======================+========================+
| **argument is valid**   | 92\% say “valid”      | *46\% say “valid”*     |
+-------------------------+-----------------------+------------------------+
| **argument is invalid** | *92\% say “valid”*    | 8\% say “valid”        |
+-------------------------+-----------------------+------------------------+

Oh dear, that is not as good. Apparently, when people are presented with
a strong argument that contradicts our pre-existing beliefs, we find it
pretty hard to even perceive it to be a strong argument (people only did
so 46\% of the time). Even worse, when people are presented with a weak
argument that agrees with our pre-existing biases, almost no-one can see
that the argument is weak (people got that one wrong 92\% of the
time!).\ [#]_

If you think about it, it is not as if these data are horribly damning.
Overall, people did do better than chance at compensating for their
prior biases, since about 60\% of people’s judgements were correct (you would
expect 50\% by chance). Even so, if you were a professional “evaluator of
evidence”, and someone came along and offered you a magic tool that
improves your chances of making the right decision from 60\% to (say)
95\%, you would probably jump at it, right? Of course you would. Thankfully,
we actually do have a tool that can do this. But it is not magic, it is
statistics. So that is reason #1 why scientists love statistics. It is
just *too easy* for us to “believe what we want to believe”. So instead,
if we want to “believe in the data”, we are going to need a bit of help
to keep our personal biases under control. That is what statistics does,
it helps keep us honest.

------

.. [#]
   Including the suggestion that common sense is in short supply among
   scientists.

.. [#]
   In my more cynical moments I feel like this fact alone explains 95\%
   of what I read on the internet.
