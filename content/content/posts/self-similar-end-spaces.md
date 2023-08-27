---
title: "Self-similar End Spaces"
date: 2022-08-14T16:16:35-04:00
math: true
---
This is the third post in a series on
Katie Mann and Kasra Rafi's paper
[Large-scale geometry of big mapping class groups](https://arxiv.org/abs/1912.10914).
In the previous post we explored an obstruction to coarse boundedness,
while in this one we will introduce a sufficient condition for {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}
to be coarsely bounded.
This post includes proofs that closely follow those in the paper,
which while elementary, get a little involved.
I imagine this will be one of very few moments in the series where I give full proofs.

## Necessary conditions

Suppose that {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}} is coarsely bounded.
Then by the contrapositive of the result of the [previous post],
if {{< katex >}}$S${{< /katex >}} is a finite-type subsurface of {{< katex >}}$\Sigma${{< /katex >}},
there must be a homeomorphism {{< katex >}}$f\colon \Sigma \to \Sigma${{< /katex >}}
satisfying {{< katex >}}$f(S) \cap S = \varnothing${{< /katex >}}.
Therefore by the examples given at the end of the previous post,
if {{< katex >}}$\Sigma${{< /katex >}} has finitely many maximal ends,
it has at most two,
and if {{< katex >}}$\Sigma${{< /katex >}} has nonzero genus, it has infinite genus.
In fact, by a variant of the former condition,
if {{< katex >}}$X \subset \operatorname{Ends}(\Sigma)${{< /katex >}} is a finite,
{{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}-invariant set,
it has cardinality at most two.
(I got worried here a little: what if the invariant ends are isolated and planar,
i.e. punctures?
But then I realized: any subsurface containing all the finitely many punctures of {{< katex >}}$\Sigma${{< /katex >}}
would be nondisplaceable.)

## Self-similarity

Towards the construction of *sufficient* conditions for {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}
to be coarsely bounded,
we introduce the property of *self-similarity* of {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}}:
recall that {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}} is a closed subset of the Cantor set,
so the most natural open neighborhoods to work with are *clopen* (closed and open) neighborhoods.
Supposing we have a decomposition

{{< katex >}}$\operatorname{Ends}(\Sigma) = E_1 \sqcup E_2${{< /katex >}}

of {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}} into clopen subsets,
then *self-similarity* of {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}} is the condition that
one of the subsets, say {{< katex >}}$E_1${{< /katex >}}, contains a clopen subset {{< katex >}}$D${{< /katex >}} such that the pair
{{< katex >}}$(D,D \cap \operatorname{Ends}^g(\Sigma))${{< /katex >}} 
is homeomorphic to the pair {{< katex >}}$(\operatorname{Ends}(\Sigma),\operatorname{Ends}^g(\Sigma))${{< /katex >}}.
Note that we can further split {{< katex >}}$E_1${{< /katex >}} into two, and so on,
so this condition is clearly equivalent to the condition that whenever

{{< katex >}}$\operatorname{Ends}(\Sigma) = E_1 \sqcup \cdots \sqcup E_n${{< /katex >}}

is a decomposition into finitely many clopen subsets,
one of them, say {{< katex >}}$E_1${{< /katex >}}, contains a clopen subset {{< katex >}}$D${{< /katex >}} as above.

Anyway, suppose that {{< katex >}}$\Sigma${{< /katex >}} has infinite or zero genus and self-similar end space.
We first show that each finite-type subsurface {{< katex >}}$S${{< /katex >}} of {{< katex >}}$\Sigma${{< /katex >}} is displaceable
in a strong sense:
after enlarging {{< katex >}}$S${{< /katex >}}, we may suppose that each boundary component of {{< katex >}}$S${{< /katex >}} is separating
(i.e. removing it cuts {{< katex >}}$\Sigma${{< /katex >}} into two pieces)
and complementary component of {{< katex >}}$\Sigma - S${{< /katex >}}
has infinite type and infinite or zero genus;
the complementary components in {{< katex >}}$\Sigma - S${{< /katex >}} together with the finite set of punctures of {{< katex >}}$S${{< /katex >}}
partition {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}} into finitely many clopen subsets,
so some complementary component, call it {{< katex >}}$C_0${{< /katex >}},
has end space containing a clopen neighborhood homeomorphic to {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}}
(respecting the subspaces of nonplanar ends).

