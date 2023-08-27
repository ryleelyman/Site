---
title: "Boundaries of Free Splittings"
date: 2021-07-25T14:57:02-04:00
math: true
---
The other day on Twitter I asked whether it might be the case that a non-proper
hyperbolic metric space might still have locally compact Gromov boundary.
I was particularly interested in the case of a simplicial tree
equipped with the path metric where each edge has length {{< katex >}}$1${{< /katex >}}
with some vertices of infinite valence.
The answer in this case is *no.*
Instead, the boundary of such a tree is homeomorphic to the *Baire space* {{< katex >}}$\mathbb{N}^\mathbb{N}${{< /katex >}}.
In this post I'll talk through why this is the case.
There is also a notion of a *Bowditch boundary* for a tree with vertices of infinite valence.
I'd like to show that the Bowditch boundary of such a tree is a Cantor set.

The trees we are interested in are Bass--Serre trees associated to free splittings of countable groups
with the property that some vertex group is infinite.
Let {{< katex >}}$T${{< /katex >}} be such a tree.
Then {{< katex >}}$T${{< /katex >}} admits a cocompact group action, has countably infinitely many edges
and has a vertex of countably infinite valence.
We can give {{< katex >}}$T${{< /katex >}} the structure of a metric space by considering the path metric
where each edge is assigned length {{< katex >}}$1${{< /katex >}}.
The "identity map" from {{< katex >}}$T${{< /katex >}} as a simplicial complex to {{< katex >}}$T${{< /katex >}} as a metric space
is continuous, but its inverse is not.
The property that {{< katex >}}$T${{< /katex >}} admits a cocompact group action
implies that any geodesic ray (isometric embedding of {{< katex >}}$\mathbb{R}_{\ge 0}${{< /katex >}})
passes through infinitely many vertices of infinite valence.

## The Gromov boundary of {{< katex >}}$T${{< /katex >}}
Fix a point {{< katex >}}$p${{< /katex >}} in {{< katex >}}$T${{< /katex >}}.
The Gromov boundary {{< katex >}}$\partial_\infty T${{< /katex >}} of {{< katex >}}$T${{< /katex >}} is the set of geodesic rays in {{< katex >}}$T${{< /katex >}} beginning at {{< katex >}}$p${{< /katex >}}.
(It turns out that the Gromov boundary is independent of the choice of basepoint.)
Let {{< katex >}}$J${{< /katex >}} be a (finite) geodesic segment in {{< katex >}}$T${{< /katex >}} beginning at {{< katex >}}$p${{< /katex >}}.
A basic open set {{< katex >}}$U_J${{< /katex >}} for the topology on {{< katex >}}$\partial_\infty T${{< /katex >}}
is given by the set of geodesic rays that contain {{< katex >}}$J${{< /katex >}} as a subpath.
I'll leave it to show you that the intersection of basic open sets is either empty or another basic open set.

## The Baire space
The Baire space {{< katex >}}$\mathbb{N}^\mathbb{N}${{< /katex >}} is homeomorphic to the irrational numbers.
A theorem of Alexandrov and Urysohn says that
the Baire space is characterized up to homeomorphism by the following properties.
It is a (nonempty) *Polish space,* meaning it is *separable* and *completely metrizable.*
It is *zero-dimensional,* meaning it has a basis of clopen sets.
Finally, every compact subset has empty interior.

