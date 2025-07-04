.. sectionauthor:: `Danielle J. Navarro <https://djnavarro.net/>`_ and `David R. Foxcroft <https://www.davidfoxcroft.com/>`_

Assumptions of the test(s)
--------------------------

All statistical tests make assumptions, and it is usually a good idea to
check that those assumptions are met. For the χ²-tests discussed
so far in this chapter, the assumptions are:

-  *Expected frequencies are sufficiently large*. Remember how in the previous
   section we saw that the χ² sampling distribution emerges because the
   binomial distribution is pretty similar to a normal distribution? Well,
   like we discussed in chapter :doc:`../Ch07/Ch07_Probability` this is only
   true when the number of observations is sufficiently large. What that means
   in practice is that all of the expected frequencies need to be reasonably
   big. How big is reasonably big? Opinions differ, but the default assumption
   seems to be that you generally would like to see all your expected
   frequencies larger than about 5, though for larger tables you would
   probably be okay if at least 80\% of the the expected frequencies are above
   5 and none of them are below 1. However, from what I have been able to
   discover (e.g., :ref:`Cochran, 1954 <Cochran_1954>`), these seem to have been
   proposed as rough guidelines, not hard and fast rules, and they seem to be
   somewhat conservative (:ref:`Larntz, 1978 <Larntz_1978>`).

-  *Data are independent of one another*. One somewhat hidden assumption
   of the χ²-test is that you have to genuinely believe that the
   observations are independent. Here is what I mean. Suppose I am
   interested in proportion of babies born at a particular hospital that
   are boys. I walk around the maternity wards and observe 20 girls and
   only 10 boys. Seems like a pretty convincing difference, right? But
   later on, it turns out that I had actually walked into the same ward 10
   times and in fact I had only seen two girls and one boy. Not as convincing,
   is it? My original 30 *observations* were massively non-independent,
   and were only in fact equivalent to three independent observations.
   Obviously this is an extreme (and extremely silly) example, but it
   illustrates the basic issue. Non-independence “stuffs things up”.
   Sometimes it causes you to falsely reject the null, as the silly
   hospital example illustrates, but it can go the other way too. To
   give a slightly less stupid example, let us consider what would happen
   if I had done the cards experiment slightly differently Instead of
   asking 200 people to try to imagine sampling one card at random,
   suppose I asked 50 people to select four cards. One possibility would be
   that *everyone* selects one heart, one club, one diamond and one
   spade (in keeping with the “representativeness heuristic”; :ref:`Tversky &
   Kahneman, 1974 <Tversky_1974>`). This is highly non-random behaviour from
   people, but in this case I would get an observed frequency of 50 for all
   four suits. For this example the fact that the observations are
   non-independent (because the four cards that you pick will be related to
   each other) actually leads to the opposite effect, falsely retaining the
   null.

If you happen to find yourself in a situation where independence is
violated, it may be possible to use the McNemar test (which we will
discuss) or the Cochran test (which we will not). Similarly, if your
expected cell counts are too small, check out the Fisher exact test. It
is to these topics that we now turn.