> **Lemma 3.2** ([Mann–Rafi]).
With notation as above, {{< katex >}}$C_0${{< /katex >}} contains a finite-type subsurface {{< katex >}}$R${{< /katex >}} disjoint from
but homeomorphic to {{< katex >}}$S${{< /katex >}}
via a homeomorphism {{< katex >}}$f \colon \Sigma \to \Sigma${{< /katex >}}
satisfying {{< katex >}}$f(S) = R${{< /katex >}}, {{< katex >}}$f(C_0) \supset S${{< /katex >}} and such that the end set of
{{< katex >}}$f(C_0) \cap C_0${{< /katex >}} contains a homeomorphic copy of {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}}
(respecting the subspaces of nonplanar ends).

Before we sketch the proof, here's an example.
The surface {{< katex >}}$\Sigma${{< /katex >}} has a Cantor space of ends, of which exactly one is accumulated by genus.
This end space is self-similar,
because any clopen subset of a Cantor set is itself a Cantor set,
and after chopping the end space into finitely many pieces,
one piece contains the nonplanar end,
and that piece is therefore homeomorphic to the whole end space.
Suppose {{< katex >}}$S${{< /katex >}} is a pair of pants (a genus-zero subsurface with three boundary components)
cutting the end space into three pieces.
The claim is that within the piece that contains the nonplanar end,
there is a pair of pants {{< katex >}}$R${{< /katex >}} disjoint from {{< katex >}}$S${{< /katex >}},
a homeomorphism of {{< katex >}}$\Sigma${{< /katex >}} taking {{< katex >}}$S${{< /katex >}} to {{< katex >}}$R${{< /katex >}}
and the "big" complementary component of {{< katex >}}$S${{< /katex >}} to the "big" complementary component of {{< katex >}}$R${{< /katex >}}
(i.e. the ones containing the nonplanar end).
In this case, the intersection of the "big" components is again 
homeomorphic to a Cantor set of ends with one nonplanar end.
By the way, Ian Biringer suggested the name "Cantor tree in early spring" for the surface {{< katex >}}$\Sigma${{< /katex >}};
I'm a fan.

![The surface described above with two pairs of pants indicated](/assets/img/cantortreeearlyspring.jpeg)

*Proof.* The proof is ultimately an appeal to the Kerékjártó–Richards classification of surfaces.
Let {{< katex >}}$C_0,\ldots,C_n${{< /katex >}} be the components of {{< katex >}}$\Sigma - S${{< /katex >}},
where {{< katex >}}$C_0${{< /katex >}} is the indicated "big" component.
Write {{< katex >}}$E_i${{< /katex >}} for the end set of {{< katex >}}$C_i${{< /katex >}}, and {{< katex >}}$P_S${{< /katex >}} for the set of punctures of {{< katex >}}$S${{< /katex >}}.
We have

{{< katex >}}$\operatorname{Ends}(\Sigma) = E_0 \sqcup \cdots \sqcup E_n \sqcup P_S.${{< /katex >}}

Since the end set {{< katex >}}$E_0${{< /katex >}} of {{< katex >}}$C_0${{< /katex >}} contains a clopen subset {{< katex >}}$D${{< /katex >}} 
homeomorphic to {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}}
respecting the subset of nonplanar ends,
we may find a decomposition of {{< katex >}}$D${{< /katex >}} as

{{< katex >}}$D = E'_0 \sqcup \cdots \sqcup E'_n \sqcup P_R,${{< /katex >}}

