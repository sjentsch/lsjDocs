.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Statistical theory: A Prelude
=============================

The part on statistical theory is by far the most theoretical, focusing as it
does on the theory of statistical inference. Over the next three chapters my
goal is to give you an introduction to probability theory (chapter 
:doc:`../Ch07/Ch07_Probability`), sampling and estimation (chapter
:doc:`../Ch08/Ch08_Estimation`) and statistical hypothesis testing (chapter
:doc:`../Ch09/Ch09_HypothesisTesting`). Before we get started though, I want
to say something about the big picture. Statistical inference is primarily
about *learning from data*. The goal is no longer merely to describe our data
but to use the data to draw conclusions about the world. To motivate the
discussion I want to spend a bit of time talking about a philosophical puzzle
known as the *riddle of induction*, because it speaks to an issue that will
pop up over and over again throughout the book: statistical inference relies
on *assumptions*. This sounds like a bad thing. In everyday life people say
things like “you should never make assumptions”, and psychology classes often
talk about assumptions and biases as bad things that we should try to avoid.
From personal experience I have learned never to say such things around
philosophers!

On the limits of logical reasoning
----------------------------------

.. epigraph::

   | *The whole art of war consists in getting at what is on the other side of
     the hill, or, in other words, in learning what we do not know from what we 
     do.*
     
   -- Arthur Wellesley, 1st Duke of Wellington

This `quote <https://www.bartleby.com/lit-hub/samuel-arthur-bent/duke-ofwellington/quote>`_
came about as a consequence of a carriage ride across the countryside.
Wellesley and his companion, J. W. Croker, were playing a guessing game, each
trying to predict what would be on the other side of each hill. In every case
it turned out that Wellesley was right and Croker was wrong. Many years later
when Wellesley was asked about the game he explained that “the whole art of
war consists in getting at what is on the other side of the hill”. Indeed, war
is not special in this respect. All of life is a guessing game of one form or
another, and getting by on a day-to-day basis requires us to make good guesses.
So let us play a guessing game of our own.

Suppose you and I are observing the Wellesley-Croker competition and after
every three hills you and I have to predict who will win the next one,
Wellesley or Croker. Let us say that ``W`` refers to a Wellesley victory and
``C`` refers to a Croker victory. After three hills, our data set looks like
this:

.. code-block:: text

   WWW

Our conversation goes like this:

   Three in a row does not mean much. I suppose Wellesley might be better at 
   this than Croker, but it might just be luck. Still, I am a bit of a gambler. 
   I will bet on Wellesley. I agree that three in a row is not informative and 
   I see no reason to prefer Wellesley’s guesses over Croker’s. I can not
   justify betting at this stage. Sorry. No bet for me.

Your gamble paid off: three more hills go by and Wellesley wins all three.
Going into the next round of our game the score is 1 - 0 in favour of you and
our data set looks like this:

.. code-block:: text

   WWW WWW

I have organised the data into blocks of three so that you can see which batch
corresponds to the observations that we had available at each step in our
little side game. After seeing this new batch, our conversation continues:

   Six wins in a row for Duke Wellesley. This is starting to feel a bit
   suspicious. I am still not certain, but I reckon that he is going to win the 
   next one too. I guess I do not see that. Sure, I agree that Wellesley has 
   won six in a row, but I do not see any logical reason why that means he will 
   win the seventh one. No bet. Do you really think so? Fair enough, but my bet 
   worked out last time and I am okay with my choice.

For a second time you were right, and for a second time I was wrong. Wellesley
wins the next three hills, extending his winning record against Croker to 9 - 0.
The data set available to us is now this:

.. code-block:: text

   WWW WWW WWW

And our conversation goes like this:

   Okay, this is pretty obvious. Wellesley is way better at this game.
   We both agree he is going to win the next hill, right? Is there really
   any logical evidence for that? Before we started this game, there
   were lots of possibilities for the first 10 outcomes, and I had no
   idea which one to expect. ``WWW WWW WWW W`` was one possibility, but
   so was ``WCC CWC WWC C`` and ``WWW WWW WWW C`` or even
   ``CCC CCC CCC C``. Because I had no idea what would happen so I would
   have said they were all equally likely. I assume you would have too,
   right? I mean, that is what it *means* to say you have “no idea”,
   is not it? I suppose so. Well then, the observations we have made
   logically rule out all possibilities except two: ``WWW WWW WWW C`` or
   ``WWW WWW WWW W``. Both of these are perfectly consistent with the
   evidence we have encountered so far, are they not? Yes, of course they
   are. Where are you going with this? So what is changed then? At the
   start of our game, you would have agreed with me that these are equally
   plausible and none of the evidence that we have encountered has
   discriminated between these two possibilities. Therefore, both of
   these possibilities remain equally plausible and I see no logical
   reason to prefer one over the other. So yes, while I agree with you
   that Wellesley’s run of nine wins in a row is remarkable, I can not think
   of a good reason to think he will win the 10th hill. No bet. I see your
   point, but I am still willing to chance it. I’m betting on Wellesley.

