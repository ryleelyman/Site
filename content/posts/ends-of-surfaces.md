---
title: "Ends of Surfaces"
date: 2022-08-11T16:09:37-04:00
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

Each puncture is an *end* of the surface {{< katex >}}$\Sigma${{< /katex >}}.
Informally an end is a way to go "to infinity" in the surface.
Formally, there is a whole *space of ends* of {{< katex >}}$\Sigma${{< /katex >}}
which is the inverse limit

{{< katex >}}$\operatorname{Ends}(\Sigma) = \varprojlim_{K \text{ compact}} \pi_0(\Sigma - K)${{< /katex >}}

of the set of complementary components of {{< katex >}}$\Sigma${{< /katex >}} after removing compact subsets {{< katex >}}$K${{< /katex >}}.
As usual with inverse limits,
{{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}} is naturally a subspace of
{{< katex >}}$\prod_K \pi_0(\Sigma - K)${{< /katex >}},
and I say *space* of ends because if we give each set of complementary components
the discrete topology and
the product the product topology,
the inverse limit is a closed subset.

Now, {{< katex >}}$\Sigma${{< /katex >}} admits a countable exhaustion by compact sets
{{< katex >}}$\varnothing = K_0 \subset K_1 \subset K_2 \subset \cdots${{< /katex >}},
and we obtain the same space of ends if we restrict the product and inverse limit
to be drawn from the {{< katex >}}$K_i${{< /katex >}}.
An *end* {{< katex >}}$\xi${{< /katex >}}, then, is a function that assigns to each {{< katex >}}$K_i${{< /katex >}}
a component {{< katex >}}$\xi(K_i)${{< /katex >}} of {{< katex >}}$\Sigma - K_i${{< /katex >}} such that if {{< katex >}}$i < j${{< /katex >}},
we have {{< katex >}}$\xi(K_j) \subset \xi(K_i)${{< /katex >}}.
Since the product {{< katex >}}$\prod_i \pi_0(\Sigma - K_i)${{< /katex >}} is a Cantor set,
being a countable product of finite discrete spaces,
the closed subset {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}} 
is compact, Hausdorff, metrizable and totally disconnected.

Now, of course, if {{< katex >}}$\Sigma${{< /katex >}} is of finite type,
{{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}} is a finite discrete set,
but one might wonder what possible closed subsets of the Cantor set can arise.
If the genus of {{< katex >}}$\Sigma${{< /katex >}} is allowed to be infinite,
certain of the ends {{< katex >}}$\xi${{< /katex >}} of {{< katex >}}$\Sigma${{< /katex >}} must be *accumulated by genus*
(another common term I'm likely to use is *nonplanar ends*)
in the sense that any subsurface of {{< katex >}}$\Sigma${{< /katex >}} containing some {{< katex >}}$\xi(K_i)${{< /katex >}}
has infinite genus.
This turns out to be a closed condition,
so we end up with a closed subspace {{< katex >}}$\operatorname{Ends}^g(\Sigma)${{< /katex >}}
of nonplanar ends.

It turns out this is enough to classify surfaces!

> **Theorem** (Kerékjártó, Richards).
Let {{< katex >}}$E${{< /katex >}} be a closed subset of the Cantor set, {{< katex >}}$E^g${{< /katex >}} a closed subset of {{< katex >}}$E${{< /katex >}},
and {{< katex >}}$g \in \{0,1,2,\ldots\} \cup \{\infty\}${{< /katex >}},
such that {{< katex >}}$E^g = \varnothing${{< /katex >}} if {{< katex >}}$g \ne \infty${{< /katex >}}.
There exists an orientable, infinite-type surface {{< katex >}}$\Sigma${{< /katex >}} without boundary
with {{< katex >}}$\operatorname{genus}(\Sigma) = g${{< /katex >}},
{{< katex >}}$\operatorname{Ends}(\Sigma) = E${{< /katex >}} and {{< katex >}}$\operatorname{Ends}^g(\Sigma) = E^g${{< /katex >}}.
Moreover, {{< katex >}}$\Sigma${{< /katex >}} is determined by this data in the sense that
if {{< katex >}}$\operatorname{genus}(\Sigma) = \operatorname{genus}(\Sigma')${{< /katex >}}
and {{< katex >}}$\hat f\colon \operatorname{Ends}(\Sigma) \to \operatorname{Ends}(\Sigma')${{< /katex >}}
is a homeomorphism carrying {{< katex >}}$\operatorname{Ends}^g(\Sigma)${{< /katex >}} homeomorphically to
{{< katex >}}$\operatorname{Ends}^g(\Sigma')${{< /katex >}},
then {{< katex >}}$\hat f${{< /katex >}} extends to a homeomorphism {{< katex >}}$f \colon \Sigma \to \Sigma'${{< /katex >}}.

## A preorder on {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}}.

One useful tool that Mann and Rafi introduce
is the following preorder on the space of ends of {{< katex >}}$\Sigma${{< /katex >}}.
Given ends {{< katex >}}$\xi${{< /katex >}} and {{< katex >}}$\zeta${{< /katex >}} in {{< katex >}}$\operatorname{Ends}(\Sigma)${{< /katex >}},
say that {{< katex >}}$\xi \preceq \zeta${{< /katex >}} if for every neighborhood {{< katex >}}$U${{< /katex >}} of {{< katex >}}$\zeta${{< /katex >}},
there exists a neighborhood {{< katex >}}$V${{< /katex >}} of {{< katex >}}$\xi${{< /katex >}} and an embedding of {{< katex >}}$V${{< /katex >}} into {{< katex >}}$U${{< /katex >}}.
I say *preorder* because distinct ends {{< katex >}}$\xi${{< /katex >}} and {{< katex >}}$\zeta${{< /katex >}} can certainly satisfy
{{< katex >}}$\xi \preceq \zeta${{< /katex >}} and {{< katex >}}$\zeta \preceq \xi${{< /katex >}},
in which case we say {{< katex >}}$\zeta \sim \xi${{< /katex >}}.
Write {{< katex >}}$E(\xi)${{< /katex >}} for the {{< katex >}}$\sim${{< /katex >}}-equivalence class of {{< katex >}}$\xi${{< /katex >}}.
The equivalence classes are partially ordered;
write {{< katex >}}$\prec${{< /katex >}} for the partial order.

Using Zorn's lemma and compactness, Mann and Rafi prove
that the poset of equivalence classes admits maximal elements,
and they write {{< katex >}}$\mathcal{M}(\Sigma)${{< /katex >}} for the set of maximal equivalence classes.

![An infinite-type surface with three maximal ends, two accumulated by genus and two accumulated by punctures](/img/infinitetypesurface.jpeg)

In the above figure, we have an infinite-type surface with an infinite number of
isolated planar ends (drawn as "hyperbolic cusps" across the top)
which accumulate to two of the three maximal ends,
which are drawn larger in the figure than the others.
One end (on the right) is accumulated by both genus and isolated planar ends,
another (on the left) only by isolated planar ends, and a third (on the bottom) only by genus.

We close with a precise statement of Mann–Rafi's result.

> **Proposition 4.7** (Mann–Rafi)
For each {{< katex >}}$\xi \in \operatorname{Ends}(\Sigma)${{< /katex >}},
there exists {{< katex >}}$E(\zeta) \in \mathcal{M}(\Sigma)${{< /katex >}} such that {{< katex >}}$\xi \preceq \zeta${{< /katex >}}.
If {{< katex >}}$E(\zeta) \in \mathcal{M}(\Sigma)${{< /katex >}},
the equivalence class {{< katex >}}$E(\zeta)${{< /katex >}} is either finite or a Cantor set.


