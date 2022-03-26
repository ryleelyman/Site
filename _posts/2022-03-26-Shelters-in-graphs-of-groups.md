---
layout: post
math: true
---
Let's fix a group $$G$$ that acts cocompactly on a tree $$T$$.
[Forester][Forester] introduced the notion of a *deformation* of the tree $$T$$
and [Guirardel and Levitt][GuirardelLevitt] studied the *deformation space*
$$\mathscr{D}$$ consisting of trees obtainable from $$T$$ by a finite sequence of deformations.
Usually we assume $$G$$ to be finitely generated,
but it's not clear to me how often this assumption is necessary.
Maybe that'll be a topic for another blog post.
In this post I want to discuss the notion of a *shelter,*
which Guirardel and Levitt (and also [Clay][Clay]) 
use to construct a deformation retraction of $$\mathscr{D}$$ (or its simplicial spine)
onto a smaller, often finite-dimensional, space.

## The quotient graph of groups
Given a group $$G$$ acting on a graph $$\Gamma$$,
there is a notion of a *quotient graph of groups,* 
which I'd like to describe once and for all here.
Let me remind you that a *graph of groups* 
is a graph, which I'll call $$\mathcal{G}$$,
together with an assignment of groups $$\mathcal{G}_v$$ and $$\mathcal{G}_e$$
to each vertex $$v$$ and edge $$e$$ of $$\mathcal{G}$$,
along with injective homomorphisms $$\iota_e \colon \mathcal{G}_e \to \mathcal{G}_v$$
whenever $$v$$ is the terminal vertex of the oriented edge $$e$$.

Anyway, suppose we have $$G$$ acting on $$\Gamma$$.
I want this action to be essentially combinatorial,
in the sense that we can think of $$\Gamma$$ as having a set of vertices and a set of edges,
and $$G$$ permutes the elements of those sets preserving adjacency.
Making this precise is surprisingly exhausting 
("fix a homeomorphism between each closed edge..."), so I won't.
By $$G$$-equivariantly subdividing certain orbits of edges,
we may suppose that the action is *without inversions in edges,*
which means that if a group element preserves an edge $$e$$ of $$\Gamma$$,
then it fixes each vertex incident to $$e$$.
The advantage of this condition is that the quotient $$G\backslash\Gamma$$
then inherits the structure of a graph, call it $$\mathcal{G}$$.
To make $$\mathcal{G}$$ into a graph of groups, we need groups and homomorphisms.

So fix connected subgraphs $$S_0 \subset S_1 \subset \Gamma$$
with the property that the natural projection $$p\colon \Gamma \to \mathcal{G}$$
restricts to a bijection on the set of vertices of $$S_0$$
and a bijection on the set of edges of $$S_1$$.
In other words, $$S_1$$ is a *fundamental domain* for the action of $$G$$ on $$\Gamma$$,
and if we assume $$S_0$$ is a minimal subgraph of $$S_1$$ with the defining property,
it follows that $$S_0$$ projects to a *spanning tree* of $$\mathcal{G}$$.
For a vertex $$v$$ and an edge $$e$$ of $$\mathcal{G}$$, 
write $$\tilde v$$ and $$\tilde e$$ for its unique preimage in $$S_0$$ and $$S_1$$ respectively.
For each oriented edge $$e$$ of $$\mathcal{G}$$,
choose a group element $$g_e \in G$$
with the following property:
if $$x$$ is the terminal vertex of $$\tilde e$$ and $$p(x) = v$$,
we have that $$g_e.x = \tilde v$$.
Furthermore, if $$x = \tilde v$$, choose $$g_e = 1$$.
The groups $$\mathcal{G}_v$$ and $$\mathcal{G}_e$$
are the stabilizers in $$G$$ of $$\tilde v$$ and $$\tilde e$$ respectively,
and the injective homomorphism $$\iota_e \colon \mathcal{G}_e \to \mathcal{G}_v$$
is the restriction of the map $$h \mapsto g_e h g_e^{-1}$$ to $$\mathcal{G}_e$$.