where each {{< katex >}}$E'_i${{< /katex >}} is homeomorphic (respecting nonplanar ends) to {{< katex >}}$E_i${{< /katex >}},
and {{< katex >}}$P_R${{< /katex >}} is a finite collection of isolated planar ends of the same cardinality of {{< katex >}}$P_S${{< /katex >}}.
There are two things to claim.
The first is that we can find a finite-type subsurface {{< katex >}}$R${{< /katex >}} disjoint from {{< katex >}}$S${{< /katex >}}
with genus equal to that of {{< katex >}}$S${{< /katex >}},
puncture set {{< katex >}}$P_R${{< /katex >}} and {{< katex >}}$n+1${{< /katex >}} boundary components
partitioning the end space of {{< katex >}}$\Sigma${{< /katex >}} into
{{< katex >}}$E'_1,\ldots, E'_n${{< /katex >}}, along with {{< katex >}}$P_R${{< /katex >}} and the remaining ends, namely

{{< katex >}}$E^R_0 = E'_0 \sqcup (E_0 - D) \sqcup E_1 \sqcup \cdots \sqcup E_n \sqcup P_S.${{< /katex >}}

It is clear (replace {{< katex >}}$P_S${{< /katex >}} with {{< katex >}}$P_R${{< /katex >}}, erase the primes and use the decomposition of {{< katex >}}$D${{< /katex >}} above)
that this latter set of ends {{< katex >}}$E^R_0${{< /katex >}} is actually homeomorphic to {{< katex >}}$E_0${{< /katex >}}
respecting the subspace of nonplanar ends.
Depending on your comfort level with arguing about subsurfaces,
this may take some thought.
I further claim that we can do this so that each complementary component of {{< katex >}}$\Sigma - R${{< /katex >}}
also has infinite or zero genus 
(necessarily according to whether the "corresponding" component of {{< katex >}}$\Sigma - S${{< /katex >}} does).
For me the key observation in both claims was that I really could 
shuffle finite amounts of genus around to arrange this.

Since {{< katex >}}$R${{< /katex >}} and {{< katex >}}$S${{< /katex >}} have the same number of punctures, boundary components and the same genus,
there is a homeomorphism from {{< katex >}}$S${{< /katex >}} to {{< katex >}}$R${{< /katex >}};
we may take it to match up the boundary components 
according to the labeling of the complementary regions,
so for example the boundary component corresponding to {{< katex >}}$E_0${{< /katex >}} is sent to the component
corresponding to {{< katex >}}$E^R_0${{< /katex >}}.
Similarly, for each complementary component of {{< katex >}}$\Sigma - S${{< /katex >}},
the corresponding complementary component of {{< katex >}}$\Sigma - R${{< /katex >}}
has the same genus and homeomorphic end space,
so by the classification of surfaces, the given homeomorphism of the end spaces
extends to a homeomorphism sending the complementary component of {{< katex >}}$\Sigma - S${{< /katex >}}
to the corresponding component of {{< katex >}}$\Sigma - R${{< /katex >}}.
These {{< katex >}}$n + 2${{< /katex >}} homeomorphisms glue together to yield the desired homeomorphism
{{< katex >}}$f \colon \Sigma \to \Sigma${{< /katex >}}.
By construction, we have {{< katex >}}$f(C_0) \supset S${{< /katex >}} and
since {{< katex >}}$f(C_0) \cap C_0${{< /katex >}} contains {{< katex >}}$E'_0${{< /katex >}} in its end set,
it contains a homeomorphic copy of {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}}
respecting the subspace of nonplanar ends. {{< katex >}}$\blacksquare${{< /katex >}}

Note that since we only ever enlarged {{< katex >}}$S${{< /katex >}} to get it to satisfy all the technical things we desired,
the lemma is actually true for smaller finite-type subsurfaces as well.
Anyway, the lemma is the main tool to prove the following theorem.

> **Proposition 3.1** ([Mann–Rafi]).
Suppose {{< katex >}}$\Sigma${{< /katex >}} has self-similar end space and infinite or zero genus.
Then {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}} is coarsely bounded.


