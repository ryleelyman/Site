---
title: "More on Free Splittings"
date: 2021-12-29T15:03:14-04:00
math: true
---

Let {{< katex >}}$F${{< /katex >}} be a group.
A *free splitting* of {{< katex >}}$F${{< /katex >}} is a simplicial tree {{< katex >}}$T${{< /katex >}}
equipped with an {{< katex >}}$F${{< /katex >}}-action
such that edge stabilizers are trivial.
I've been thinking a lot about free splittings;
here are some of my musings.
There isn't really a punch line here,
but since it was clarifying to write this, I may as well post it.

We are interested in free splittings where there are finitely many orbits of edges
and some vertex has infinite stabilizer.
In this case, Bass–Serre theory shows that {{< katex >}}$F${{< /katex >}}
is a free product of the form

{{< katex >}}$F = A_1*\cdots*A_n*F_k${{< /katex >}}

where the {{< katex >}}$A_i${{< /katex >}} are countable groups
(at least one of which is infinite)
and {{< katex >}}$F_k${{< /katex >}} is a free group of finite rank {{< katex >}}$k${{< /katex >}}.

## The Gromov boundary of {{< katex >}}$T${{< /katex >}}

Fix a basepoint {{< katex >}}$p \in T${{< /katex >}}.
A *geodesic ray* in {{< katex >}}$T${{< /katex >}} based at {{< katex >}}$p${{< /katex >}}
is a proper embedding {{< katex >}}$\xi\colon [0,\infty) \to T${{< /katex >}}
such that {{< katex >}}$\xi(0) = p${{< /katex >}}.
We are really interested in the image of {{< katex >}}$\xi${{< /katex >}} more than the map.
Similarly we have *geodesics;* embeddings {{< katex >}}$[0,1] \to T${{< /katex >}}.
Every path in {{< katex >}}$T${{< /katex >}} is homotopic rel endpoints to a unique geodesic or to a constant map.
Let {{< katex >}}$\partial_\infty T${{< /katex >}} denote the set of geodesic rays in {{< katex >}}$T${{< /katex >}} based at {{< katex >}}$p${{< /katex >}}.
This is the *Gromov boundary* of {{< katex >}}$T${{< /katex >}}.
We may topologize {{< katex >}}$T \cup \partial_\infty T${{< /katex >}} by giving {{< katex >}}$T${{< /katex >}} the usual topology
and defining basic open neighborhoods of boundary points in the following way.
Given a boundary point {{< katex >}}$\xi${{< /katex >}}, the basic open neighborhood is determined by a finite subpath
{{< katex >}}$\gamma${{< /katex >}} of the ray {{< katex >}}$\xi${{< /katex >}};
the basic open set {{< katex >}}$N(\gamma)${{< /katex >}} consists of those points {{< katex >}}$x \in T \cup \partial_\infty T${{< /katex >}}
such that the geodesic from {{< katex >}}$p${{< /katex >}} to {{< katex >}}$x${{< /katex >}} contains {{< katex >}}$\gamma${{< /katex >}}.
In [July][Boundaries1], we showed that in our situation,
if all the groups {{< katex >}}$A_i${{< /katex >}} are countable and one is countably infinite,
then the Gromov boundary of {{< katex >}}$T${{< /katex >}} is homeomorphic (in the subspace topology) to the Baire space.

## The observer's topology

We may give {{< katex >}}$T \cup \partial_\infty T${{< /katex >}} a different topology
that makes it into a compact space:
this is the *observer's topology,* coined by [Coulbois, Hilion and Lustig][CHL].
Let {{< katex >}}$x \in T${{< /katex >}} be a point.
A *half-tree* based at {{< katex >}}$x${{< /katex >}} is a component of {{< katex >}}$T \setminus \{x\}${{< /katex >}}.
A subbasis for the observer's topology on {{< katex >}}$T \cup \partial_\infty T${{< /katex >}} 
is given by the set of half-trees;
where we say a boundary point {{< katex >}}$\xi \in \partial_\infty T${{< /katex >}} belongs to a half-tree
if the corresponding geodesic ray has infinite intersection with the half-tree.
In our situation, where the groups {{< katex >}}$A_i${{< /katex >}} are countable,
the tree {{< katex >}}$T${{< /katex >}} has countably many edges, so has a countable dense subset.
Since every point supports at most countably many half-trees,
it follows that the observer's topology on {{< katex >}}$T \cup \partial_\infty T${{< /katex >}} is second countable.
Thus it makes sense to talk about the topology in terms of convergent sequences:
a sequence {{< katex >}}$\{x_n\} \in T \cup \partial_\infty T${{< /katex >}} converges to a point {{< katex >}}$x${{< /katex >}}
if for every point {{< katex >}}$y \ne x${{< /katex >}},
the points {{< katex >}}$x_n${{< /katex >}} belong to the same half-tree at {{< katex >}}$y${{< /katex >}} as {{< katex >}}$x${{< /katex >}} for {{< katex >}}$n${{< /katex >}} sufficiently large.