Wellesley’s winning streak continues for the next three hills. The score in the
Wellesley-Croker game is now 12 - 0, and the score in our game is now 3 - 0. As
we approach the fourth round of our game, our data set is this:

.. code-block:: text

   WWW WWW WWW WWW

And the conversation continues:

   Oh yeah! Three more wins for Wellesley and another victory for me.
   Admit it, I was right about him! I guess we are both betting on
   Wellesley this time around, right? I do not know what to think. I feel
   like we are in the same situation we were in last round, and nothing
   much has changed. There are only two legitimate possibilities for a
   sequence of 13 hills that have not already been ruled out,
   ``WWW WWW WWW WWW C`` and ``WWW WWW WWW WWW W``. It is just like I
   said last time. If all possible outcomes were equally sensible before
   the game started, should not these two be equally sensible now given
   that our observations do not rule out either one? I agree that it
   feels like Wellesley is on an amazing winning streak, but where is the
   logical evidence that the streak will continue? I think you are being
   unreasonable. Why not take a look at *our* scorecard, if you need
   evidence? You are the expert on statistics and you have been using this
   fancy logical analysis, but the fact is you are losing. I am just
   relying on common sense and I am winning. Maybe you should switch
   strategies. Hmm, that is a good point and I do not want to lose the
   game, but I am afraid I do not see any logical evidence that your
   strategy is better than mine. It seems to me that if there were
   someone else watching our game, what they would have observed is a run
   of three wins to you. Their data would look like this: ``YYY``.
   Logically, I do not see that this is any different to our first round
   of watching Wellesley and Croker. Three wins to you does not seem like
   a lot of evidence, and I see no reason to think that your strategy is
   working out any better than mine. If I did not think that ``WWW`` was
   good evidence then for Wellesley being better than Croker at *their*
   game, surely I have no reason now to think that ``YYY`` is good
   evidence that you are better at *ours*? Okay, now I think you are being
   a jerk. I do not see the logical evidence for that.

Learning without making assumptions is a myth
---------------------------------------------

There are lots of different ways in which we could dissect this dialogue, but
since this is a statistics book pitched at psychologists and not an introduction
to the philosophy and psychology of reasoning, I will keep it brief. What I
have described above is sometimes referred to as the riddle of induction. It
seems entirely *reasonable* to think that a 12 - 0 winning record by Wellesley
is pretty strong evidence that he will win the 13th game, but it is not easy to
provide a proper logical justification for this belief. On the contrary,
despite the *obviousness* of the answer, it is not actually possible to justify
betting on Wellesley without relying on some assumption that you do not have
any logical justification for.

The riddle of induction is most associated with the philosophical work of David
Hume and more recently Nelson Goodman, but you can find examples of the problem
popping up in fields as diverse as literature (Lewis Carroll) and machine
learning (the “no free lunch” theorem). There really is something weird about
trying to “learn what we do not know from what we do know”. The critical point
is that assumptions and biases are unavoidable if you want to learn anything
about the world. There is no escape from this, and it is just as true for
statistical inference as it is for human reasoning. In the dialogue I was taking
aim at your perfectly sensible inferences as a human being, but the common
sense reasoning that you relied on is no different to what a statistician would
have done. Your “common sense” half of the dialog relied on an implicit
*assumption* that there exists some difference in skill between Wellesley and
Croker, and what you were doing was trying to work out what that difference in
skill level would be. My “logical analysis” rejects that assumption entirely.
All I was willing to accept is that there are sequences of wins and losses and
that I did not know which sequences would be observed. Throughout the dialogue
I kept insisting that all logically possible data sets were equally plausible
at the start of the Wellesely-Croker game, and the only way in which I ever
revised my beliefs was to eliminate those possibilities that were factually
inconsistent with the observations.

That sounds perfectly sensible on its own terms. In fact, it even sounds like
the hallmark of good deductive reasoning. Like Sherlock Holmes, my approach was
to rule out that which is impossible in the hope that what would be left is the
truth. Yet as we saw, ruling out the impossible *never* led me to make a
prediction. On its own terms everything I said in my half of the dialogue was
entirely correct. An inability to make any predictions is the logical
consequence of making “no assumptions”. In the end I lost our game because you
did make some assumptions and those assumptions turned out to be right. Skill
is a real thing, and because you believed in the existence of skill you were
able to learn that Wellesley had more of it than Croker. Had you relied on a
less sensible assumption to drive your learning you might not have won the game.

Ultimately there are two things you should take away from this. First, as I
have said, you cannot avoid making assumptions if you want to learn anything
from your data. But second, once you realise that assumptions are necessary it
becomes important to make sure you *make the right ones!* A data analysis that
relies on few assumptions is not necessarily better than one that makes many
assumptions, it all depends on whether those assumptions are good ones for your
data. As we go through the rest of this book I will often point out the
assumptions that underpin a particular statistical technique, and how you can
check whether those assumptions are sensible.
