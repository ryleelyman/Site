---
title: "Shelters in Graphs of Groups"
date: 2022-03-26T15:09:16-04:00
math: true
---
Let's fix a group {{< katex >}}$G${{< /katex >}} that acts cocompactly on a tree {{< katex >}}$T${{< /katex >}}.
[Forester][Forester] introduced the notion of a *deformation* of the tree {{< katex >}}$T${{< /katex >}}
and [Guirardel and Levitt][GuirardelLevitt] studied the *deformation space*
{{< katex >}}$\mathscr{D}${{< /katex >}} consisting of trees obtainable from {{< katex >}}$T${{< /katex >}} by a finite sequence of deformations.
Usually we assume {{< katex >}}$G${{< /katex >}} to be finitely generated,
but it's not clear to me how often this assumption is necessary.
Maybe that'll be a topic for another blog post.
In this post I want to discuss the notion of a *shelter,*
which Guirardel and Levitt (and also [Clay][Clay]) 
use to construct a deformation retraction of {{< katex >}}$\mathscr{D}${{< /katex >}} (or its simplicial spine)
onto a smaller, often finite-dimensional, space.

## The quotient graph of groups
Given a group {{< katex >}}$G${{< /katex >}} acting on a graph {{< katex >}}$\Gamma${{< /katex >}},
there is a notion of a *quotient graph of groups,* 
which I'd like to describe once and for all here.
Let me remind you that a *graph of groups* 
is a graph, which I'll call {{< katex >}}$\mathcal{G}${{< /katex >}},
together with an assignment of groups {{< katex >}}$\mathcal{G}_v${{< /katex >}} and {{< katex >}}$\mathcal{G}_e${{< /katex >}}
to each vertex {{< katex >}}$v${{< /katex >}} and edge {{< katex >}}$e${{< /katex >}} of {{< katex >}}$\mathcal{G}${{< /katex >}},
along with injective homomorphisms {{< katex >}}$\iota_e \colon \mathcal{G}_e \to \mathcal{G}_v${{< /katex >}}
whenever {{< katex >}}$v${{< /katex >}} is the terminal vertex of the oriented edge {{< katex >}}$e${{< /katex >}}.

Anyway, suppose we have {{< katex >}}$G${{< /katex >}} acting on {{< katex >}}$\Gamma${{< /katex >}}.
I want this action to be essentially combinatorial,
in the sense that we can think of {{< katex >}}$\Gamma${{< /katex >}} as having a set of vertices and a set of edges,
and {{< katex >}}$G${{< /katex >}} permutes the elements of those sets preserving adjacency.
Making this precise is surprisingly exhausting 
("fix a homeomorphism between each closed edge..."), so I won't.
By {{< katex >}}$G${{< /katex >}}-equivariantly subdividing certain orbits of edges,
we may suppose that the action is *without inversions in edges,*
which means that if a group element preserves an edge {{< katex >}}$e${{< /katex >}} of {{< katex >}}$\Gamma${{< /katex >}},
then it fixes each vertex incident to {{< katex >}}$e${{< /katex >}}.
The advantage of this condition is that the quotient {{< katex >}}$G\backslash\Gamma${{< /katex >}}
then inherits the structure of a graph, call it {{< katex >}}$\mathcal{G}${{< /katex >}}.
To make {{< katex >}}$\mathcal{G}${{< /katex >}} into a graph of groups, we need groups and homomorphisms.

