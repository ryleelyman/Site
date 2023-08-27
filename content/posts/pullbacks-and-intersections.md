---
title: "Pullbacks and Intersections"
date: 2021-06-17T14:18:01-04:00
math: true
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

{{< katex >}}$$\begin{CD}
  \mathscr{L}_{\hat e} @>f_{\hat e}>> \mathscr{G}_e \\
  @V\iota_{\hat e}VV @VV\operatorname{ad}(\delta_{\hat e})\iota_eV \\
  \mathscr{L}_w @>f_w>> \mathscr{G}_v.
\end{CD}$${{< /katex >}}

It's not really important what these groups *are,*
but in case you're curious this is a commutative diagram associated to a morphism of graphs of groups—in
my particular case, a covering map.

Anyway, I wanted to know, is the image of {{< katex >}}$\mathscr{L}_e${{< /katex >}} under these maps
equal to the intersection {{< katex >}}$f_w(\mathscr{G}_w) \cap \operatorname{ad}(\delta_{\hat e})\iota_e(\mathscr{G}_e)${{< /katex >}}?
Since the situation is pretty general, I wondered if there was maybe a universal property argument:
like, if in the situation above, the square is always a *pullback square,*
then maybe we would be able to show that the two subgroups above were equal.

It turns out that I had it kind of backwards:
Given injective homomorphisms {{< katex >}}$f\colon H \to G${{< /katex >}} and {{< katex >}}$g\colon K \to G${{< /katex >}}, the *pullback*
{{< katex >}}$H\times_G K${{< /katex >}} is (up to unique isomorphism) the intersection {{< katex >}}$f(H) \cap g(K)${{< /katex >}}.
Recall that the pullback
is characterized by the following universal property:
it fits in the following commutative diagram

{{< katex >}}$$\begin{CD}
  H\times_G K @>\pi_2>> K \\
  @V\pi_1VV @VVgV \\
  H @>f>> G,
\end{CD}$${{< /katex >}}

and is universal for this property in the sense that given a group {{< katex >}}$L${{< /katex >}}
fitting into the commutative diagram

{{< katex >}}$$\begin{CD}
  L @>p_2>> K \\
  @Vp_1VV @VVgV \\
  H @>f>> G
\end{CD}$${{< /katex >}}

there is a unique homomorphism {{< katex >}}$q\colon L \to H\times_GK${{< /katex >}} such that
{{< katex >}}$\pi_2q = p_2${{< /katex >}} and {{< katex >}}$\pi_1q = p_1.${{< /katex >}}
(If there was justice and not MathJax in this world, I'd draw the full commutative diagram I'm alluding to here.)

So! Assuming {{< katex >}}$f${{< /katex >}} and {{< katex >}}$g${{< /katex >}} are injective, let's prove that {{< katex >}}$H\times_GK${{< /katex >}} is the intersection
{{< katex >}}$f(H)\cap g(K)${{< /katex >}}.
This is not hard: first observe that the intersection admits maps {{< katex >}}$\pi_1 \colon f(H)\cap g(K) \to H${{< /katex >}}
and {{< katex >}}$\pi_2\colon f(H)\cap g(K) \to K${{< /katex >}}:
{{< katex >}}$\pi_1${{< /katex >}} takes {{< katex >}}$g \in f(H)\cap g(K)${{< /katex >}}, recognizes we can write it as {{< katex >}}$f(\hat g)${{< /katex >}}
for a unique {{< katex >}}$\hat g${{< /katex >}} in {{< katex >}}$H${{< /katex >}}, and sends {{< katex >}}$g${{< /katex >}} to {{< katex >}}$\hat g${{< /katex >}}.
Injectivity of {{< katex >}}$f${{< /katex >}} assures that this really defines a well-defined homomorphism,
while general properties of functions assure that {{< katex >}}$\pi_1${{< /katex >}} is injective.
The compositions {{< katex >}}$f\pi_1${{< /katex >}} and {{< katex >}}$g\pi_2${{< /katex >}} are the natural inclusion {{< katex >}}$\iota\colon f(H)\cap g(K) \to G${{< /katex >}}.
The map {{< katex >}}$\pi_2${{< /katex >}} is defined similarly.
Next observe that any group {{< katex >}}$L${{< /katex >}} fitting into the commutative diagram above
clearly maps into {{< katex >}}$f(H)\cap g(K)${{< /katex >}}, in other words,
the map {{< katex >}}$fp_1 = gp_2${{< /katex >}} factor through a map {{< katex >}}$q\colon L \to f(H)\cap g(K)${{< /katex >}} as {{< katex >}}$\iota q${{< /katex >}}.
From here it's not hard to argue that in fact {{< katex >}}$\pi_1q = p_1${{< /katex >}} and {{< katex >}}$\pi_2q = p_2${{< /katex >}}; I'll leave it to you.

Even though in my particular situation I had the universals backwards,
I did find this realization clarifying:
it showed that to prove my result,
I needed to show that {{< katex >}}$\mathscr{L}_e${{< /katex >}} way up above has the universal property of the pullback,
for which it suffices to argue that given an element in the intersection
{{< katex >}}$f_w(\mathscr{L}_w) \cap \operatorname{ad}(\delta_{\hat e})\iota_e(\mathscr{G}_e)${{< /katex >}},
we can pull it back (as it were) and show that it really comes from an element of {{< katex >}}$\mathscr{L}_e${{< /katex >}}.
This turned out to be true thanks to an extra property my situation enjoys!

[NCNGT]: https://www.ncngt.org
[Ty]: http://cirget.math.uqam.ca/~tyghaswala/