*Proof.* We aim to show that for any open neighborhood {{< katex >}}$U${{< /katex >}} 
of the identity in {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}},
there exists a finite set {{< katex >}}$F${{< /katex >}} and {{< katex >}}$k \ge 1${{< /katex >}} such that
{{< katex >}}$\operatorname{Map}(\Sigma) \subset (FU)^k${{< /katex >}}.
Without loss of generality,
we may assume that {{< katex >}}$U${{< /katex >}} is 

{{< katex >}}$U_S = \{[g] \in \operatorname{Map}(\Sigma) : g|_S = 1\}${{< /katex >}}

for some finite-type subsurface {{< katex >}}$S${{< /katex >}} satisfying the hypotheses and hence the conclusions
of Lemma 3.2 above (note that enlarging {{< katex >}}$S${{< /katex >}} *shrinks* {{< katex >}}$U_S${{< /katex >}}, which is good for our purposes).
That is, we have a subsurface {{< katex >}}$R${{< /katex >}} disjoint from {{< katex >}}$S${{< /katex >}}
and a homeomorphism {{< katex >}}$f\colon \Sigma \to \Sigma${{< /katex >}} taking {{< katex >}}$S${{< /katex >}} to {{< katex >}}$R${{< /katex >}}.
The finite set {{< katex >}}$F${{< /katex >}} will be the mapping classes of the identity, {{< katex >}}$f${{< /katex >}} and {{< katex >}}$f^{-1}${{< /katex >}}.
It suffices to take {{< katex >}}$k = 5${{< /katex >}}.

Take {{< katex >}}$[g] \in \operatorname{Map}(\Sigma)${{< /katex >}}.
If {{< katex >}}$g(S) = S${{< /katex >}} and {{< katex >}}$g|_S = 1${{< /katex >}}, we are done, since {{< katex >}}$g \in U${{< /katex >}},
so certainly in {{< katex >}}$(FU)^5${{< /katex >}}.
If {{< katex >}}$g(R) = R${{< /katex >}} and {{< katex >}}$g|_R = 1${{< /katex >}}, then since {{< katex >}}$f(S) = R${{< /katex >}},
we have {{< katex >}}$f^{-1}gf(S) = f^{-1}g(R) = f^{-1}(R) = S${{< /katex >}}
and {{< katex >}}$f^{-1}gf|_S = 1${{< /katex >}}. 
In this case we see that {{< katex >}}$g \in FUF \subset (FU)^2${{< /katex >}}.
This illustrates the strategy:
if we can, using finitely many elements of {{< katex >}}$F${{< /katex >}} and {{< katex >}}$U${{< /katex >}},
reduce {{< katex >}}$g${{< /katex >}} to the case where it is the identity on {{< katex >}}$R${{< /katex >}} or {{< katex >}}$S${{< /katex >}}, we win.
Now, in the notation of Lemma 3.2, the end set {{< katex >}}$E_0${{< /katex >}} of {{< katex >}}$C_0${{< /katex >}}
satisfies the condition that {{< katex >}}$E_0 \cap f(E_0)${{< /katex >}}
contains a homeomorphic copy {{< katex >}}$E'${{< /katex >}} of {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}}.
Since {{< katex >}}$f(E_0) \cup E_0 = \operatorname{Ends}(\Sigma)${{< /katex >}},
we have a decomposition

{{< katex >}}$\operatorname{Ends}(\Sigma) = (E_0 - f(E_0)) \sqcup (E_0 \cap f(E_0)) \sqcup (f(E_0) - E_0),${{< /katex >}}

so the intersection of one of these sets with the self-similar set 
{{< katex >}}$g(E') \cong \operatorname{Ends}(\Sigma)${{< /katex >}}
contains a clopen subset {{< katex >}}$E''${{< /katex >}} homeomorphic to {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}}.
At the cost of one application of {{< katex >}}$f^{-1}${{< /katex >}},
we may assume that {{< katex >}}$E''${{< /katex >}} is contained in {{< katex >}}$E_0${{< /katex >}},
the end set of the "big" complementary component {{< katex >}}$C_0${{< /katex >}} of {{< katex >}}$\Sigma - S${{< /katex >}}.