So fix connected subgraphs {{< katex >}}$S_0 \subset S_1 \subset \Gamma${{< /katex >}}
with the property that the natural projection {{< katex >}}$p\colon \Gamma \to \mathcal{G}${{< /katex >}}
restricts to a bijection on the set of vertices of {{< katex >}}$S_0${{< /katex >}}
and a bijection on the set of edges of {{< katex >}}$S_1${{< /katex >}}.
In other words, {{< katex >}}$S_1${{< /katex >}} is a *fundamental domain* for the action of {{< katex >}}$G${{< /katex >}} on {{< katex >}}$\Gamma${{< /katex >}},
and if we assume {{< katex >}}$S_0${{< /katex >}} is a minimal subgraph of {{< katex >}}$S_1${{< /katex >}} with the defining property,
it follows that {{< katex >}}$S_0${{< /katex >}} projects to a *spanning tree* of {{< katex >}}$\mathcal{G}${{< /katex >}}.
For a vertex {{< katex >}}$v${{< /katex >}} and an edge {{< katex >}}$e${{< /katex >}} of {{< katex >}}$\mathcal{G}${{< /katex >}}, 
write {{< katex >}}$\tilde v${{< /katex >}} and {{< katex >}}$\tilde e${{< /katex >}} for its unique preimage in {{< katex >}}$S_0${{< /katex >}} and {{< katex >}}$S_1${{< /katex >}} respectively.
For each oriented edge {{< katex >}}$e${{< /katex >}} of {{< katex >}}$\mathcal{G}${{< /katex >}},
choose a group element {{< katex >}}$g_e \in G${{< /katex >}}
with the following property:
if {{< katex >}}$x${{< /katex >}} is the terminal vertex of {{< katex >}}$\tilde e${{< /katex >}} and {{< katex >}}$p(x) = v${{< /katex >}},
we have that {{< katex >}}$g_e.x = \tilde v${{< /katex >}}.
Furthermore, if {{< katex >}}$x = \tilde v${{< /katex >}}, choose {{< katex >}}$g_e = 1${{< /katex >}}.
The groups {{< katex >}}$\mathcal{G}_v${{< /katex >}} and {{< katex >}}$\mathcal{G}_e${{< /katex >}}
are the stabilizers in {{< katex >}}$G${{< /katex >}} of {{< katex >}}$\tilde v${{< /katex >}} and {{< katex >}}$\tilde e${{< /katex >}} respectively,
and the injective homomorphism {{< katex >}}$\iota_e \colon \mathcal{G}_e \to \mathcal{G}_v${{< /katex >}}
is the restriction of the map {{< katex >}}$h \mapsto g_e h g_e^{-1}${{< /katex >}} to {{< katex >}}$\mathcal{G}_e${{< /katex >}}.

## Properties of the tree in the quotient
Let's return to the situation of our group {{< katex >}}$G${{< /katex >}} acting cocompactly on a tree {{< katex >}}$T${{< /katex >}}.
Then the quotient graph of groups {{< katex >}}$\mathcal{G}${{< /katex >}} is finite and connected.
We assume the action is *minimal,*
in the sense that there is no {{< katex >}}$G${{< /katex >}}-invariant subtree.
In the quotient graph of groups {{< katex >}}$\mathcal{G}${{< /katex >}},
this is equivalent to the condition that no valence-one vertex {{< katex >}}$v${{< /katex >}}
has the property that the incident edge-to-vertex group inclusion is surjective.
We also assume that {{< katex >}}$T${{< /katex >}} has no *subdivision vertices,*
i.e. that a valence-two vertex of {{< katex >}}$T${{< /katex >}} has the property
that the incident edges are in the same {{< katex >}}$G${{< /katex >}}-orbit.
In the quotient graph of groups {{< katex >}}$\mathcal{G}${{< /katex >}},
this is equivalent to the condition that no valence-two vertex {{< katex >}}$v${{< /katex >}}
has the property that both incident edge-to-vertex group inclusions are surjective.

A general fact about automorphisms of simplicial trees
(in fact, isometries of real trees)
is that each automorphism (isometry) is either *elliptic,*
i.e. fixes a point of the tree
or *hyperbolic*
i.e. there is an embedded copy of {{< katex >}}$\mathbb{R}${{< /katex >}} called the *axis* in the tree
that is preserved by the automorphism (isometry) and along which
the automorphism (isometry) acts by translation.

