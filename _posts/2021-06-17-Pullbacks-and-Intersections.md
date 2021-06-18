---
layout: post
math: true
published: true
---
Sometimes a pullback square is an intersection!
Here's a short post about something cute that came up in my research this week.

Aside from [NCNGT][NCNGT], which has been very lovely,
my math this week has been carefully walking through a small side proposition
in a paper I'm working on with [Ty Ghaswala][Ty].
The idea is that graphs of groups come with a notion of a covering space due to Bass,
and étale groupoids come with their own notion of covering spaces
(for us, we're following the definition in Bridson–Haefliger),
and given that you can construct an étale groupoid associated to any graph of groups,
I wanted to reconcile the two notions.
The proof ends up being a story of very careful bookkeeping;
I spent much more of this week than I expected trying to gently pin down what goes where
and why and balance the sudden explosion of notation it seemed to require—not the most fun,
but so it goes. And then right at the very end I had this delightful little puzzle. Let me tell you about it.

So I happened to be staring at the following commutative diagram of groups and homomorphisms,
all of which are injective in the particular case I was concerned with

$$\require{AMScd}\begin{CD}
  \mathscr{L}_{\hat e} @>f_{\hat e}>> \mathscr{G}_e \\
  @V\iota_{\hat e}VV @VV\operatorname{ad}(\delta_{\hat e})\iota_eV \\
  \mathscr{L}_w @>f_w>> \mathscr{G}_v.
\end{CD}$$

It's not really important what these groups *are,*
but in case you're curious this is a commutative diagram associated to a morphism of graphs of groups—in
my particular case, a covering map.

Anyway, I wanted to know, is the image of $$\mathscr{L}_e$$ under these maps
equal to the intersection $$f_w(\mathscr{G}_w) \cap \operatorname{ad}(\delta_{\hat e})\iota_e(\mathscr{G}_e)$$?
Since the situation is pretty general, I wondered if there was maybe a universal property argument:
like, if in the situation above, the square is always a *pullback square,*
then maybe we would be able to show that the two subgroups above were equal.

It turns out that I had it kind of backwards:
Given injective homomorphisms $$f\colon H \to G$$ and $$g\colon K \to G$$, the *pullback*
$$H\times_G K$$ is (up to unique isomorphism) the intersection $$f(H) \cap g(K)$$.
Recall that the pullback
is characterized by the following universal property:
it fits in the following commutative diagram

$$\begin{CD}
  H\times_G K @>\pi_2>> K \\
  @V\pi_1VV @VVgV \\
  H @>f>> G,
\end{CD}$$

and is universal for this property in the sense that given a group $$L$$
fitting into the commutative diagram

$$\begin{CD}
  L @>p_2>> K \\
  @Vp_1VV @VVgV \\
  H @>f>> G
\end{CD}$$

there is a unique homomorphism $$q\colon L \to H\times_GK$$ such that
$$\pi_2q = p_2$$ and $$\pi_1q = p_1.$$
(If there was justice and not MathJax in this world, I'd draw the full commutative diagram I'm alluding to here.)

So! Assuming $$f$$ and $$g$$ are injective, let's prove that $$H\times_GK$$ is the intersection
$$f(H)\cap g(K)$$.
This is not hard: first observe that the intersection admits maps $$\pi_1 \colon f(H)\cap g(K) \to H$$
and $$\pi_2\colon f(H)\cap g(K) \to K$$:
$$\pi_1$$ takes $$g \in f(H)\cap g(K)$$, recognizes we can write it as $$f(\hat g)$$
for a unique $$\hat g$$ in $$H$$, and sends $$g$$ to $$\hat g$$.
Injectivity of $$f$$ assures that this really defines a well-defined homomorphism,
while general properties of functions assure that $$\pi_1$$ is injective.
The compositions $$f\pi_1$$ and $$g\pi_2$$ are the natural inclusion $$\iota\colon f(H)\cap g(K) \to G$$.
The map $$\pi_2$$ is defined similarly.
Next observe that any group $$L$$ fitting into the commutative diagram above
clearly maps into $$f(H)\cap g(K)$$, in other words,
the map $$fp_1 = gp_2$$ factor through a map $$q\colon L \to f(H)\cap g(K)$$ as $$\iota q$$.
From here it's not hard to argue that in fact $$\pi_1q = p_1$$ and $$\pi_2q = p_2$$; I'll leave it to you.

Even though in my particular situation I had the universals backwards,
I did find this realization clarifying:
it showed that to prove my result,
I needed to show that $$\mathscr{L}_e$$ way up above has the universal property of the pullback,
for which it suffices to argue that given an element in the intersection
$$f_w(\mathscr{L}_w) \cap \operatorname{ad}(\delta_{\hat e})\iota_e(\mathscr{G}_e)$$,
we can pull it back (as it were) and show that it really comes from an element of $$\mathscr{L}_e$$.
This turned out to be true thanks to an extra property my situation enjoys!
