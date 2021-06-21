---
layout: post
math: true
published: true
---
A famous theorem of Rips says that a finitely generated group
with a free action on a *real tree* is a free product of free abelian and surface groups.
The purpose of this blog post is to introduce real trees and illustrate this theorem by constructing
free actions of such groups on real trees.

Let us begin by defining real trees.
An *arc* in a space $$X$$ is an embedding $$\gamma\colon [a,b] \to X$$
of a closed interval of $$\mathbb{R}$$ in $$X$$.
If $$(X,d)$$ is a metric space,
an arc in $$X$$ is a *geodesic* if the embedding is an isometric embedding—that is,
for all $$s$$ and $$t$$ in $$[a,b]$$, we have

$$d(\gamma(s),\gamma(t)) = |t - s|.$$

A *real tree* or an $$\mathbb{R}$$*-tree* is a metric space $$(T,d)$$
in which every two points are joined by a unique arc,
and this arc is the image of a geodesic.

## Examples of real trees

Let's see a couple of examples of real trees.
As a first example,
$$\mathbb{R}$$ is a real tree.
If $$X$$ is a simply connected simplicial complex of dimension $$1$$,
that is, a *simplicial tree,*
we can define a metric on $$X$$
by declaring each edge of $$X$$ to be isometric to an interval of $$\mathbb{R}$$ of length $$1$$,
and then giving $$X$$ the metric where the distance between two points is the length of a shortest path between them.
In this metric, $$X$$ becomes a real tree.
The metric topology is in general strictly coarser than the simplicial topology.
This means the "identity" map from the simplicial complex $$X$$ to the metric space $$X$$ is continuous,
but its inverse need not be continuous.

## Free abelian groups act freely on real trees

It's not hard to construct free actions of finitely generated free abelian groups on real trees,
in fact the word "tree" is somewhat obfuscating:
the real tree in question is the real line $$\mathbb{R}$$.
Let $$a_1,\dotsc,a_n$$ be a basis for $$\mathbb{Z}^n$$.
Have each $$a_i$$ act by translation on $$\mathbb{R}$$ by some distance $$t_i$$.
If the $$t_i$$ are not rationally related, then the resulting action of $$\mathbb{Z}^n$$ is free.
It also has *dense orbits,* a property of some other actions of groups on real trees
that I struggled to visualize—I find this simpler example helpful in that regard!

## Surface groups act freely on real trees

The following is admittedly more complicated.
Let $$S$$ be a surface equipped with a complete Riemannian metric of constant sectional curvature $$-1$$.
A *measured geodesic lamination* $$(\mathscr{L},\mu)$$ on $$S$$
is a closed subset $$\mathscr{L} \subset S$$ (the *lamination*) which decomposes as a disjoint union of
complete geodesics (called *leaves*)
together with a *transverse measure* $$\mu$$.
This is an assignment, for each arc $$c$$ transverse to $$\mathscr{L}$$,
of a Radon measure $$\mu|_c$$ with support equal to $$c \cap \mathscr{L}$$
that is invariant under homotopy transverse to $$\mathscr{L}$$.

That's a bit of a mouthful, sorry!
A simple example of a measured geodesic lamination is just a closed geodesic $$\gamma$$ on $$S$$,
where the transverse measure simply counts the points of intersections of arcs $$c$$ with $$\gamma$$.
Notice that even if an arc $$c$$ transverse to $$\gamma$$ is homotopic to an arc with fewer points of intersection,
this homotopy cannot be performed transverse to $$\gamma$$, so the measure is really homotopy invariant.
There are measured geodesic laminations with stranger properties
than those that come from closed geodesics,
but I think it can be helpful when trying to picture things involving geodesic laminations,
to just imagine the closed geodesic case and think of a general measured geodesic lamination
as being a sort of generalization or "limit" of this picture.
Thurston has a cute picture in his notes on the geometry and topology of 3-manifolds, see below.