To show that the Gromov boundary of {{< katex >}}$T${{< /katex >}} is homeomorphic to the Baire space,
we will verify these properties.
It is completely metrizable by general theory.
There are countably infinitely many finite geodesic segments in {{< katex >}}$T${{< /katex >}} beginning at {{< katex >}}$p${{< /katex >}}
(one for each vertex of {{< katex >}}$T${{< /katex >}}),
so {{< katex >}}$\partial_\infty T${{< /katex >}} is second countable, and in particular separable.
A basic closed set of {{< katex >}}$\partial_\infty T${{< /katex >}} is given by the set of those geodesic rays
that do *not* contain a geodesic segment {{< katex >}}$J${{< /katex >}} as a subpath.
It's not hard to find a collection of geodesic segments such that any geodesic ray
that does not contain any of these geodesic segments as a subpath must contain {{< katex >}}$J${{< /katex >}} as a subpath.
I'll leave the details to you.
Therefore {{< katex >}}$\partial_\infty T${{< /katex >}} has a basis of clopen sets.
To show that every compact subset has empty interior,
it suffices to show that our basic clopen sets are never compact.
To see this, continue {{< katex >}}$J${{< /katex >}} until you reach a vertex of infinite valence,
giving us a new finite geodesic segment {{< katex >}}$J'${{< /katex >}}.
Write {{< katex >}}$U_J \setminus U_{J'}${{< /katex >}} as a finite disjoint union of basic open sets,
and {{< katex >}}$U_{J'}${{< /katex >}} as the infinite disjoint union of the {{< katex >}}$U_{J''}${{< /katex >}},
where {{< katex >}}$J''${{< /katex >}} is one edge longer than {{< katex >}}$J'${{< /katex >}}.
The result is an open cover of {{< katex >}}$U_J${{< /katex >}} with no finite subcover.

## The Bowditch boundary
The *Bowditch boundary* of {{< katex >}}$T${{< /katex >}} is the set {{< katex >}}$\partial T = \partial_\infty T \cup V_\infty(T)${{< /katex >}},
where {{< katex >}}$V_\infty(T)${{< /katex >}} denotes the set of vertices of {{< katex >}}$T${{< /katex >}} with infinite valence.
The Bowditch boundary carries with it the *observer's topology,* which we now describe.
Given two points {{< katex >}}$q${{< /katex >}} and {{< katex >}}$r${{< /katex >}} in {{< katex >}}$T${{< /katex >}}, the *direction of {{< katex >}}$r${{< /katex >}} at {{< katex >}}$q${{< /katex >}}* is the component of {{< katex >}}$T\setminus \{q\}${{< /katex >}}
that contains {{< katex >}}$r${{< /katex >}}.
We continue to think of points of {{< katex >}}$\partial_\infty T${{< /katex >}} as geodesic rays based at {{< katex >}}$p${{< /katex >}};
for convenience suppose that {{< katex >}}$p${{< /katex >}} is either in the interior of an edge or a vertex with finite valence.
We may additionally think of a point {{< katex >}}$v \in V_\infty(T)${{< /katex >}}
as being represented by the geodesic segment from {{< katex >}}$p${{< /katex >}} to {{< katex >}}$v${{< /katex >}}.
We say that a point of {{< katex >}}$\partial T${{< /katex >}} belongs to a direction if the
corresponding geodesic starting at {{< katex >}}$p${{< /katex >}} is contained in the direction.
The set of directions in {{< katex >}}$T${{< /katex >}} forms a subbasis for the observer's topology on {{< katex >}}$\partial T${{< /katex >}};
thus a basic open set is given by a finite intersection of directions of {{< katex >}}$T${{< /katex >}}.
Put another way, a basic open set is given by the set of those geodesics based at {{< katex >}}$p${{< /katex >}}
that avoid a given finite subset of {{< katex >}}$T${{< /katex >}}.
We can always take this finite set to be a set of vertices or midpoints of edges,
so the observer's topology is second countable.

We'd like to show that the Bowditch boundary of {{< katex >}}$T${{< /katex >}} is a Cantor set.
It is clear that {{< katex >}}$\partial T${{< /katex >}} has no isolated points.
It is compact and Hausdorff by general theory.
Thus it suffices to show that our basis elements are clopen.
We will show that our open basic open sets are compact.
Indeed, let {{< katex >}}$U${{< /katex >}} be a basic open set determined by the finite set of points {{< katex >}}$\{z_1,\dotsc,z_n\} \subset T${{< /katex >}},
and let {{< katex >}}$\{U_{\alpha}\}_{\alpha\in I}${{< /katex >}} be an open cover of {{< katex >}}$U${{< /katex >}} by basic open sets,
which are determined by finite sets of points containing {{< katex >}}$\{z_1,\dotsc, z_n\}${{< /katex >}} as a subset.
Take {{< katex >}}$U_\alpha \in I${{< /katex >}}.
Then there are finitely many points {{< katex >}}$z_{n+1},\dotsc,z_{n+k}${{< /katex >}} determining {{< katex >}}$U_\alpha${{< /katex >}} and contained in {{< katex >}}$U${{< /katex >}}.
For each {{< katex >}}$z_{n+i}${{< /katex >}} for {{< katex >}}$i${{< /katex >}} satisfying {{< katex >}}$1 \le i \le k${{< /katex >}}, we can find {{< katex >}}$\alpha_i \in I${{< /katex >}}
such that {{< katex >}}$U_{\alpha_i}${{< /katex >}} contains {{< katex >}}$z_{n+i}${{< /katex >}}.
Then {{< katex >}}$U_\alpha,U_{\alpha_1},\dotsc,U_{\alpha_k}${{< /katex >}} is a finite subcover of {{< katex >}}$U${{< /katex >}}.

## A parallel example
Let the Cantor space be {{< katex >}}$\{0,1\}^{\mathbb{N}}${{< /katex >}}.
The subspace of sequences which are eventually constant is countable and dense.
The subspace of sequences which are *not* eventually constant is
[homeomorphic to the Baire space](https://math.stackexchange.com/a/254381/447318).
This is more or less what is happening here: we add countably many points to
our non-locally compact Gromov boundary to get the compact Bowditch boundary.
