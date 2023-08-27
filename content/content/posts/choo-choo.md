---
title: "Choo Choo"
date: 2019-09-06T12:32:57-04:00
math: true
---
Today I posted my first paper, 
[Train Tracks, Orbigraphs and CAT(0) Free-by-cyclic Groups][paper]
to the ArXiv! Here is a description of the paper and the idea behind the main application.

### Orbigraphs

One of my main goals currently is to better understand outer automorphisms of
free products of finite groups. I became interested because I like [Coxeter groups][Coxeter],
and I was surprised to hear that we knew so little about their automorphisms.
The natural place to start is the "free" Coxeter group {{< katex >}}$W_n${{< /katex >}}, which is a free product of 
{{< katex >}}$n${{< /katex >}} copies of {{< katex >}}$\mathbb Z/2\mathbb Z${{< /katex >}}. I'm tempted to say the 
*{{< katex >}}$n${{< /katex >}}th copower of {{< katex >}}$\mathbb Z/2\mathbb Z${{< /katex >}},* but I guess it's a little too scary-sounding.

Along the way I've become quite enamored with [orbifolds][orbifolds]. The idea behind
orbifolds is that just as it is useful to study the fundamental group of a manifold both
as a group of homotopy classes of loops and as deck transformations of the universal cover,
so to should there be some object "downstairs" to look at in the case of a group acting
properly discontinuously but not freely.

An orbigraph, then, is an orbifold quotient of a graph. In other words, the underlying
topological space of an orbigrph is a (typically finite) graph. At a (typically finite)
collection of points called *cone points,* there is some nontrivial stabilizer information.
Note that there is the related idea of a [graph of groups][graph of groups], which is more
general. Since the singular locus of an orbifold is required to be nowhere dense, the term
"orbigraph" succinctly captures the restrictions I require. I also want to think of
orbigraphs as having interesting and nontrivial algebraic topology—in essentially the
same way as in Bass–Serre theory, but I take a slightly less combinatorial bent.

In the paper the underlying
space of all orbigraphs in question are finite trees, but I am realizing there is maybe some
(small) usefulness in orbigraphs whose underlying graph is not a tree.

### Train Tracks

The main tool for studying automorphisms of free groups is what are called
*relative train track maps.* Relative train track maps provide a topological "normal form"
for elements of {{< katex >}}$\operatorname{Out}(F_n)${{< /katex >}}. They were introduced by Bestvina–Handel in 
1992. My adaptation to the case of orbigraphs
builds on later developments by Bestvina–Feighn–Handel in 2000 and
Feighn–Handel in 2011. The name "relative train track map" is inspired by the theory
of surface homeomorphisms: there a *train track* is a graph embedded into the surface
in a prescribed wy.  The combinatorial properties of certain train tracks associated
to the mapping class of a surface homeomorphism yield a surprisingly rich  amount of
information about the dynamics of the homeomorphism.

The original idea of Bestvina--Handel's paper was to attempt to adapt the theory
to study outer automorphisms of free groups. Here, since any homeomorphism of a graph
has a finite power homotopic to the identity, we're forced to consider homotopy equivalences
of graphs. More explicitly: if {{< katex >}}$\varphi \in \operatorname{Out}(F_n)${{< /katex >}} is an outer
automorphism of a free group {{< katex >}}$F_n${{< /katex >}} of rank {{< katex >}}$n${{< /katex >}}, {{< katex >}}$G${{< /katex >}} is a graph, and {{< katex >}}$f\colon G \to G${{< /katex >}}
is a homotopy equivalence such that the (outer) action of {{< katex >}}$f${{< /katex >}} on {{< katex >}}$\pi_1(G)${{< /katex >}} is equal
to {{< katex >}}$\varphi${{< /katex >}}, then if {{< katex >}}$\varphi${{< /katex >}} has infinite order, {{< katex >}}$f${{< /katex >}} cannot be a homeomorphism.
We may as well assume {{< katex >}}$f${{< /katex >}} sends vertices to vertices.
Stallings tells us that in this situation, there is a vertex {{< katex >}}$v${{< /katex >}} of {{< katex >}}$G${{< /katex >}} and a pair of
edges {{< katex >}}$e${{< /katex >}} and {{< katex >}}$e'${{< /katex >}} incident to {{< katex >}}$v${{< /katex >}} such that {{< katex >}}$f(e)${{< /katex >}} and {{< katex >}}$f(e')${{< /katex >}} share a common segment.
We say {{< katex >}}$f${{< /katex >}} *folds* these edges, or that they form an *illegal turn*.

A *train track map* has the next best property: We say that {{< katex >}}$f\colon G \to G${{< /katex >}} is a
*train track map* if for each edge {{< katex >}}$e${{< /katex >}} of {{< katex >}}$G${{< /katex >}} and each positive integer {{< katex >}}$k${{< /katex >}},
the {{< katex >}}$k${{< /katex >}}th iterate, {{< katex >}}$f^k(e)${{< /katex >}} is an immersed path, i.e. it is never sent over an
illegal turn.