![Thurston's picture of a geodesic lamination](/assets/img/geodesiclamination.png)

Anyway, let $$(\mathscr{L},\mu)$$ be a measured geodesic lamination.
We can lift it to a $$\pi_1(S)$$-invariant measured geodesic lamination $$(\tilde{\mathscr{L}},\tilde\mu)$$
on the universal cover $$\tilde S$$ of $$S$$.
I will describe [Morgan and Shalen's][MorganShalen]
construction of a real tree *dual* to $$(\tilde{\mathscr{L}},\tilde\mu)$$.
Since $$(\tilde{\mathscr{L}},\tilde\mu)$$ is $$\pi_1(S)$$-invariant,
we will obtain an action of $$\pi_1(S)$$ by isometries on the dual real tree.
Let $$C$$ be the set of complementary components of $$\tilde S\setminus \tilde{\mathscr{L}}$$.
Given components $$c$$ and $$c'$$,
let $$\gamma$$ be a path with one endpoint in $$c$$ and the other in $$c'$$
such that $$\gamma$$ is transverse to $$\tilde{\mathscr{L}}$$ and intersects each leaf of $$\tilde{\mathscr{L}}$$
at most once.
For example, given a point $$x$$ in $$c$$ and $$y$$ in $$c'$$,
the path $$\gamma$$ could be the unique geodesic from $$x$$ to $$y$$.
Define

$$d(c,c') = \int_\gamma d\tilde\mu. $$

Morgan and Shalen show that this defines a well-defined distance function on $$C$$,
and that this distance satisfies a $$0$$-hyperbolicity condition,
therefore there is a real tree $$T$$ equipped with an isometric embedding $$C \to T$$
such that $$T$$ is the smallest subtree containing the image of $$C$$.
This tree $$T$$ is unique up to unique isometry,
so in particular the action of $$\pi_1(S)$$ on $$C$$ extends to an action on $$T$$.

Let us return to our example of a measured geodesic lamination $$(\mathscr{L},\mu)$$,
where $$\mathscr{L}$$ was a closed geodesic $$\gamma$$
and the transverse measure $$\mu$$ counted intersection points.
Thinking of $$\gamma$$ as an element of $$\pi_1(S)$$,
the lamination $$\tilde{\mathscr{L}}$$ has a leaf for each conjugate of $$\gamma$$ in $$\pi_1(S)$$,
and each leaf separates $$\tilde S$$ into two components.
The minimal intersection number for a path joining the complementary components is $$1$$,
so adjacent components are at distance one in $$T$$.
In fact, if you know a little Bass–Serre theory,
the dual tree turns out to be exactly the Bass–Serre tree for the one-edge splitting of $$\pi_1(S)$$
with edge group $$\langle\gamma\rangle$$, where each edge has been assigned length $$1$$!
Notice that the action of $$\pi_1(S)$$ on this particular tree is *not* free.

Morgan and Shalen show that the stabilizer of a point $$p$$ in $$T$$ under the action of $$\pi_1(S)$$
is the stabilizer of the corresponding component of $$\tilde S \setminus \tilde{\mathscr{L}}$$ if
$$p$$ is in the image of $$C$$, and is the stabilizer of a leaf of $$\mathscr{L}$$ otherwise.
Their key result (which they prove with a Baire Category Theorem argument!)
is the following.

**Theorem.** If $$S$$ is a closed hyperbolic surface that is not the connect sum of three projective planes,
there is a measured geodesic lamination $$(\mathscr{L},\mu)$$ on $$S$$
all of whose leaves and complementary components are simply connected.

It follows that the action of $$\pi_1(S)$$ on the dual tree $$T$$ is free.
Morgan and Shalen also prove algebraically that if $$S$$ *is* the connect sum of three projective planes,
then $$\pi_1(S)$$ cannot act freely on a real tree.

## Free products of groups acting freely

In the remainder of this post,
we will prove the following theorem.

**Theorem.** If $$A$$ and $$B$$ are groups acting freely on real trees $$S$$ and $$T$$,
then there is a real tree $$X$$ on which the free product $$A*B$$ acts freely.

If $$G$$ is a finitely generated group,
[Grushko's theorem](https://en.wikipedia.org/wiki/Grushko_theorem)
says that the number of factors in any free product decomposition of $$G$$ is finite,
so applying the theorem inductively provides examples of free actions
of finitely generated free products of free abelian and surface groups.
(Provided, of course, that none of the surfaces in question are the projective plane,
the Klein bottle, or the connect sum of three projective planes.)

*Proof.* The free product $$G = A*B$$ acts on a (simplicial) tree $$Y$$
with two orbits of vertices and one orbit of edges with trivial edge stabilizers.
By the orbit stabilizer theorem, the tree has the following description.
The vertex set is the union of the sets of cosets of $$A$$ and $$B$$ in $$G$$,
and the edge set is the set of elements of $$G$$.
The edge labeled $$g$$ connects the vertices labeled $$gA$$ and $$gB$$.
Choose points $$s \in S$$ and $$t \in T$$.
The real tree $$X$$ will be constructed in the following way.
We replace vertices of $$Y$$ with copies of $$S$$ or $$T$$, corresponding to whether
the vertex corresponded to a coset of $$A$$ or $$B$$, respectively,
gluing the edges of $$Y$$ so that one endpoint lies in a copy of $$S$$ and the other in a copy of $$T$$.

Explicitly the space $$X$$ is the quotient of the disjoint union $$G\times S \sqcup G \times T \sqcup G\times [0,1]$$
by the following relations, where $$g \in G$$, $$x \in S$$, $$y \in T$$, $$a \in A$$ and $$b \in B$$:
 - $$(ga,x) \sim (g,a.x)$$,
 - $$(gb,y) \sim (g,b.y)$$,
 - $$(g,0) \sim (g,s)$$ and
 - $$(g,1) \sim (g,t)$$.

One checks that the relations imply that there is a copy of $$S$$ for each coset $$gA$$ in $$G$$,
a copy of $$T$$ for each coset $$gB$$ in $$G$$,
and an edge $$[0,1]$$ for each element of $$G$$.
Since $$Y$$ was a tree, $$X$$ will be a real tree.
The multiplication in the labels of the disjoint union yields an action of $$G$$ on $$X$$ by isometries.
There is a natural equivariant map $$X \to Y$$ that collapses each copy of $$S$$ and each copy of $$T$$ to a point.
Each element $$g$$ of $$G$$ either acts freely on $$Y$$ (in which case it must act freely on $$X$$),
or it stabilizes a unique vertex of $$Y$$, in which case $$g$$ is conjugate to an element of $$A$$ or $$B$$.
In this latter case, $$g$$ preserves a copy of $$S$$ or $$T$$ 
and one checks that it acts as an element of $$A$$ or $$B$$.
But since the actions of $$A$$ and $$B$$ were free, it follows that if $$g$$ is nontrivial, then it acts freely.
$$\blacksquare$$

[MorganShalen]: https://www.sciencedirect.com/science/article/pii/004093839190002L
