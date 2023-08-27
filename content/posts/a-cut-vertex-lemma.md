---
title: "A Cut Vertex Lemma"
date: 2022-05-10T15:19:26-04:00
math: true
---

Building on ideas from the previous post regarding the star graph,
I wrote a short paper generalizing a classical lemma of Whitehead.
The purpose of this post is to describe Whitehead's lemma and my generalization.

In the [previous post][The Star Graph], we met the star graph
associated to a collection of conjugacy classes of elements
of a virtually free group.
It should be reasonably clear that one can extend
the notion of a star graph to conjugacy classes of elements
of a group that acts cocompactly on a tree.
What is perhaps less obvious is that one can also extend this notion
to convex-cocompact subgroups of groups acting on trees,
where a subgroup is *convex-cocompact* if it acts cocompactly on its minimal subtree.
This generalization is due to [Bestvina, Feighn and Handel][BFH] in the case of free groups.

The idea is the following.
A classical observation of Stallings says that 
any finitely generated subgroup {{< katex >}}$H${{< /katex >}} of a free group {{< katex >}}$G${{< /katex >}}
may be represented by an immersion of a finite graph {{< katex >}}$\Gamma${{< /katex >}} into a rose {{< katex >}}$R${{< /katex >}},
that is a graph with one vertex {{< katex >}}$w${{< /katex >}} and {{< katex >}}$n${{< /katex >}} edges, where {{< katex >}}$n${{< /katex >}} is the rank of {{< katex >}}$G${{< /katex >}}.
The set of directions {{< katex >}}$D_w${{< /katex >}} is the set of oriented edges of {{< katex >}}$R${{< /katex >}}.
Cut each edge of {{< katex >}}$\Gamma${{< /katex >}} at its midpoint,
observe that the half-edge left over crosses a direction of {{< katex >}}$R${{< /katex >}}
and attach, in the star graph of {{< katex >}}$\Gamma${{< /katex >}},
the half-edge to the vertex corresponding to the given direction in {{< katex >}}$D_w${{< /katex >}}.
Thus we get a bipartite graph with one vertex for each vertex of {{< katex >}}$\Gamma${{< /katex >}}
and one vertex for each direction in {{< katex >}}$D_w${{< /katex >}}.
A pair of directions are connected by a path of length two in this star graph
if and only if the corresponding [turn][The Star Graph] 
is in the image of the map on turns associated to the immersion {{< katex >}}$\Gamma \to R${{< /katex >}}.

This idea generalizes readily to {{< katex >}}$G${{< /katex >}} the fundamental group of a graph of groups {{< katex >}}$\mathbb{G}${{< /katex >}}.
A subgroup of {{< katex >}}$G${{< /katex >}} is convex-cocompact if and only if it may be represented as an immersion
of a finite connected graph of groups {{< katex >}}$f\colon \mathcal{G} \to \mathbb{G}${{< /katex >}}.
The set of directions we have met before.
Rather than snipping edges at midpoints in {{< katex >}}$\mathcal{G}${{< /katex >}},
we essentially do this in the Bass–Serre tree.
If {{< katex >}}$v${{< /katex >}} is a vertex of {{< katex >}}$\mathcal{G}${{< /katex >}} mapping to a vertex {{< katex >}}$w${{< /katex >}} in {{< katex >}}$\mathbb{G}${{< /katex >}},
we attach {{< katex >}}$|\mathbb{G}_w : f_v(\mathcal{G}_v)|${{< /katex >}} copies of this *piece*
of the Bass–Serre tree,
where the {{< katex >}}$gf_v(\mathcal{G}_v)${{< /katex >}} copy attaches an edge corresponding to a direction {{< katex >}}$d${{< /katex >}} in {{< katex >}}$D_v${{< /katex >}}
to the vertex corresponding to the direction {{< katex >}}$g.D_vf(d)${{< /katex >}} in {{< katex >}}$D_w${{< /katex >}}.

