---
layout: post
math: true
---
Let $$F$$ be a group.
A *free splitting* of $$F$$ is a simplicial tree $$T$$
equipped with an $$F$$-action
such that edge stabilizers are trivial.
I've been thinking a lot about free splittings;
here are some of my musings.
There isn't really a punch line here,
but since it was clarifying to write this, I may as well post it.

We are interested in free splittings where there are finitely many orbits of edges
and some vertex has infinite stabilizer.
In this case, Bass–Serre theory shows that $$F$$
is a free product of the form

$$F = A_1*\cdots*A_n*F_k$$

where the $$A_i$$ are countable groups
(at least one of which is infinite)
and $$F_k$$ is a free group of finite rank $$k$$.

## The Gromov boundary of $$T$$

Fix a basepoint $$p \in T$$.
A *geodesic ray* in $$T$$ based at $$p$$
is a proper embedding $$\xi\colon [0,\infty) \to T$$
such that $$\xi(0) = p$$.
We are really interested in the image of $$\xi$$ more than the map.
Similarly we have *geodesics;* embeddings $$[0,1] \to T$$.
Every path in $$T$$ is homotopic rel endpoints to a unique geodesic or to a constant map.
Let $$\partial_\infty T$$ denote the set of geodesic rays in $$T$$ based at $$p$$.
This is the *Gromov boundary* of $$T$$.
We may topologize $$T \cup \partial_\infty T$$ by giving $$T$$ the usual topology
and defining basic open neighborhoods of boundary points in the following way.
Given a boundary point $$\xi$$, the basic open neighborhood is determined by a finite subpath
$$\gamma$$ of the ray $$\xi$$;
the basic open set $$N(\gamma)$$ consists of those points $$x \in T \cup \partial_\infty T$$
such that the geodesic from $$p$$ to $$x$$ contains $$\gamma$$.
In [July][Boundaries1], we showed that in our situation,
if all the groups $$A_i$$ are countable and one is countably infinite,
then the Gromov boundary of $$T$$ is homeomorphic (in the subspace topology) to the Baire space.

## The observer's topology

We may give $$T \cup \partial_\infty T$$ a different topology
that makes it into a compact space:
this is the *observer's topology,* coined by [Coulbois, Hilion and Lustig][CHL].
Let $$x \in T$$ be a point.
A *half-tree* based at $$x$$ is a component of $$T \setminus \{x\}$$.
A subbasis for the observer's topology on $$T \cup \partial_\infty T$$ 
is given by the set of half-trees;
where we say a boundary point $$\xi \in \partial_\infty T$$ belongs to a half-tree
if the corresponding geodesic ray has infinite intersection with the half-tree.
In our situation, where the groups $$A_i$$ are countable,
the tree $$T$$ has countably many edges, so has a countable dense subset.
Since every point supports at most countably many half-trees,
it follows that the observer's topology on $$T \cup \partial_\infty T$$ is second countable.
Thus it makes sense to talk about the topology in terms of convergent sequences:
a sequence $$\{x_n\} \in T \cup \partial_\infty T$$ converges to a point $$x$$
if for every point $$y \ne x$$,
the points $$x_n$$ belong to the same half-tree at $$y$$ as $$x$$ for $$n$$ sufficiently large.

Coulbois, Hilion and Lustig show that $$T \cup \partial_\infty T$$ is compact in the observer's topology.
Here is their argument:
suppose $$\{x_n\}$$ is a sequence,
and let $$\{U_i\}$$ be a countable set of half-trees 
generating the topology on $$T \cup \partial_\infty T$$
For each $$U_i$$, we may, after passing to a subsequence,
assume that $$x_n$$ either belongs to $$U_i$$ or not for $$n$$ large.
Now note that the intersection of (the images of) two (distinct)
geodesics or geodesic rays based at $$p$$
is either a point or a geodesic.
Let $$\gamma_n$$ denote the geodesic or geodesic ray from $$p$$ to $$x_n$$,
and consider the geodesic

$$I_k = \bigcap_{m \ge k} \gamma_m.$$

Observe that $$I_k \subset I_{k+1}$$, so

$$\overline{\bigcup_k I_k}$$