An edge {{< katex >}}$\tilde e${{< /katex >}} of {{< katex >}}$T${{< /katex >}} is *collapsible* if collapsing each edge in its orbit to a point
does not change the partition of elements of {{< katex >}}$G${{< /katex >}} into hyperbolic and elliptic elements.
Equivalently, the {{< katex >}}$G${{< /katex >}}-orbit of {{< katex >}}$\tilde e${{< /katex >}} must not contain the axis of a hyperbolic element.
In the quotient graph of groups, we must have that the endpoints of {{< katex >}}$p(\tilde e) = e${{< /katex >}}
are distinct and that at least one of the edge-to-vertex group inclusions is surjective.
If {{< katex >}}$\tilde e${{< /katex >}} is collapsible, collapsing each edge in its orbit to a point
yields a new tree {{< katex >}}$T'${{< /katex >}} in the same deformation space as {{< katex >}}$T${{< /katex >}}.
In [my paper][TrainTracksonGraphsofGroups], I describe this as a *collapse map*
of the quotient graphs of groups which is a *homotopy equivalence.*

A tree {{< katex >}}$T${{< /katex >}} is *reduced* if is has no collapsible edges.
In the quotient graph of groups,
this says that if some edge-to-vertex group inclusion 
{{< katex >}}$\iota_e\colon \mathcal{G}_e \to \mathcal{G}_v${{< /katex >}} is surjective,
then the edge {{< katex >}}$e${{< /katex >}} forms a loop.
Every cocompact {{< katex >}}$G${{< /katex >}}-tree {{< katex >}}$T${{< /katex >}} may be made reduced by a finite sequence of collapse maps.

## Shelters
An edge {{< katex >}}$\tilde e${{< /katex >}} in a tree {{< katex >}}$T${{< /katex >}} is *surviving*
if there is a reduced tree {{< katex >}}$T'${{< /katex >}} and a product of collapse maps {{< katex >}}$T \to T'${{< /katex >}}
with the property that the edge {{< katex >}}$\tilde e${{< /katex >}} is not collapsed.
The deformation retraction mentioned in the first paragraph
consists of those trees all of whose edges are surviving.
For the reader familiar with Culler--Vogtmann Outer Space,
it's not hard to see that a tree in Outer Space has the property that every edge is surviving
if and only if the quotient graph has no separating edges.
The concept of a *shelter* generalizes this "no separating edges" condition.

Let {{< katex >}}$\mathcal{G}${{< /katex >}} be the quotient graph of groups.
Label each half-edge of {{< katex >}}$\mathcal{G}${{< /katex >}} by {{< katex >}}$=${{< /katex >}} or {{< katex >}}$\neq${{< /katex >}}
according to whether the corresponding edge-to-vertex group inclusion
is surjective or non-surjective, respectively.
An embedded segment or circle {{< katex >}}$\gamma${{< /katex >}} in {{< katex >}}$\mathcal{G}${{< /katex >}} is a *shelter*
if it satisfies one of the following properties:

1. {{< katex >}}$\gamma${{< /katex >}} is a segment with {{< katex >}}$\ne${{< /katex >}} at each of its endpoints
and {{< katex >}}$=${{< /katex >}} otherwise.

2. {{< katex >}}$\gamma${{< /katex >}} is a circle with two {{< katex >}}$=${{< /katex >}} labels at all of its vertices 
with the possible exception of one.

3. {{< katex >}}$\gamma${{< /katex >}} is a circle, and there is an orientation of {{< katex >}}$\gamma${{< /katex >}} such that
all positively oriented edges have {{< katex >}}$=${{< /katex >}} at their endpoints.

Clay has a nice picture as Figure 1 in [his paper][Clay].
Clay proves the following as Proposition 1.13 of [his paper][Clay].

**Theorem.** An edge {{< katex >}}$\tilde e${{< /katex >}} of {{< katex >}}$T${{< /katex >}} is surviving if and only if
{{< katex >}}$p(\tilde e)${{< /katex >}} is contained in a shelter.

[Forester]: https://arxiv.org/abs/math/0107008
[GuirardelLevitt]: https://arxiv.org/abs/math/0605545
[Clay]: https://mattclay.hosted.uark.edu/Papers/def.pdf
[TrainTracksonGraphsofGroups]: https://arxiv.org/abs/2102.02848