Suppose there exists {{< katex >}}$\mathcal{G}'${{< /katex >}} a graph of groups with fundamental group {{< katex >}}$G${{< /katex >}} and one edge
with the property that {{< katex >}}$\mathcal{G}'${{< /katex >}} may be obtained from a graph of groups
[homotopy equivalent][Free Splittings to Graphs of Groups] to {{< katex >}}$\mathbb{G}${{< /katex >}} by collapsing edges.
Anyway, say that a conjugacy class of an element or convex-cocompact subgroup of {{< katex >}}$G${{< /katex >}} is *simple*
if there is such a graph of groups {{< katex >}}$\mathcal{G}'${{< /katex >}} with the property that our element or subgroup
is conjugate into a vertex group in {{< katex >}}$\mathcal{G}'${{< /katex >}}.
For free groups thought of as fundamental groups of ordinary graphs,
it's not hard to see that an element or finitely generated (hence convex-cocompact) subgroup
is simple if and only if it is contained in a proper free factor of the free group.

The main result of my paper is that if we have a *jointly* simple collection {{< katex >}}$C${{< /katex >}} of conjugacy classes
of elements or convex-cocompact subgroups of {{< katex >}}$G${{< /katex >}}
(i.e. the same {{< katex >}}$\mathcal{G}'${{< /katex >}} works for all members of {{< katex >}}$C${{< /katex >}} at once)
then the star graph of {{< katex >}}$C${{< /katex >}} is either disconnected or has a cut vertex.

"Ahh but Rylee," you say astutely, paying far too much attention, "Isn't the star graph already disconnected
if {{< katex >}}$\mathbb{G}${{< /katex >}} has more than one vertex?"
To which I have to concede that you are correct and explain my usage further.
The star graph is a union of graphs {{< katex >}}$\Gamma_w${{< /katex >}} as {{< katex >}}$w${{< /katex >}} varies over the vertices of {{< katex >}}$\mathbb{G}${{< /katex >}},
where {{< katex >}}$\Gamma_w${{< /katex >}} contains all the vertices corresponding to directions in {{< katex >}}$D_w${{< /katex >}}.
We say that the star graph is disconnected if some {{< katex >}}$\Gamma_w${{< /katex >}} is disconnected,
and that it has a cut vertex if each {{< katex >}}$\Gamma_w${{< /katex >}} is connected and there is some direction {{< katex >}}$d \in D_w${{< /katex >}},
the removal of which disconnects {{< katex >}}$\Gamma_w${{< /katex >}}.

The proof is very much inspired by a paper of [Heusener and Weidmann][HeusenerWeidmann],
which gives a proof of the classical Whitehead lemma for free groups using Stallings folds.
The idea is that if a collection of conjugacy classes is simple,
there is a graph which folds onto the rose with a single fold
(their term is "almost rose")
in which these conjugacy classes may be read,
in the sense that the immersion {{< katex >}}$f\colon \Gamma \to R${{< /katex >}} factors through the almost rose.
They prove that (their version of) the star graph of an almost rose has a cut vertex
and that if the map {{< katex >}}$f\colon \Gamma \to R${{< /katex >}} factors through a graph {{< katex >}}$\Theta${{< /katex >}},
then the star graph of {{< katex >}}$\Gamma${{< /katex >}} is a subgraph of the star graph of {{< katex >}}$\Theta${{< /katex >}}.
Although we are working with a different notion of the star graph,
the broad-strokes outline of the proof carries over to our graph of groups setting!
If you'd like to know more, you can read the paper [here][Whitehead].

[Whitehead]: "/pdfs/Whitehead.pdf"
[BFH]: https://arxiv.org/abs/2009.10052
[HeusenerWeidmann]: https://www.degruyter.com/document/doi/10.1515/jgth-2018-0118/html?lang=en
[The Star Graph]: {{< ref "the-star-graph.md" >}}
[Free Splittings to Graphs of Groups]: {{< ref "from-free-splittings-to-graphs-of-groups.md" >}}

