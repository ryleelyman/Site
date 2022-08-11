---
layout: post
math: true
---

This is the first post in a series on
Katie Mann and Kasra Rafi's paper
"Large-scale geometry of big mapping class groups."
The purpose of this post is to introduce
the classification of (possibly) infinite-type surfaces
by their genus and end spaces,
and to introduce Mann and Rafi's preorder on the end space.

By a *surface,* I mean a 2-dimensional manifold
(which I will usually assume to be orientable and without boundary)
which is Hausdorff and second countable.
*Finite-type* surfaces,
i.e. those with finitely generated fundamental group
are classically classified by their *genus* and number of *punctures.*
So for example we have the sphere, the plane,
the open annulus (or cylinder)
and spheres with a higher number of punctures,
all with genus zero,
the torus with genus one and some number of punctures,
and so on.

## Ends and classification

Each puncture is an *end* of the surface $$\Sigma$$.
Informally an end is a way to go "to infinity" in the surface.
Formally, there is a whole *space of ends* of $$\Sigma$$
which is the inverse limit

$$\operatorname{Ends}(\Sigma) = \varprojlim_{K \text{ compact}} \pi_0(\Sigma - K)$$

of the set of complementary components of $$\Sigma$$ after removing compact subsets $$K$$.
As usual with inverse limits,
$$\operatorname{Ends}(\Sigma)$$ is naturally a subspace of
$$\prod_K \pi_0(\Sigma - K)$$,
and I say *space* of ends because if we give each set of complementary components
the discrete topology and
the product the product topology,
the inverse limit is a closed subset.

Now, $$\Sigma$$ admits a countable exhaustion by compact sets
$$\varnothing = K_0 \subset K_1 \subset K_2 \subset \cdots$$,
and we obtain the same space of ends if we restrict the product and inverse limit
to be drawn from the $$K_i$$.
An *end* $$\xi$$, then, is a function that assigns to each $$K_i$$
a component $$\xi(K_i)$$ of $$\Sigma - K_i$$ such that if $$i < j$$,
we have $$\xi(K_j) \subset \xi(K_i)$$.
Since the product $$\prod_i \pi_0(\Sigma - K_i)$$ is a Cantor set,
being a countable product of finite discrete spaces,
the closed subset $$\operatorname{Ends}(\Sigma)$$ 
is compact, Hausdorff, metrizable and totally disconnected.

Now, of course, if $$\Sigma$$ is of finite type,
$$\operatorname{Ends}(\Sigma)$$ is a finite discrete set,
but one might wonder what possible closed subsets of the Cantor set can arise.
If the genus of $$\Sigma$$ is allowed to be infinite,
certain of the ends $$\xi$$ of $$\Sigma$$ must be *accumulated by genus*
(another common term I'm likely to use is *nonplanar ends*)
in the sense that any subsurface of $$\Sigma$$ containing some $$\xi(K_i)$$
has infinite genus.
This turns out to be a closed condition,
so we end up with a closed subspace $$\operatorname{Ends}^g(\Sigma)$$
of nonplanar ends.

It turns out this is enough to classify surfaces!

> **Theorem** (Kerékjártó, Richards).
Let $$E$$ be a closed subset of the Cantor set, $$E^g$$ a closed subset of $$E$$,
and $$g \in \{0,1,2,\ldots\} \cup \{\infty\}$$,
such that $$E^g = \varnothing$$ if $$g \ne \infty$$.
There exists an orientable, infinite-type surface $$\Sigma$$ without boundary
with $$\operatorname{genus}(\Sigma) = g$$,
$$\operatorname{Ends}(\Sigma) = E$$ and $$\operatorname{Ends}^g(\Sigma) = E^g$$.
Moreover, $$\Sigma$$ is determined by this data in the sense that
if $$\operatorname{genus}(\Sigma) = \operatorname{genus}(\Sigma')$$
and $$\hat f\colon \operatorname{Ends}(\Sigma) \to \operatorname{Ends}(\Sigma')$$
is a homeomorphism carrying $$\operatorname{Ends}^g(\Sigma)$$ homeomorphically to
$$\operatorname{Ends}^g(\Sigma')$$,
then $$\hat f$$ extends to a homeomorphism $$f \colon \Sigma \to \Sigma'$$.

## A preorder on $$\operatorname{Ends}(\Sigma)$$.

One useful tool that Mann and Rafi introduce
is the following preorder on the space of ends of $$\Sigma$$.
Given ends $$\xi$$ and $$\zeta$$ in $$\operatorname{Ends}(\Sigma)$$,
say that $$\xi \preceq \zeta$$ if for every neighborhood $$U$$ of $$\zeta$$,
there exists a neighborhood $$V$$ of $$\xi$$ and an embedding of $$V$$ into $$U$$.
I say *preorder* because distinct ends $$\xi$$ and $$\zeta$$ can certainly satisfy
$$\xi \preceq \zeta$$ and $$\zeta \preceq \xi$$,
in which case we say $$\zeta \sim \xi$$.
Write $$E(\xi)$$ for the $$\sim$$-equivalence class of $$\xi$$.
The equivalence classes are partially ordered;
write $$\prec$$ for the partial order.

Using Zorn's lemma and compactness, Mann and Rafi prove
that the poset of equivalence classes admits maximal elements,
and they write $$\mathcal{M}(\Sigma)$$ for the set of maximal equivalence classes.
We close with a precise statement.

> **Proposition 4.7** (Mann–Rafi)
For each $$\xi \in \operatorname{Ends}(\Sigma)$$,
there exists $$E(\zeta) \in \mathcal{M}(\Sigma)$$ such that $$\xi \preceq \zeta$$.
If $$E(\zeta) \in \mathcal{M}(\Sigma)$$,
the equivalence class $$E(\zeta)$$ is either finite or a Cantor set.

