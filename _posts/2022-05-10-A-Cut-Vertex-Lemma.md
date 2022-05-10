---
layout: post
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
any finitely generated subgroup $$H$$ of a free group $$G$$
may be represented by an immersion of a finite graph $$\Gamma$$ into a rose $$R$$,
that is a graph with one vertex $$w$$ and $$n$$ edges, where $$n$$ is the rank of $$G$$.
The set of directions $$D_w$$ is the set of oriented edges of $$R$$.
Cut each edge of $$\Gamma$$ at its midpoint,
observe that the half-edge left over crosses a direction of $$R$$
and attach, in the star graph of $$\Gamma$$,
the half-edge to the vertex corresponding to the given direction in $$D_w$$.
Thus we get a bipartite graph with one vertex for each vertex of $$\Gamma$$
and one vertex for each direction in $$D_w$$.
A pair of directions are connected by a path of length two in this star graph
if and only if the corresponding [turn][The Star Graph] 
is in the image of the map on turns associated to the immersion $$\Gamma \to R$$.

This idea generalizes readily to $$G$$ the fundamental group of a graph of groups $$\mathbb{G}$$.
A subgroup of $$G$$ is convex-cocompact if and only if it may be represented as an immersion
of a finite connected graph of groups $$f\colon \mathcal{G} \to \mathbb{G}$$.
The set of directions we have met before.
Rather than snipping edges at midpoints in $$\mathcal{G}$$,
we essentially do this in the Bass–Serre tree.
If $$v$$ is a vertex of $$\mathcal{G}$$ mapping to a vertex $$w$$ in $$\mathbb{G}$$,
we attach $$|\mathbb{G}_w : f_v(\mathcal{G}_v)|$$ copies of this *piece*
of the Bass–Serre tree,
where the $$gf_v(\mathcal{G}_v)$$ copy attaches an edge corresponding to a direction $$d$$ in $$D_v$$
to the vertex corresponding to the direction $$g.D_vf(d)$$ in $$D_w$$.

Suppose there exists $$\mathcal{G}'$$ a graph of groups with fundamental group $$G$$ and one edge
with the property that $$\mathcal{G}'$$ may be obtained from a graph of groups
[homotopy equivalent][Free Splittings to Graphs of Groups] to $$\mathbb{G}$$ by collapsing edges.
Anyway, say that a conjugacy class of an element or convex-cocompact subgroup of $$G$$ is *simple*
if there is such a graph of groups $$\mathcal{G}'$$ with the property that our element or subgroup
is conjugate into a vertex group in $$\mathcal{G}'$$.
For free groups thought of as fundamental groups of ordinary graphs,
it's not hard to see that an element or finitely generated (hence convex-cocompact) subgroup
is simple if and only if it is contained in a proper free factor of the free group.

The main result of my paper is that if we have a *jointly* simple collection $$C$$ of conjugacy classes
of elements or convex-cocompact subgroups of $$G$$
(i.e. the same $$\mathcal{G}'$$ works for all members of $$C$$ at once)
then the star graph of $$C$$ is either disconnected or has a cut vertex.

"Ahh but Rylee," you say astutely, paying far too much attention, "Isn't the star graph already disconnected
if $$\mathbb{G}$$ has more than one vertex?"
To which I have to concede that you are correct and explain my usage further.
The star graph is a union of graphs $$\Gamma_w$$ as $$w$$ varies over the vertices of $$\mathbb{G}$$,
where $$\Gamma_w$$ contains all the vertices corresponding to directions in $$D_w$$.
We say that the star graph is disconnected if some $$\Gamma_w$$ is disconnected,
and that it has a cut vertex if each $$\Gamma_w$$ is connected and there is some direction $$d \in D_w$$,
the removal of which disconnects $$\Gamma_w$$.

The proof is very much inspired by a paper of [Heusener and Weidmann][HeusenerWeidmann],
which gives a proof of the classical Whitehead lemma for free groups using Stallings folds.
The idea is that if a collection of conjugacy classes is simple,
there is a graph which folds onto the rose with a single fold
(their term is "almost rose")
in which these conjugacy classes may be read,
in the sense that the immersion $$f\colon \Gamma \to R$$ factors through the almost rose.
They prove that (their version of) the star graph of an almost rose has a cut vertex
and that if the map $$f\colon \Gamma \to R$$ factors through a graph $$\Theta$$,
then the star graph of $$\Gamma$$ is a subgraph of the star graph of $$\Theta$$.
Although we are working with a different notion of the star graph,
the broad-strokes outline of the proof carries over to our graph of groups setting!
If you'd like to know more, you can read the paper [here][Whitehead].

[Whitehead]: {{ "assets/pdfs/Whitehead.pdf" | relative_url }}
[BFH]: https://arxiv.org/abs/2009.10052
[HeusenerWeidmann]: https://www.degruyter.com/document/doi/10.1515/jgth-2018-0118/html?lang=en
[The Star Graph]: {% link _posts/2022-04-02-The-star-graph.md %}
[Free Splittings to Graphs of Groups]: {% link _posts/2022-01-06-From-free-splittings-to-graphs-of-groups.md %}