If you'd like to try playing with the definition here's something to try: let
{{< katex >}}$G${{< /katex >}} be the "rose with four petals." That is, {{< katex >}}$G${{< /katex >}} has one vertex and four edges,
each of which forms a loop. Label the edges {{< katex >}}$A${{< /katex >}} through {{< katex >}}$D${{< /katex >}} and choose an orientation
for each. Let's define {{< katex >}}$f${{< /katex >}} as {{< katex >}}$A \mapsto B${{< /katex >}}, {{< katex >}}$B \mapsto C${{< /katex >}}, {{< katex >}}$C \mapsto D${{< /katex >}}, and
{{< katex >}}$D \mapsto AB${{< /katex >}}, i.e. the path that first follows the edge {{< katex >}}$A${{< /katex >}} and then {{< katex >}}$B${{< /katex >}}.
There are a few things to check: 1) Find a homotopy inverse for {{< katex >}}$f${{< /katex >}}. 2) Which
turns (pairs of oriented edges originating at a common vertex) are illegal? 3) Is
{{< katex >}}$f${{< /katex >}} a train track map?

The word *relative* above is sort of forced on us by the structure of more complicated 
homotopy equivalences: as it turns out,
it may not be the case that we can always avoid illegal turns.
This is especially true in the "bad" case of polynomial growth, about which more below.

### CAT(0) Free-by-Cyclic Groups

Gersten in 1994 showed that {{< katex >}}$\operatorname{Out}(F_n)${{< /katex >}} cannot act
properly and cocompactly on a CAT(0) metric space when {{< katex >}}$n \ge 4${{< /katex >}}.
This is something of a bummer, but also to be expected: Acting by geometrically
on a CAT(0) metric space is a nice situation to be in, and one might think that
{{< katex >}}$\operatorname{Out}(F_n)${{< /katex >}} should be in some sense too complicated to do so.

I set out aiming to prove a version of Gersten's theorem for more general free products,
but instead I found essentially a *strong negation* of the situation he described.
Let me describe it in more detail:

Write {{< katex >}}$F_n = \langle x_1,\dotsc,x_n\rangle${{< /katex >}}, let {{< katex >}}$\Phi${{< /katex >}} be an automorphism and suppose
that {{< katex >}}$\Phi(x_i) = u_ix_iv_i${{< /katex >}}, where {{< katex >}}$u_i,v_i \in \langle x_1,\dotsc,x_{i-1}\rangle${{< /katex >}}.
Let's call such  automorphisms *upper triangular,* by analogy with groups of matrices.
In the free-by-cyclic group {{< katex >}}$F_n\rtimes_\Phi\mathbb{Z} = \langle x_1,\dotsc,x_n,t\rangle${{< /katex >}},
this gives us the relation {{< katex >}}$tx_it^{-1} = u_ix_iv_i${{< /katex >}}, which we can rewrite as
{{< katex >}}$x_i^{-1}u_i^{-1}tx_i = v_it${{< /katex >}}, which, if you squint, starts to look like a relation in
an HNN extension with stable letter {{< katex >}}$x_i${{< /katex >}}. In fact, by our assumption on {{< katex >}}$u_i${{< /katex >}} and {{< katex >}}$v_i${{< /katex >}},
we actually do get a description of {{< katex >}}$F_n\rtimes\mathbb{Z}${{< /katex >}} as an iterated HNN extension.

This situation can be good and bad. Gersten gave an example of such a description of a free-by-cyclic
group which is a "poison subgroup" for nonpositive curvature. There, {{< katex >}}$u_i${{< /katex >}} and {{< katex >}}$v_i${{< /katex >}}
are such that {{< katex >}}$u_i^{-1}t${{< /katex >}} and {{< katex >}}$v_it${{< /katex >}} have no business being conjugate in a nice action on a CAT(0) space.
On the other hand, in the situation where they *should* be conjugate,
Bridson--Haefliger give a construction that allows you to bootstrap a
geometric action on a CAT(0) space up the HNN extension.

What I realized was that in the class of automorphisms I was studying,
if it were the case that the automorphism was already upper-triangular
with respect to the basis {{< katex >}}$x_1,\dotsc,x_n${{< /katex >}} we were handed, then
{{< katex >}}$u_i^{-1}t${{< /katex >}} and {{< katex >}}$v_it${{< /katex >}} were *already* conjugate, so Bridson--Haefliger says we win.
So, my goal in constructing relative train track maps was to find a basis
that has this nice property for a (power of) an arbitrary polynomially-growing
outer automorphism. In the paper, the application is in Section 7, while the
heavy lifting is to find a way to adapt the relative train track technology appropriately.

Since relative train track maps with nice properties have become a foundational
tool in the study of {{< katex >}}$\operatorname{Out}(F_n)${{< /katex >}}, my hope is that this construction
will help in the study of outer automorphism groups of free products.

[paper]: https://arxiv.org/abs/1909.03097 
[graph of groups]: https://en.wikipedia.org/wiki/Graph_of_groups
[orbifolds]:  https://en.wikipedia.org/wiki/Orbifold
[Coxeter]: https://en.wikipedia.org/wiki/Coxeter_group


