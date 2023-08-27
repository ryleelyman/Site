---
title: "Free Actions on Real Trees"
date: 2021-06-21T14:38:35-04:00
math: true
---
A famous theorem of Rips says that a finitely generated group
with a free action on a *real tree* is a free product of free abelian and surface groups.
The purpose of this blog post is to introduce real trees and illustrate this theorem by constructing
free actions of such groups on real trees.

Let us begin by defining real trees.
An *arc* in a space {{< katex >}}$X${{< /katex >}} is an embedding {{< katex >}}$\gamma\colon [a,b] \to X${{< /katex >}}
of a closed interval of {{< katex >}}$\mathbb{R}${{< /katex >}} in {{< katex >}}$X${{< /katex >}}.
If {{< katex >}}$(X,d)${{< /katex >}} is a metric space,
an arc in {{< katex >}}$X${{< /katex >}} is a *geodesic* if the embedding is an isometric embedding—that is,
for all {{< katex >}}$s${{< /katex >}} and {{< katex >}}$t${{< /katex >}} in {{< katex >}}$[a,b]${{< /katex >}}, we have

{{< katex >}}$d(\gamma(s),\gamma(t)) = |t - s|.${{< /katex >}}

A *real tree* or an {{< katex >}}$\mathbb{R}${{< /katex >}}-*tree* is a metric space {{< katex >}}$(T,d)${{< /katex >}}
in which every two points are joined by a unique arc,
and this arc is the image of a geodesic.

## Examples of real trees

Let's see a couple of examples of real trees.
As a first example,
{{< katex >}}$\mathbb{R}${{< /katex >}} is a real tree.
If {{< katex >}}$X${{< /katex >}} is a simply connected simplicial complex of dimension {{< katex >}}$1${{< /katex >}},
that is, a *simplicial tree,*
we can define a metric on {{< katex >}}$X${{< /katex >}}
by declaring each edge of {{< katex >}}$X${{< /katex >}} to be isometric to an interval of {{< katex >}}$\mathbb{R}${{< /katex >}} of length {{< katex >}}$1${{< /katex >}},
and then giving {{< katex >}}$X${{< /katex >}} the metric where the distance between two points is the length of a shortest path between them.
In this metric, {{< katex >}}$X${{< /katex >}} becomes a real tree.
The metric topology is in general strictly coarser than the simplicial topology.
This means the "identity" map from the simplicial complex {{< katex >}}$X${{< /katex >}} to the metric space {{< katex >}}$X${{< /katex >}} is continuous,
but its inverse need not be continuous.

## Free abelian groups act freely on real trees

It's not hard to construct free actions of finitely generated free abelian groups on real trees,
in fact the word "tree" is somewhat obfuscating:
the real tree in question is the real line {{< katex >}}$\mathbb{R}${{< /katex >}}.
Let {{< katex >}}$a_1,\dotsc,a_n${{< /katex >}} be a basis for {{< katex >}}$\mathbb{Z}^n${{< /katex >}}.
Have each {{< katex >}}$a_i${{< /katex >}} act by translation on {{< katex >}}$\mathbb{R}${{< /katex >}} by some distance {{< katex >}}$t_i${{< /katex >}}.
If the {{< katex >}}$t_i${{< /katex >}} are not rationally related, then the resulting action of {{< katex >}}$\mathbb{Z}^n${{< /katex >}} is free.
It also has *dense orbits,* a property of some other actions of groups on real trees
that I struggled to visualize—I find this simpler example helpful in that regard!

## Surface groups act freely on real trees

The following is admittedly more complicated.
Let {{< katex >}}$S${{< /katex >}} be a surface equipped with a complete Riemannian metric of constant sectional curvature {{< katex >}}$-1${{< /katex >}}.
A *measured geodesic lamination* {{< katex >}}$(\mathscr{L},\mu)${{< /katex >}} on {{< katex >}}$S${{< /katex >}}
is a closed subset {{< katex >}}$\mathscr{L} \subset S${{< /katex >}} (the *lamination*) which decomposes as a disjoint union of
complete geodesics (called *leaves*)
together with a *transverse measure* {{< katex >}}$\mu${{< /katex >}}.
This is an assignment, for each arc {{< katex >}}$c${{< /katex >}} transverse to {{< katex >}}$\mathscr{L}${{< /katex >}},
of a Radon measure {{< katex >}}$\mu|_c${{< /katex >}} with support equal to {{< katex >}}$c \cap \mathscr{L}${{< /katex >}}
that is invariant under homotopy transverse to {{< katex >}}$\mathscr{L}${{< /katex >}}.

