---
layout: post
math: true
---
The other day on Twitter I asked whether it might be the case that a non-proper
hyperbolic metric space might still have locally compact Gromov boundary.
I was particularly interested in the case of a simplicial tree
equipped with the path metric where each edge has length $$1$$
with some vertices of infinite valence.
The answer in this case is *no.*
Instead, the boundary of such a tree is homeomorphic to the *Baire space* $$\mathbb{N}^\mathbb{N}$$.
In this post I'll talk through why this is the case.
There is also a notion of a *Bowditch boundary* for a tree with vertices of infinite valence.
I'd like to show that the Bowditch boundary of such a tree is a Cantor set.

The trees we are interested in are Bass--Serre trees associated to free splittings of countable groups
with the property that some vertex group is infinite.
Let $$T$$ be such a tree.
Then $$T$$ admits a cocompact group action, has countably infinitely many edges
and has a vertex of countably infinite valence.
We can give $$T$$ the structure of a metric space by considering the path metric
where each edge is assigned length $$1$$.
The "identity map" from $$T$$ as a simplicial complex to $$T$$ as a metric space
is continuous, but its inverse is not.
The property that $$T$$ admits a cocompact group action
implies that any geodesic ray (isometric embedding of $$\mathbb{R}_{\ge 0}$$)
passes through infinitely many vertices of infinite valence.

## The Gromov boundary of $$T$$
Fix a point $$p$$ in $$T$$.
The Gromov boundary $$\partial_\infty T$$ of $$T$$ is the set of geodesic rays in $$T$$ beginning at $$p$$.
(It turns out that the Gromov boundary is independent of the choice of basepoint.)
Let $$J$$ be a (finite) geodesic segment in $$T$$ beginning at $$p$$.
A basic open set $$U_J$$ for the topology on $$\partial_\infty T$$
is given by the set of geodesic rays that contain $$J$$ as a subpath.
I'll leave it to show you that the intersection of basic open sets is either empty or another basic open set.

## The Baire space
The Baire space $$\mathbb{N}^\mathbb{N}$$ is homeomorphic to the irrational numbers.
A theorem of Alexandrov and Urysohn says that
the Baire space is characterized up to homeomorphism by the following properties.
It is a (nonempty) *Polish space,* meaning it is *separable* and *completely metrizable.*
It is *zero-dimensional,* meaning it has a basis of clopen sets.
Finally, every compact subset has empty interior.

To show that the Gromov boundary of $$T$$ is homeomorphic to the Baire space,
we will verify these properties.
It is completely metrizable by general theory.
There are countably infinitely many finite geodesic segments in $$T$$ beginning at $$p$$
(one for each vertex of $$T$$),
so $$\partial_\infty T$$ is second countable, and in particular separable.
A basic closed set of $$\partial_\infty T$$ is given by the set of those geodesic rays
that do *not* contain a geodesic segment $$J$$ as a subpath.
It's not hard to find a collection of geodesic segments such that any geodesic ray
that does not contain any of these geodesic segments as a subpath must contain $$J$$ as a subpath.
I'll leave the details to you.
Therefore $$\partial_\infty T$$ has a basis of clopen sets.
To show that every compact subset has empty interior,
it suffices to show that our basic clopen sets are never compact.
To see this, continue $$J$$ until you reach a vertex of infinite valence,
giving us a new finite geodesic segment $$J'$$.
Write $$U_J \setminus U_{J'}$$ as a finite disjoint union of basic open sets,
and $$U_{J'}$$ as the infinite disjoint union of the $$U_{J''}$$,
where $$J''$$ is one edge longer than $$J'$$.
The result is an open cover of $$U_J$$ with no finite subcover.

## The Bowditch boundary
The *Bowditch boundary* of $$T$$ is the set $$\partial T = \partial_\infty T \cup V_\infty(T)$$,
where $$V_\infty(T)$$ denotes the set of vertices of $$T$$ with infinite valence.
The Bowditch boundary carries with it the *observer's topology,* which we now describe.
Given two points $$q$$ and $$r$$ in $$T$$, the *direction of $$r$$ at $$q$$* is the component of $$T\setminus \{q\}$$
that contains $$r$$.
We continue to think of points of $$\partial_\infty T$$ as geodesic rays based at $$p$$;
for convenience suppose that $$p$$ is either in the interior of an edge or a vertex with finite valence.
We may additionally think of a point $$v \in V_\infty(T)$$
as being represented by the geodesic segment from $$p$$ to $$v$$.
We say that a point of $$\partial T$$ belongs to a direction if the
corresponding geodesic starting at $$p$$ is contained in the direction.
The set of directions in $$T$$ forms a subbasis for the observer's topology on $$\partial T$$;
thus a basic open set is given by a finite intersection of directions of $$T$$.
Put another way, a basic open set is given by the set of those geodesics based at $$p$$
that avoid a given finite subset of $$T$$.
We can always take this finite set to be a set of vertices or midpoints of edges,
so the observer's topology is second countable.

We'd like to show that the Bowditch boundary of $$T$$ is a Cantor set.
It is clear that $$\partial T$$ has no isolated points.
It is compact and Hausdorff by general theory.
Thus it suffices to show that our basis elements are clopen.
We will show that our open basic open sets are compact.
Indeed, let $$U$$ be a basic open set determined by the finite set of points $$\{z_1,\dotsc,z_n\} \subset T$$,
and let $$\{U_{\alpha}\}_{\alpha\in I}$$ be an open cover of $$U$$ by basic open sets,
which are determined by finite sets of points containing $$\{z_1,\dotsc, z_n\}$$ as a subset.
Take $$U_\alpha \in I$$.
Then there are finitely many points $$z_{n+1},\dotsc,z_{n+k}$$ determining $$U_\alpha$$ and contained in $$U$$.
For each $$z_{n+i}$$ for $$i$$ satisfying $$1 \le i \le k$$, we can find $$\alpha_i \in I$$
such that $$U_{\alpha_i}$$ contains $$z_{n+i}$$.
Then $$U_\alpha,U_{\alpha_1},\dotsc,U_{\alpha_k}$$ is a finite subcover of $$U$$.

## A parallel example
Let the Cantor space be $$\{0,1\}^{\mathbb{N}}$$.
The subspace of sequences which are eventually constant is countable and dense.
The subspace of sequences which are *not* eventually constant is
[homeomorphic to the Baire space](https://math.stackexchange.com/a/254381/447318).
This is more or less what is happening here: we add countably many points to
our non-locally compact Gromov boundary to get the compact Bowditch boundary.