is a geodesic or geodesic ray; let its endpoint be $$x$$.
We will show that our subsequence $$\{x_n\}$$ converges to $$x$$.
Suppose for $$n \ge N$$ we have that $$x_n \notin U_i$$.
Then for any finite collection of such $$x_n$$,
the subtree spanned by the collection is entirely outside $$U_i$$,
since the (closed) complement of a half-tree is convex.
The nearest point to $$p$$ belongs to this spanning subtree,
so inductively this shows that the endpoint of $$I_k$$ is outside $$U_i$$ for large $$k$$.
It follows that $$x \notin U_i$$. 
Therefore if $$x \in U_i$$, then infinitely many,
and thus all but finitely many of the $$x_n$$ belong to $$U_i$$,
showing that the sequence $$\{x_n\}$$ converges to $$x$$.

Next we would like to show that the topology induced on $$\partial_\infty T$$
agrees with the one above.
Suppose $$\{x_n\}$$ converges to $$\xi \in \partial_\infty T$$ in the observer's topology,
so for any point $$y \in T$$,
the points $$x_n$$ belong to the same half-tree at $$y$$ as $$\xi$$ for $$n$$ large.
Taking the points $$y$$ to be on the geodesic ray $$\xi$$
shows that the geodesic or geodesic ray from $$p$$ to $$x_n$$
must contain any finite subpath of $$\xi$$ for $$n$$ large.
If conversely the geodesic or geodesic ray from $$p$$ to $$x_n$$
contains any finite subpath of $$\xi$$ for $$n$$ sufficiently large,
then if the intersection of the ray $$\xi$$ with a given half-tree is infinite,
we may take a finite subpath $$\gamma$$ so large that it ends inside the half-tree.
If the geodesic or geodesic ray from $$p$$ to $$x_n$$ contains $$\gamma$$,
then since $$T$$ is a tree, we conclude that $$x_n$$ belongs to the half-tree.

## The Bowditch Boundary of $$T$$

It's not hard to see that if $$x \in T$$ is a point of finite valence,
(i.e. either a vertex of finite valence or a point in the interior of an edge)
then there is a basic open set containing $$x$$ that contains only points of finite valence.
If we write $$V_\infty(T)$$ for the set of vertices of infinite valence,
this argument shows that $$\partial T = \partial_\infty T \cup V_\infty(T)$$
is closed in the observer's topology,
hence it is compact.
This is the *Bowditch boundary* of $$T$$.
In fact, we showed in [July][Boundaries1] that $$\partial T$$ is a Cantor set;
one might think of the points $$V_\infty(T)$$ as being akin to the rational points
of the standard middle-thirds Cantor set.

## Laminations

Consider the space

$$\tilde{\mathcal{B}}(T) = ((\partial T \times \partial T)\setminus \Delta )/ \mathbb{Z}/2\mathbb{Z}$$

where $$\Delta$$ is the diagonal and $$\mathbb{Z}/2\mathbb{Z}$$ acts by interchanging the coordinates.
Thus $$\tilde{\mathcal{B}}(T)$$ is the space of unordered pairs of points
in the Bowditch boundary of $$T$$.
The diagonal action of $$F$$ on $$\partial T$$ extends to an action on $$\tilde{\mathcal{B}}(T)$$.
A *lamination* is an $$F$$-invariant closed subset of $$\tilde{\mathcal{B}}(T)$$.

Given a point $$\xi \in \partial_\infty T$$, there is a lamination $$\Lambda(\xi)$$
called the *limit set* of $$\xi$$ defined as follows.
A point $$(\alpha,\omega) \in \tilde{\mathcal{B}}(T)$$ belongs to $$\Lambda(\xi)$$
if (possibly after swapping $$\alpha$$ and $$\omega$$),
there is a sequence $$\{g_n\}$$ of elements of $$F$$
such that the sequence $$\{g_n.p\}$$ converges to $$\alpha$$
and the sequence $$\{g_n.\xi\}$$ converges to $$\omega$$.

[Boundaries1]: {{ "blog/2021-07-25-Boundaries-of-free-splittings.html" | relative_url }}
[CHL]: https://projecteuclid.org/journals/illinois-journal-of-mathematics/volume-51/issue-3/Non-unique-ergodicity-observers-topology-and-the-dual-algebraic-lamination/10.1215/ijm/1258131109.full