Coulbois, Hilion and Lustig show that {{< katex >}}$T \cup \partial_\infty T${{< /katex >}} is compact in the observer's topology.
Here is their argument:
suppose {{< katex >}}$\{x_n\}${{< /katex >}} is a sequence,
and let {{< katex >}}$\{U_i\}${{< /katex >}} be a countable set of half-trees 
generating the topology on {{< katex >}}$T \cup \partial_\infty T${{< /katex >}}
For each {{< katex >}}$U_i${{< /katex >}}, we may, after passing to a subsequence,
assume that {{< katex >}}$x_n${{< /katex >}} either belongs to {{< katex >}}$U_i${{< /katex >}} or not for {{< katex >}}$n${{< /katex >}} large.
Now note that the intersection of (the images of) two (distinct)
geodesics or geodesic rays based at {{< katex >}}$p${{< /katex >}}
is either a point or a geodesic.
Let {{< katex >}}$\gamma_n${{< /katex >}} denote the geodesic or geodesic ray from {{< katex >}}$p${{< /katex >}} to {{< katex >}}$x_n${{< /katex >}},
and consider the geodesic

{{< katex >}}$I_k = \bigcap_{m \ge k} \gamma_m.${{< /katex >}}

Observe that {{< katex >}}$I_k \subset I_{k+1}${{< /katex >}}, so

{{< katex >}}$\overline{\bigcup_k I_k}${{< /katex >}}

is a geodesic or geodesic ray; let its endpoint be {{< katex >}}$x${{< /katex >}}.
We will show that our subsequence {{< katex >}}$\{x_n\}${{< /katex >}} converges to {{< katex >}}$x${{< /katex >}}.
Suppose for {{< katex >}}$n \ge N${{< /katex >}} we have that {{< katex >}}$x_n \notin U_i${{< /katex >}}.
Then for any finite collection of such {{< katex >}}$x_n${{< /katex >}},
the subtree spanned by the collection is entirely outside {{< katex >}}$U_i${{< /katex >}},
since the (closed) complement of a half-tree is convex.
The nearest point to {{< katex >}}$p${{< /katex >}} belongs to this spanning subtree,
so inductively this shows that the endpoint of {{< katex >}}$I_k${{< /katex >}} is outside {{< katex >}}$U_i${{< /katex >}} for large {{< katex >}}$k${{< /katex >}}.
It follows that {{< katex >}}$x \notin U_i${{< /katex >}}. 
Therefore if {{< katex >}}$x \in U_i${{< /katex >}}, then infinitely many,
and thus all but finitely many of the {{< katex >}}$x_n${{< /katex >}} belong to {{< katex >}}$U_i${{< /katex >}},
showing that the sequence {{< katex >}}$\{x_n\}${{< /katex >}} converges to {{< katex >}}$x${{< /katex >}}.

Next we would like to show that the topology induced on {{< katex >}}$\partial_\infty T${{< /katex >}}
agrees with the one above.
Suppose {{< katex >}}$\{x_n\}${{< /katex >}} converges to {{< katex >}}$\xi \in \partial_\infty T${{< /katex >}} in the observer's topology,
so for any point {{< katex >}}$y \in T${{< /katex >}},
the points {{< katex >}}$x_n${{< /katex >}} belong to the same half-tree at {{< katex >}}$y${{< /katex >}} as {{< katex >}}$\xi${{< /katex >}} for {{< katex >}}$n${{< /katex >}} large.
Taking the points {{< katex >}}$y${{< /katex >}} to be on the geodesic ray {{< katex >}}$\xi${{< /katex >}}
shows that the geodesic or geodesic ray from {{< katex >}}$p${{< /katex >}} to {{< katex >}}$x_n${{< /katex >}}
must contain any finite subpath of {{< katex >}}$\xi${{< /katex >}} for {{< katex >}}$n${{< /katex >}} large.
If conversely the geodesic or geodesic ray from {{< katex >}}$p${{< /katex >}} to {{< katex >}}$x_n${{< /katex >}}
contains any finite subpath of {{< katex >}}$\xi${{< /katex >}} for {{< katex >}}$n${{< /katex >}} sufficiently large,
then if the intersection of the ray {{< katex >}}$\xi${{< /katex >}} with a given half-tree is infinite,
we may take a finite subpath {{< katex >}}$\gamma${{< /katex >}} so large that it ends inside the half-tree.
If the geodesic or geodesic ray from {{< katex >}}$p${{< /katex >}} to {{< katex >}}$x_n${{< /katex >}} contains {{< katex >}}$\gamma${{< /katex >}},
then since {{< katex >}}$T${{< /katex >}} is a tree, we conclude that {{< katex >}}$x_n${{< /katex >}} belongs to the half-tree.