Now, notice that {{< katex >}}$C_0${{< /katex >}} and {{< katex >}}$R${{< /katex >}} taken by themselves
satisfy the hypotheses and hence the conclusions of Lemma 3.2.
This is key: arguing using the "big" collection of ends {{< katex >}}$E''${{< /katex >}},
we can find a subsurface {{< katex >}}$R'${{< /katex >}} homeomorphic to {{< katex >}}$R${{< /katex >}} in {{< katex >}}$C_0 \cap g(C_0)${{< /katex >}}
and a homeomorphism {{< katex >}}$s\colon C_0 \to C_0${{< /katex >}} satisfying {{< katex >}}$s(R) = R'${{< /katex >}}
and {{< katex >}}$R \subset s(C_0 \cap f(C_0))${{< /katex >}}.
By choosing {{< katex >}}$s${{< /katex >}} carefully, 
we may extend it to a homeomorphism {{< katex >}}$\tilde s\colon \Sigma \to \Sigma${{< /katex >}}
by declaring it to be the identity on {{< katex >}}$\Sigma - C_0${{< /katex >}}.
We have {{< katex >}}$\tilde s \in U${{< /katex >}}.

The advantage of having this {{< katex >}}$R'${{< /katex >}} is that we may "undo" {{< katex >}}$g${{< /katex >}} on {{< katex >}}$S${{< /katex >}}
while fixing {{< katex >}}$R'${{< /katex >}} via a homeomorphism {{< katex >}}$u\colon \Sigma \to \Sigma${{< /katex >}}
satisfying {{< katex >}}$ug(S) = S${{< /katex >}} and {{< katex >}}$ug|_S = 1${{< /katex >}}.
This is again a classification of surfaces argument:
the point is that the decomposition of {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}}
given by {{< katex >}}$S${{< /katex >}} is equivalent to that provided by {{< katex >}}$g(S)${{< /katex >}}
(the homeomorphism {{< katex >}}$g${{< /katex >}} sends one to the other)
and both {{< katex >}}$C_0${{< /katex >}} and {{< katex >}}$g(C_0)${{< /katex >}} contain {{< katex >}}$R'${{< /katex >}},
so after cutting away {{< katex >}}$R'${{< /katex >}}, the end set decompositions are still equivalent,
so there is a homeomorphism returning {{< katex >}}$g(S)${{< /katex >}} to {{< katex >}}$S${{< /katex >}} while fixing {{< katex >}}$R'${{< /katex >}},
and postcomposing with a homeomorphism supported on {{< katex >}}$S${{< /katex >}}, 
we may suppose this homeomorphism has the desired properties of {{< katex >}}$u${{< /katex >}}.

So let's put it together.
We have {{< katex >}}$ug \in U${{< /katex >}}, so we win if we can write {{< katex >}}$u${{< /katex >}} using elements of {{< katex >}}$F${{< /katex >}} and {{< katex >}}$U${{< /katex >}}.
But since {{< katex >}}$u${{< /katex >}} is the identity on {{< katex >}}$R'${{< /katex >}}, the mapping class of {{< katex >}}$(\tilde s f)^{-1}u(\tilde sf)${{< /katex >}}
is the identity on {{< katex >}}$(\tilde s f)^{-1}(R') = S${{< /katex >}}.
We have {{< katex >}}$(\tilde s f)^{-1}u(\tilde s f) \in U${{< /katex >}},
so {{< katex >}}$u \in UFUFU \subset (FU)^3${{< /katex >}}, which implies that {{< katex >}}$g \in (FU)^4${{< /katex >}}.
But remembering that we had to pay an application of {{< katex >}}$f^{-1}${{< /katex >}} a few paragraphs back,
we see that the *original* {{< katex >}}$g${{< /katex >}} is contained in {{< katex >}}$(FU)^5${{< /katex >}}. {{< katex >}}$\blacksquare${{< /katex >}}

[previous post]: {{< ref "nondisplaceable-subsurfaces.md" >}}
[Mann–Rafi]: https://arxiv.org/abs/1912.10914