That's a bit of a mouthful, sorry!
A simple example of a measured geodesic lamination is just a closed geodesic {{< katex >}}$\gamma${{< /katex >}} on {{< katex >}}$S${{< /katex >}},
where the transverse measure simply counts the points of intersections of arcs {{< katex >}}$c${{< /katex >}} with {{< katex >}}$\gamma${{< /katex >}}.
Notice that even if an arc {{< katex >}}$c${{< /katex >}} transverse to {{< katex >}}$\gamma${{< /katex >}} is homotopic to an arc with fewer points of intersection,
this homotopy cannot be performed transverse to {{< katex >}}$\gamma${{< /katex >}}, so the measure is really homotopy invariant.
There are measured geodesic laminations with stranger properties
than those that come from closed geodesics,
but I think it can be helpful when trying to picture things involving geodesic laminations,
to just imagine the closed geodesic case and think of a general measured geodesic lamination
as being a sort of generalization or "limit" of this picture.
Thurston has a cute picture in his notes on the geometry and topology of 3-manifolds, see below.

![Thurston's picture of a geodesic lamination](/img/geodesiclamination.png)

Anyway, let {{< katex >}}$(\mathscr{L},\mu)${{< /katex >}} be a measured geodesic lamination.
We can lift it to a {{< katex >}}$\pi_1(S)${{< /katex >}}-invariant measured geodesic lamination {{< katex >}}$(\tilde{\mathscr{L}},\tilde\mu)${{< /katex >}}
on the universal cover {{< katex >}}$\tilde S${{< /katex >}} of {{< katex >}}$S${{< /katex >}}.
I will describe [Morgan and Shalen's][MorganShalen]
construction of a real tree *dual* to {{< katex >}}$(\tilde{\mathscr{L}},\tilde\mu)${{< /katex >}}.
Since {{< katex >}}$(\tilde{\mathscr{L}},\tilde\mu)${{< /katex >}} is {{< katex >}}$\pi_1(S)${{< /katex >}}-invariant,
we will obtain an action of {{< katex >}}$\pi_1(S)${{< /katex >}} by isometries on the dual real tree.
Let {{< katex >}}$C${{< /katex >}} be the set of complementary components of {{< katex >}}$\tilde S\setminus \tilde{\mathscr{L}}${{< /katex >}}.
Given components {{< katex >}}$c${{< /katex >}} and {{< katex >}}$c'${{< /katex >}},
let {{< katex >}}$\gamma${{< /katex >}} be a path with one endpoint in {{< katex >}}$c${{< /katex >}} and the other in {{< katex >}}$c'${{< /katex >}}
such that {{< katex >}}$\gamma${{< /katex >}} is transverse to {{< katex >}}$\tilde{\mathscr{L}}${{< /katex >}} and intersects each leaf of {{< katex >}}$\tilde{\mathscr{L}}${{< /katex >}}
at most once.
For example, given a point {{< katex >}}$x${{< /katex >}} in {{< katex >}}$c${{< /katex >}} and {{< katex >}}$y${{< /katex >}} in {{< katex >}}$c'${{< /katex >}},
the path {{< katex >}}$\gamma${{< /katex >}} could be the unique geodesic from {{< katex >}}$x${{< /katex >}} to {{< katex >}}$y${{< /katex >}}.
Define

{{< katex >}}$d(c,c') = \int_\gamma d\tilde\mu. ${{< /katex >}}

Morgan and Shalen show that this defines a well-defined distance function on {{< katex >}}$C${{< /katex >}},
and that this distance satisfies a {{< katex >}}$0${{< /katex >}}-hyperbolicity condition,
therefore there is a real tree {{< katex >}}$T${{< /katex >}} equipped with an isometric embedding {{< katex >}}$C \to T${{< /katex >}}
such that {{< katex >}}$T${{< /katex >}} is the smallest subtree containing the image of {{< katex >}}$C${{< /katex >}}.
This tree {{< katex >}}$T${{< /katex >}} is unique up to unique isometry,
so in particular the action of {{< katex >}}$\pi_1(S)${{< /katex >}} on {{< katex >}}$C${{< /katex >}} extends to an action on {{< katex >}}$T${{< /katex >}}.

Let us return to our example of a measured geodesic lamination {{< katex >}}$(\mathscr{L},\mu)${{< /katex >}},
where {{< katex >}}$\mathscr{L}${{< /katex >}} was a closed geodesic {{< katex >}}$\gamma${{< /katex >}}
and the transverse measure {{< katex >}}$\mu${{< /katex >}} counted intersection points.
Thinking of {{< katex >}}$\gamma${{< /katex >}} as an element of {{< katex >}}$\pi_1(S)${{< /katex >}},
the lamination {{< katex >}}$\tilde{\mathscr{L}}${{< /katex >}} has a leaf for each conjugate of {{< katex >}}$\gamma${{< /katex >}} in {{< katex >}}$\pi_1(S)${{< /katex >}},
and each leaf separates {{< katex >}}$\tilde S${{< /katex >}} into two components.
The minimal intersection number for a path joining the complementary components is {{< katex >}}$1${{< /katex >}},
so adjacent components are at distance one in {{< katex >}}$T${{< /katex >}}.
In fact, if you know a little Bass–Serre theory,
the dual tree turns out to be exactly the Bass–Serre tree for the one-edge splitting of {{< katex >}}$\pi_1(S)${{< /katex >}}
with edge group {{< katex >}}$\langle\gamma\rangle${{< /katex >}}, where each edge has been assigned length {{< katex >}}$1${{< /katex >}}!
Notice that the action of {{< katex >}}$\pi_1(S)${{< /katex >}} on this particular tree is *not* free.

Morgan and Shalen show that the stabilizer of a point {{< katex >}}$p${{< /katex >}} in {{< katex >}}$T${{< /katex >}} under the action of {{< katex >}}$\pi_1(S)${{< /katex >}}
is the stabilizer of the corresponding component of {{< katex >}}$\tilde S \setminus \tilde{\mathscr{L}}${{< /katex >}} if
{{< katex >}}$p${{< /katex >}} is in the image of {{< katex >}}$C${{< /katex >}}, and is the stabilizer of a leaf of {{< katex >}}$\mathscr{L}${{< /katex >}} otherwise.
Their key result (which they prove with a Baire Category Theorem argument!)
is the following.

**Theorem.** If {{< katex >}}$S${{< /katex >}} is a closed hyperbolic surface that is not the connect sum of three projective planes,
there is a measured geodesic lamination {{< katex >}}$(\mathscr{L},\mu)${{< /katex >}} on {{< katex >}}$S${{< /katex >}}
all of whose leaves and complementary components are simply connected.

It follows that the action of {{< katex >}}$\pi_1(S)${{< /katex >}} on the dual tree {{< katex >}}$T${{< /katex >}} is free.
Morgan and Shalen also prove algebraically that if {{< katex >}}$S${{< /katex >}} *is* the connect sum of three projective planes,
then {{< katex >}}$\pi_1(S)${{< /katex >}} cannot act freely on a real tree.

## Free products of groups acting freely

In the remainder of this post,
we will prove the following theorem.

**Theorem.** If {{< katex >}}$A${{< /katex >}} and {{< katex >}}$B${{< /katex >}} are groups acting freely on real trees {{< katex >}}$S${{< /katex >}} and {{< katex >}}$T${{< /katex >}},
then there is a real tree {{< katex >}}$X${{< /katex >}} on which the free product {{< katex >}}$A*B${{< /katex >}} acts freely.

If {{< katex >}}$G${{< /katex >}} is a finitely generated group,
[Grushko's theorem](https://en.wikipedia.org/wiki/Grushko_theorem)
says that the number of factors in any free product decomposition of {{< katex >}}$G${{< /katex >}} is finite,
so applying the theorem inductively provides examples of free actions
of finitely generated free products of free abelian and surface groups.
(Provided, of course, that none of the surfaces in question are the projective plane,
the Klein bottle, or the connect sum of three projective planes.)

*Proof.* The free product {{< katex >}}$G = A*B${{< /katex >}} acts on a (simplicial) tree {{< katex >}}$Y${{< /katex >}}
with two orbits of vertices and one orbit of edges with trivial edge stabilizers.
By the orbit stabilizer theorem, the tree has the following description.
The vertex set is the union of the sets of cosets of {{< katex >}}$A${{< /katex >}} and {{< katex >}}$B${{< /katex >}} in {{< katex >}}$G${{< /katex >}},
and the edge set is the set of elements of {{< katex >}}$G${{< /katex >}}.
The edge labeled {{< katex >}}$g${{< /katex >}} connects the vertices labeled {{< katex >}}$gA${{< /katex >}} and {{< katex >}}$gB${{< /katex >}}.
Choose points {{< katex >}}$s \in S${{< /katex >}} and {{< katex >}}$t \in T${{< /katex >}}.
The real tree {{< katex >}}$X${{< /katex >}} will be constructed in the following way.
We replace vertices of {{< katex >}}$Y${{< /katex >}} with copies of {{< katex >}}$S${{< /katex >}} or {{< katex >}}$T${{< /katex >}}, corresponding to whether
the vertex corresponded to a coset of {{< katex >}}$A${{< /katex >}} or {{< katex >}}$B${{< /katex >}}, respectively,
gluing the edges of {{< katex >}}$Y${{< /katex >}} so that one endpoint lies in a copy of {{< katex >}}$S${{< /katex >}} and the other in a copy of {{< katex >}}$T${{< /katex >}}.

Explicitly the space {{< katex >}}$X${{< /katex >}} is the quotient of the disjoint union {{< katex >}}$G\times S \sqcup G \times T \sqcup G\times [0,1]${{< /katex >}}
by the following relations, where {{< katex >}}$g \in G${{< /katex >}}, {{< katex >}}$x \in S${{< /katex >}}, {{< katex >}}$y \in T${{< /katex >}}, {{< katex >}}$a \in A${{< /katex >}} and {{< katex >}}$b \in B${{< /katex >}}:
 - {{< katex >}}$(ga,x) \sim (g,a.x)${{< /katex >}},
 - {{< katex >}}$(gb,y) \sim (g,b.y)${{< /katex >}},
 - {{< katex >}}$(g,0) \sim (g,s)${{< /katex >}} and
 - {{< katex >}}$(g,1) \sim (g,t)${{< /katex >}}.

One checks that the relations imply that there is a copy of {{< katex >}}$S${{< /katex >}} for each coset {{< katex >}}$gA${{< /katex >}} in {{< katex >}}$G${{< /katex >}},
a copy of {{< katex >}}$T${{< /katex >}} for each coset {{< katex >}}$gB${{< /katex >}} in {{< katex >}}$G${{< /katex >}},
and an edge {{< katex >}}$[0,1]${{< /katex >}} for each element of {{< katex >}}$G${{< /katex >}}.
Since {{< katex >}}$Y${{< /katex >}} was a tree, {{< katex >}}$X${{< /katex >}} will be a real tree.
The multiplication in the labels of the disjoint union yields an action of {{< katex >}}$G${{< /katex >}} on {{< katex >}}$X${{< /katex >}} by isometries.
There is a natural equivariant map {{< katex >}}$X \to Y${{< /katex >}} that collapses each copy of {{< katex >}}$S${{< /katex >}} and each copy of {{< katex >}}$T${{< /katex >}} to a point.
Each element {{< katex >}}$g${{< /katex >}} of {{< katex >}}$G${{< /katex >}} either acts freely on {{< katex >}}$Y${{< /katex >}} (in which case it must act freely on {{< katex >}}$X${{< /katex >}}),
or it stabilizes a unique vertex of {{< katex >}}$Y${{< /katex >}}, in which case {{< katex >}}$g${{< /katex >}} is conjugate to an element of {{< katex >}}$A${{< /katex >}} or {{< katex >}}$B${{< /katex >}}.
In this latter case, {{< katex >}}$g${{< /katex >}} preserves a copy of {{< katex >}}$S${{< /katex >}} or {{< katex >}}$T${{< /katex >}} 
and one checks that it acts as an element of {{< katex >}}$A${{< /katex >}} or {{< katex >}}$B${{< /katex >}}.
But since the actions of {{< katex >}}$A${{< /katex >}} and {{< katex >}}$B${{< /katex >}} were free, it follows that if {{< katex >}}$g${{< /katex >}} is nontrivial, then it acts freely.
{{< katex >}}$\blacksquare${{< /katex >}}

[MorganShalen]: https://www.sciencedirect.com/science/article/pii/004093839190002L