## Properties of the tree in the quotient
Let's return to the situation of our group $$G$$ acting cocompactly on a tree $$T$$.
Then the quotient graph of groups $$\mathcal{G}$$ is finite and connected.
We assume the action is *minimal,*
in the sense that there is no $$G$$-invariant subtree.
In the quotient graph of groups $$\mathcal{G}$$,
this is equivalent to the condition that no valence-one vertex $$v$$
has the property that the incident edge-to-vertex group inclusion is surjective.
We also assume that $$T$$ has no *subdivision vertices,*
i.e. that a valence-two vertex of $$T$$ has the property
that the incident edges are in the same $$G$$-orbit.
In the quotient graph of groups $$\mathcal{G}$$,
this is equivalent to the condition that no valence-two vertex $$v$$
has the property that both incident edge-to-vertex group inclusions are surjective.

A general fact about automorphisms of simplicial trees
(in fact, isometries of real trees)
is that each automorphism (isometry) is either *elliptic,*
i.e. fixes a point of the tree
or *hyperbolic*
i.e. there is an embedded copy of $$\mathbb{R}$$ called the *axis* in the tree
that is preserved by the automorphism (isometry) and along which
the automorphism (isometry) acts by translation.

An edge $$\tilde e$$ of $$T$$ is *collapsible* if collapsing each edge in its orbit to a point
does not change the partition of elements of $$G$$ into hyperbolic and elliptic elements.
Equivalently, the $$G$$-orbit of $$\tilde e$$ must not contain the axis of a hyperbolic element.
In the quotient graph of groups, we must have that the endpoints of $$p(\tilde e) = e$$
are distinct and that at least one of the edge-to-vertex group inclusions is surjective.
If $$\tilde e$$ is collapsible, collapsing each edge in its orbit to a point
yields a new tree $$T'$$ in the same deformation space as $$T$$.
In [my paper][TrainTracksonGraphsofGroups], I describe this as a *collapse map*
of the quotient graphs of groups which is a *homotopy equivalence.*

A tree $$T$$ is *reduced* if is has no collapsible edges.
In the quotient graph of groups,
this says that if some edge-to-vertex group inclusion 
$$\iota_e\colon \mathcal{G}_e \to \mathcal{G}_v$$ is surjective,
then the edge $$e$$ forms a loop.
Every cocompact $$G$$-tree $$T$$ may be made reduced by a finite sequence of collapse maps.

## Shelters
An edge $$\tilde e$$ in a tree $$T$$ is *surviving*
if there is a reduced tree $$T'$$ and a product of collapse maps $$T \to T'$$
with the property that the edge $$\tilde e$$ is not collapsed.
The deformation retraction mentioned in the first paragraph
consists of those trees all of whose edges are surviving.
For the reader familiar with Culler--Vogtmann Outer Space,
it's not hard to see that a tree in Outer Space has the property that every edge is surviving
if and only if the quotient graph has no separating edges.
The concept of a *shelter* generalizes this "no separating edges" condition.

Let $$\mathcal{G}$$ be the quotient graph of groups.
Label each half-edge of $$\mathcal{G}$$ by $$=$$ or $$\neq$$
according to whether the corresponding edge-to-vertex group inclusion
is surjective or non-surjective, respectively.
An embedded segment or circle $$\gamma$$ in $$\mathcal{G}$$ is a *shelter*
if it satisfies one of the following properties:

1. $$\gamma$$ is a segment with $$\ne$$ at each of its endpoints
and $$=$$ otherwise.

2. $$\gamma$$ is a circle with two $$=$$ labels at all of its vertices 
with the possible exception of one.

3. $$\gamma$$ is a circle, and there is an orientation of $$\gamma$$ such that
all positively oriented edges have $$=$$ at their endpoints.

Clay has a nice picture as Figure 1 in [his paper][Clay].
Clay proves the following as Proposition 1.13 of [his paper][Clay].

**Theorem.** An edge $$\tilde e$$ of $$T$$ is surviving if and only if
$$p(\tilde e)$$ is contained in a shelter.

[Forester]: https://arxiv.org/abs/math/0107008
[GuirardelLevitt]: https://arxiv.org/abs/math/0605545
[Clay]: https://mattclay.hosted.uark.edu/Papers/def.pdf
[TrainTracksonGraphsofGroups]: https://arxiv.org/abs/2102.02848
