---
title: 'Self-Similar End Spaces'
layout: post
math: true
---

This is the third post in a series on
Katie Mann and Kasra Rafi's paper
[Large-scale geometry of big mapping class groups](https://arxiv.org/abs/1912.10914).
In the previous post we explored an obstruction to coarse boundedness,
while in this one we will introduce a sufficient conditions for $$\operatorname{Map}(\Sigma)$$
to be coarsely bounded.
This post includes proofs that closely follow those in the paper,
which while elementary, get a little involved.
I imagine this will be one of very few moments in the series where I give full proofs.

## Necessary conditions

Suppose that $$\operatorname{Map}(\Sigma)$$ is coarsely bounded.
Then by the contrapositive of the result of the [previous post],
if $$S$$ is a finite-type subsurface of $$\Sigma$$,
there must be a homeomorphism $$f\colon \Sigma \to \Sigma$$
satisfying $$f(S) \cap S = \varnothing$$.
Therefore by the examples given at the end of the previous post,
if $$\Sigma$$ has finitely many maximal ends,
it has at most two,
and if $$\Sigma$$ has nonzero genus, it has infinite genus.
In fact, by a variant of the former condition,
if $$X \subset \operatorname{Ends}(\Sigma)$$ is a finite,
$$\operatorname{Map}(\Sigma)$$-invariant set,
it has cardinality at most two.
(I got worried here a little: what if the invariant ends are isolated and planar,
i.e. punctures?
But then I realized: any subsurface containing all the finitely many punctures of $$\Sigma$$
would be nondisplaceable.)

## Self-similarity

Towards the construction of *sufficient* conditions for $$\operatorname{Map}(\Sigma)$$
to be coarsely bounded,
we introduce the property of *self-similarity* of $$\operatorname{Ends}(\Sigma)$$:
recall that $$\operatorname{Ends}(\Sigma)$$ is a closed subset of the Cantor set,
so the most natural open neighborhoods to work with are *clopen* (closed and open) neighborhoods.
Supposing we have a decomposition

$$\operatorname{Ends}(\Sigma) = E_1 \sqcup E_2$$

of $$\operatorname{Ends}(\Sigma)$$ into clopen subsets,
then *self-similarity* of $$\operatorname{Ends}(\Sigma)$$ is the condition that
one of the subsets, say $$E_1$$, contains a clopen subset $$D$$ such that the pair
$$(D,D \cap \operatorname{Ends}^g(\Sigma))$$ 
is homeomorphic to the pair $$(\operatorname{Ends}(\Sigma),\operatorname{Ends}^g(\Sigma))$$.
Note that we can further split $$E_1$$ into two, and so on,
so this condition is clearly equivalent to the condition that whenever

$$\operatorname{Ends}(\Sigma) = E_1 \sqcup \cdots \sqcup E_n$$

is a decomposition into finitely many clopen subsets,
one of them, say $$E_1$$, contains a clopen subset $$D$$ as above.

Anyway, suppose that $$\Sigma$$ has infinite or zero genus and self-similar end space.
We first show that each finite-type subsurface $$S$$ of $$\Sigma$$ is displaceable
in a strong sense:
after enlarging $$S$$, we may suppose that each boundary component of $$S$$ is separating
(i.e. removing it cuts $$\Sigma$$ into two pieces)
and complementary component of $$\Sigma - S$$
has infinite type and infinite or zero genus;
the complementary components in $$\Sigma - S$$ together with the finite set of punctures of $$S$$
partition $$\operatorname{Ends}(\Sigma)$$ into finitely many clopen subsets,
so some complementary component, call it $$C_0$$,
has end space containing a clopen neighborhood homeomorphic to $$\operatorname{Ends}(\Sigma)$$
(respecting the subspaces of nonplanar ends).

> **Lemma 3.2** ([Mann–Rafi]).
With notation as above, $$C_0$$ contains a finite-type subsurface $$R$$ disjoint from
but homeomorphic to $$S$$
via a homeomorphism $$f \colon \Sigma \to \Sigma$$
satisfying $$f(S) = R$$, $$f(C_0) \supset S$$ and such that the end set of
$$f(C_0) \cap C_0$$ contains a homeomorphic copy of $$\operatorname{Ends}(\Sigma)$$
(respecting the subspaces of nonplanar ends).

Before we sketch the proof, here's an example.
The surface $$\Sigma$$ has a Cantor space of ends, of which exactly one is accumulated by genus.
This end space is self-similar,
because any clopen subset of a Cantor set is itself a Cantor set,
and after chopping the end space into finitely many pieces,
one piece contains the nonplanar end,
and that piece is therefore homeomorphic to the whole end space.
Suppose $$S$$ is a pair of pants (a genus-zero subsurface with three boundary components)
cutting the end space into three pieces.
The claim is that within the piece that contains the nonplanar end,
there is a pair of pants $$R$$ disjoint from $$S$$,
a homeomorphism of $$\Sigma$$ taking $$S$$ to $$R$$
and the "big" complementary component of $$S$$ to the "big" complementary component of $$R$$
(i.e. the ones containing the nonplanar end).
In this case, the intersection of the "big" components is again 
homeomorphic to a Cantor set of ends with one nonplanar end.
By the way, Ian Biringer suggested the name "Cantor tree in early spring" for the surface $$\Sigma$$;
I'm a fan.

![The surface described above with two pairs of pants indicated](/assets/img/cantortreeearlyspring.jpeg)

*Proof.* The proof is ultimately an appeal to the Kerékjártó–Richards classification of surfaces.
Let $$C_0,\ldots,C_n$$ be the components of $$\Sigma - S$$,
where $$C_0$$ is the indicated "big" component.
Write $$E_i$$ for the end set of $$C_i$$, and $$P_S$$ for the set of punctures of $$S$$.
We have

$$\operatorname{Ends}(\Sigma) = E_0 \sqcup \cdots \sqcup E_n \sqcup P_S.$$

Since the end set $$E_0$$ of $$C_0$$ contains a clopen subset $$D$$ 
homeomorphic to $$\operatorname{Ends}(\Sigma)$$
respecting the subset of nonplanar ends,
we may find a decomposition of $$D$$ as

$$D = E'_0 \sqcup \cdots \sqcup E'_n \sqcup P_R,$$

where each $$E'_i$$ is homeomorphic (respecting nonplanar ends) to $$E_i$$,
and $$P_R$$ is a finite collection of isolated planar ends of the same cardinality of $$P_S$$.
There are two things to claim.
The first is that we can find a finite-type subsurface $$R$$ disjoint from $$S$$
with genus equal to that of $$S$$,
puncture set $$P_R$$ and $$n+1$$ boundary components
partitioning the end space of $$\Sigma$$ into
$$E'_1,\ldots, E'_n$$, along with $$P_R$$ and the remaining ends, namely

$$E^R_0 = E'_0 \sqcup (E_0 - D) \sqcup E_1 \sqcup \cdots \sqcup E_n \sqcup P_S.$$

It is clear (replace $$P_S$$ with $$P_R$$, erase the primes and use the decomposition of $$D$$ above)
that this latter set of ends $$E^R_0$$ is actually homeomorphic to $$E_0$$
respecting the subspace of nonplanar ends.
Depending on your comfort level with arguing about subsurfaces,
this may take some thought.
I further claim that we can do this so that each complementary component of $$\Sigma - R$$
also has infinite or zero genus 
(necessarily according to whether the "corresponding" component of $$\Sigma - S$$ does).
For me the key observation in both claims was that I really could 
shuffle finite amounts of genus around to arrange this.

Since $$R$$ and $$S$$ have the same number of punctures, boundary components and the same genus,
there is a homeomorphism from $$S$$ to $$R$$;
we may take it to match up the boundary components 
according to the labeling of the complementary regions,
so for example the boundary component corresponding to $$E_0$$ is sent to the component
corresponding to $$E^R_0$$.
Similarly, for each complementary component of $$\Sigma - S$$,
the corresponding complementary component of $$\Sigma - R$$
has the same genus and homeomorphic end space,
so by the classification of surfaces, the given homeomorphism of the end spaces
extends to a homeomorphism sending the complementary component of $$\Sigma - S$$
to the corresponding component of $$\Sigma - R$$.
These $$n + 2$$ homeomorphisms glue together to yield the desired homeomorphism
$$f \colon \Sigma \to \Sigma$$.
By construction, we have $$f(C_0) \supset S$$ and
since $$f(C_0) \cap C_0$$ contains $$E'_0$$ in its end set,
it contains a homeomorphic copy of $$\operatorname{Ends}(\Sigma)$$
respecting the subspace of nonplanar ends. $$\blacksquare$$

Note that since we only ever enlarged $$S$$ to get it to satisfy all the technical things we desired,
the lemma is actually true for smaller finite-type subsurfaces as well.
Anyway, the lemma is the main tool to prove the following theorem.

> **Proposition 3.1** ([Mann–Rafi]).
Suppose $$\Sigma$$ has self-similar end space and infinite or zero genus.
Then $$\operatorname{Map}(\Sigma)$$ is coarsely bounded.


*Proof.* We aim to show that for any open neighborhood $$U$$ 
of the identity in $$\operatorname{Map}(\Sigma)$$,
there exists a finite set $$F$$ and $$k \ge 1$$ such that
$$\operatorname{Map}(\Sigma) \subset (FU)^k$$.
Without loss of generality,
we may assume that $$U$$ is 

$$U_S = \{[g] \in \operatorname{Map}(\Sigma) : g|_S = 1\}$$

for some finite-type subsurface $$S$$ satisfying the hypotheses and hence the conclusions
of Lemma 3.2 above (note that enlarging $$S$$ *shrinks* $$U_S$$, which is good for our purposes).
That is, we have a subsurface $$R$$ disjoint from $$S$$
and a homeomorphism $$f\colon \Sigma \to \Sigma$$ taking $$S$$ to $$R$$.
The finite set $$F$$ will be the mapping classes of the identity, $$f$$ and $$f^{-1}$$.
It suffices to take $$k = 5$$.

Take $$[g] \in \operatorname{Map}(\Sigma)$$.
If $$g(S) = S$$ and $$g|_S = 1$$, we are done, since $$g \in U$$,
so certainly in $$(FU)^5$$.
If $$g(R) = R$$ and $$g|_R = 1$$, then since $$f(S) = R$$,
we have $$f^{-1}gf(S) = f^{-1}g(R) = f^{-1}(R) = S$$
and $$f^{-1}gf|_S = 1$$. 
In this case we see that $$g \in FUF \subset (FU)^2$$.
This illustrates the strategy:
if we can, using finitely many elements of $$F$$ and $$U$$,
reduce $$g$$ to the case where it is the identity on $$R$$ or $$S$$, we win.
Now, in the notation of Lemma 3.2, the end set $$E_0$$ of $$C_0$$
satisfies the condition that $$E_0 \cap f(E_0)$$
contains a homeomorphic copy $$E'$$ of $$\operatorname{Ends}(\Sigma)$$.
Since $$f(E_0) \cup E_0 = \operatorname{Ends}(\Sigma)$$,
we have a decomposition

$$\operatorname{Ends}(\Sigma) = (E_0 - f(E_0)) \sqcup (E_0 \cap f(E_0)) \sqcup (f(E_0) - E_0),$$

so the intersection of one of these sets with the self-similar set 
$$g(E') \cong \operatorname{Ends}(\Sigma)$$
contains a clopen subset $$E''$$ homeomorphic to $$\operatorname{Ends}(\Sigma)$$.
At the cost of one application of $$f^{-1}$$,
we may assume that $$E''$$ is contained in $$E_0$$,
the end set of the "big" complementary component $$C_0$$ of $$\Sigma - S$$.

Now, notice that $$C_0$$ and $$R$$ taken by themselves
satisfy the hypotheses and hence the conclusions of Lemma 3.2.
This is key: arguing using the "big" collection of ends $$E''$$,
we can find a subsurface $$R'$$ homeomorphic to $$R$$ in $$C_0 \cap g(C_0)$$
and a homeomorphism $$s\colon C_0 \to C_0$$ satisfying $$s(R) = R'$$
and $$R \subset s(C_0 \cap f(C_0))$$.
By choosing $$s$$ carefully, 
we may extend it to a homeomorphism $$\tilde s\colon \Sigma \to \Sigma$$
by declaring it to be the identity on $$\Sigma - C_0$$.
We have $$\tilde s \in U$$.

The advantage of having this $$R'$$ is that we may "undo" $$g$$ on $$S$$
while fixing $$R'$$ via a homeomorphism $$u\colon \Sigma \to \Sigma$$
satisfying $$ug(S) = S$$ and $$ug|_S = 1$$.
This is again a classification of surfaces argument:
the point is that the decomposition of $$\operatorname{Ends}(\Sigma)$$
given by $$S$$ is equivalent to that provided by $$g(S)$$
(the homeomorphism $$g$$ sends one to the other)
and both $$C_0$$ and $$g(C_0)$$ contain $$R'$$,
so after cutting away $$R'$$, the end set decompositions are still equivalent,
so there is a homeomorphism returning $$g(S)$$ to $$S$$ while fixing $$R'$$,
and postcomposing with a homeomorphism supported on $$S$$, 
we may suppose this homeomorphism has the desired properties of $$u$$.

So let's put it together.
We have $$ug \in U$$, so we win if we can write $$u$$ using elements of $$F$$ and $$U$$.
But since $$u$$ is the identity on $$R'$$, the mapping class of $$(\tilde s f)^{-1}u(\tilde sf)$$
is the identity on $$(\tilde s f)^{-1}(R') = S$$.
We have $$(\tilde s f)^{-1}u(\tilde s f) \in U$$,
so $$u \in UFUFU \subset (FU)^3$$, which implies that $$g \in (FU)^4$$.
But remembering that we had to pay an application of $$f^{-1}$$ a few paragraphs back,
we see that the *original* $$g$$ is contained in $$(FU)^5$$. $$\blacksquare$$

[previous post]: {% link _posts/2022-08-12-Nondisplaceable-Subsurfaces.md %}
[Mann–Rafi]: https://arxiv.org/abs/1912.10914