## The Bowditch Boundary of {{< katex >}}$T${{< /katex >}}

It's not hard to see that if {{< katex >}}$x \in T${{< /katex >}} is a point of finite valence,
(i.e. either a vertex of finite valence or a point in the interior of an edge)
then there is a basic open set containing {{< katex >}}$x${{< /katex >}} that contains only points of finite valence.
If we write {{< katex >}}$V_\infty(T)${{< /katex >}} for the set of vertices of infinite valence,
this argument shows that {{< katex >}}$\partial T = \partial_\infty T \cup V_\infty(T)${{< /katex >}}
is closed in the observer's topology,
hence it is compact.
This is the *Bowditch boundary* of {{< katex >}}$T${{< /katex >}}.
In fact, we showed in [July][Boundaries1] that {{< katex >}}$\partial T${{< /katex >}} is a Cantor set;
one might think of the points {{< katex >}}$V_\infty(T)${{< /katex >}} as being akin to the rational points
of the standard middle-thirds Cantor set.

## Laminations

Consider the space

{{< katex >}}$\tilde{\mathcal{B}}(T) = ((\partial T \times \partial T)\setminus \Delta )/ \mathbb{Z}/2\mathbb{Z}${{< /katex >}}

where {{< katex >}}$\Delta${{< /katex >}} is the diagonal and {{< katex >}}$\mathbb{Z}/2\mathbb{Z}${{< /katex >}} acts by interchanging the coordinates.
Thus {{< katex >}}$\tilde{\mathcal{B}}(T)${{< /katex >}} is the space of unordered pairs of points
in the Bowditch boundary of {{< katex >}}$T${{< /katex >}}.
The diagonal action of {{< katex >}}$F${{< /katex >}} on {{< katex >}}$\partial T${{< /katex >}} extends to an action on {{< katex >}}$\tilde{\mathcal{B}}(T)${{< /katex >}}.
A *lamination* is an {{< katex >}}$F${{< /katex >}}-invariant closed subset of {{< katex >}}$\tilde{\mathcal{B}}(T)${{< /katex >}}.

Given a point {{< katex >}}$\xi \in \partial_\infty T${{< /katex >}}, there is a lamination {{< katex >}}$\Lambda(\xi)${{< /katex >}}
called the *limit set* of {{< katex >}}$\xi${{< /katex >}} defined as follows.
A point {{< katex >}}$(\alpha,\omega) \in \tilde{\mathcal{B}}(T)${{< /katex >}} belongs to {{< katex >}}$\Lambda(\xi)${{< /katex >}}
if (possibly after swapping {{< katex >}}$\alpha${{< /katex >}} and {{< katex >}}$\omega${{< /katex >}}),
there is a sequence {{< katex >}}$\{g_n\}${{< /katex >}} of elements of {{< katex >}}$F${{< /katex >}}
such that the sequence {{< katex >}}$\{g_n.p\}${{< /katex >}} converges to {{< katex >}}$\alpha${{< /katex >}}
and the sequence {{< katex >}}$\{g_n.\xi\}${{< /katex >}} converges to {{< katex >}}$\omega${{< /katex >}}.

[Boundaries1]: {{< ref "boundaries-of-free-splittings.md" >}}
[CHL]: https://projecteuclid.org/journals/illinois-journal-of-mathematics/volume-51/issue-3/Non-unique-ergodicity-observers-topology-and-the-dual-algebraic-lamination/10.1215/ijm/1258131109.full
