---
layout: post
math: true
---
In an [earlier post][ideal edges] we introduced the concept of an *ideal edge*
in a graph of groups and described how to *blow up* ideal edges
to construct new graphs of groups.
To prove that (the reduced spine of) Outer Space for a virtually free group
is contractible, [Krstić and Vogtmann][equivariant outer space]
define what is essentially a combinatorial analogue of a non-singular Morse function
on Outer Space and show that for well-chosen function,
the set of minimal vertices of the complex is actually the star of a single reduced marked graph of groups,
which is contractible.
A key tool to that end is the *star graph,*
and the purpose of this post is to describe the star graph (for conjugacy classes)
in a virtually free group and describe its usefulness.

## The reduced spine of Outer Space

Before we describe the star graph, let's define the complex we're working with.
Given a virtually (non-abelian, to keep things interesting) free group $$F$$,
we'll call the reduced spine of Outer Space $$L(F)$$.
In tree language, a vertex of $$L(F)$$
is an action of $$F$$ on a simplicial tree $$T$$ with finite stabilizers and finite quotient
with the property that every edge of $$T$$ is *surviving,* see [the post on shelters][shelters]
for a definition.
Two tree actions $$T$$ and $$T'$$ are *equivalent* if there is an equivariant homeomorphism between them.
The set of equivalence classes is partially ordered under *forest collapse,*
and the *reduced spine of Outer Space* is the geometric realization of this poset.

In graphs of groups language, 
a vertex of $$L(F)$$ is a finite graph of finite groups $$\mathcal{G}$$
which is a union of *shelters*
together with a *marking,* which we can think of as an identification of $$\pi_1(\mathcal{G})$$ with $$F$$,
well-defined up to inner automorphism,
or as a *homotopy equivalence* in the sense of [my paper][traintracks]
$$\sigma\colon \mathbb{G} \to \mathcal{G}$$
from a fixed graph of finite groups $$\mathbb{G}$$.
Two marked graphs of groups $$\tau = (\mathcal{G},\sigma)$$ and $$\tau' = (\mathcal{G}',\sigma')$$
are *equivalent* if there is an isomorphism of graphs of groups
$$h \colon \mathcal{G} \to \mathcal{G}'$$ such that $$h\sigma$$ is homotopic to $$\sigma'$$.
There is also a notion of *forest collapse* in graphs of groups,
which partially orders the set of equivalence classes of marked graphs of groups.
A marked graph of groups $$\tau = (\mathcal{G},\sigma)$$ is *reduced* if it is minimal in this partial order.
The complex $$L(F)$$ is the geometric realization of this poset.
We will adopt the graphs of groups language in this post.

## The norm

Let $$\tau = (\mathcal{G},\sigma)$$ be a marked graph of groups in $$L(F)$$,
and let $$W$$ be a finite set of infinite order elements of $$F$$.
These elements are hyperbolic in some and hence every tree action in $$L(F)$$,
so we may measure $$\ell(w)$$, their hyperbolic translation length,
and we define a *norm* on $$\tau$$ as

$$ \|\tau\| = \sum_{w \in W} \ell(w). $$

We can represent each conjugacy class $$\sigma_\sharp(w)$$ in $$\pi_1(\mathcal{G})$$
as a cyclically reduced graph-of-groups *edge path*

$$ \gamma_w = g_0e_1g_1\ldots e_kg_k. $$

We have $$\ell(w) = k$$, the number of edges in $$\gamma_w$$.
Recall that for each vertex $$v$$ of $$\mathcal{G}$$ we have the set of *directions at $$v$$*

$$ D_v = \coprod_{e\in\operatorname{st}(v)} \mathcal{G}_v/\iota_e(\mathcal{G}_e) \times \{e\}. $$

There is an obvious left action of $$\mathcal{G}_v$$ on $$D_v$$
which descends to an action on the set of pairs of directions at $$v$$.
A *turn* is an orbit under this action.
A turn is *degenerate* if every pair of directions representing it are identical
and is *nondegenerate* otherwise.
The vertex group elements of the path $$\gamma_w$$ are not quite well-defined
if the edge groups of $$\mathcal{G}$$ are nontrivial,
but the *turns* $$[\{(\iota_{\bar e_i}(\mathcal{G}_{\bar e_i}),\bar e_i),
(g_i\iota_{e_{i+1}}(\mathcal{G}_{e_{i+1}}),e_{i+1})\}]$$
for $$1 \le i \le k-1$$ and $$[\{(g_k^{-1}\iota_{\bar e_k}(\mathcal{G}_{e_k}),e_k),
(g_0\iota_{e_1}(\mathcal{G}_{e_1}),e_1)\}]$$
are well-defined.
We say that $$\gamma_w$$ *crosses* these turns, which are nondegenerate
because $$\gamma_w$$ is cyclically reduced.

## The star graph

We define the *star graph* of a marked graph of groups $$\tau = (\mathcal{G},\sigma)$$
with respect to $$W$$.
Its vertex set is the union of the sets $$D_v$$ as $$v$$ varies over the vertices of $$\mathcal{G}$$.
For each turn crossed by some $$\gamma_w$$,
the star graph contains $$|\mathcal{G}_v|$$ edges,
each one connecting a pair of directions representing this turn.
Since the turns crossed by $$\gamma_w$$ are nondegenerate, the star graph contains no loop edges.

![A star graph](/assets/img/stargraph.jpeg)

In the above example we have

$$F = C_4*_{C_2} C_4 * C_3 = \langle s, t, u \mid s^4 = t^4 = u^3 = 1,\ s^2 = t^2 \rangle,$$

and the marked graph of groups $$\tau = (\mathcal{G},\sigma)$$ is the "obvious"
graph of groups presentation of $$F$$.
There are three vertices with vertex groups $$\langle s\rangle$$,
$$\langle t\rangle$$ and $$\langle u\rangle$$.
There are two edges $$a$$ and $$b$$.
The vertex $$v$$ with vertex group $$\langle t\rangle$$ has valence two;
both $$a$$ and $$b$$ are incident to it in the positive orientation.
The edge $$a$$ connects $$v$$ to the vertex with vertex group $$\langle s\rangle$$
and has $$C_2$$ edge group, while $$b$$ has trivial edge group.
The set $$W$$ is the singleton $$\{stu^2t^2\}$$.
The star graph of of $$\tau$$ with respect to $$W$$
has eleven vertices.
The component corresponding to $$\langle s\rangle$$ has two vertices,
and there are four edges corresponding to the turns in the orbit 
$$[\{(\langle s^2\rangle,\bar a),(s\langle s^2\rangle,\bar a)\}]$$.
The component corresponding to $$\langle u\rangle$$ has three vertices,
and there are three edges corresponding to the turns in the orbit
$$[\{(1,\bar b),(u^2,\bar b)\}]$$.
The component corresponding to the vertex $$v$$ has six vertices,
two for directions with underlying oriented edge $$a$$ and two with underlying oriented edge $$b$$.
This subgraph of the star graph is complete bipartite
corresponding to the turns in the orbits
$$[\{(\langle t^2\rangle,a),(t,b)\}]$$ and $$[\{(1,b),(\langle t^2\rangle,a)\}]$$.

We can compute the norm of $$\tau$$ from the star graph by summing up

$$ \|\tau\| = \frac{1}{2}\sum_{v \in \mathcal{G}}\sum_{d \in D_v} 
\frac{\operatorname{valence}(d)}{|\mathcal{G}_v|}.$$

So in this example we see that we have $$\|\tau\| = 4$$.

## Dot product and absolute value

Following Culler and Vogtmann,
given subsets $$S$$ and $$T$$ of the vertex set of a graph,
define the *dot product* $$S\cdot T$$ to be the number of (unoriented) edges in the graph
with one vertex in $$S$$ and the other in $$T$$.
The *absolute value* $$|S|$$ of $$S$$  is the dot product of $$S$$ with its complement.
An [*ideal edge*][ideal edges] $$\alpha$$ is in particular a subset of the vertex set of the star graph,
so we may compute $$|\alpha|$$.
If $$\alpha' = g.\alpha$$ under the action of $$\mathcal{G}_v$$ on $$D_v$$,
then $$|\alpha| = |\alpha'|$$.
Similarly a direction $$d \in D_v$$ is a singleton subset of the vertex set of the star graph
and we may compute $$|d| = |\{d\}|$$.
If $$d' = g.d$$, then $$|d| = |d'|$$.
Put another way, the absolute value of $$d$$ is a property of the underlying oriented edge $$e$$
and we may sometimes write $$|e|$$ for $$|d|$$.

In the above example, the ideal edge $$\alpha = \{(\langle t^2\rangle,a),(t,b),(t^3,b)\}$$
has absolute value $$|\alpha| = 4$$,
while the direction $$d = (\langle t^2\rangle,a)$$ also has absolute value $$4$$.
Both $$d$$ and $$\alpha$$ have edge group isomorphic to $$C_2$$,
so we have

$$\frac{|d|}{|\mathcal{G}_a|} = \frac{|\alpha|}{|\mathcal{G}_\alpha|} = 2.$$

If we blow up the ideal edge $$\alpha$$ obtaining $$\tau^\alpha = (\mathcal{G}^\alpha,\sigma^\alpha)$$,
the original $$\gamma_w$$ was $$as\bar atb u^2\bar b t^2$$ and
the new $$\gamma_w$$ is $$as\bar ab tu^2t^{-1}\bar b \bar\alpha t\alpha t^2$$,
which has $$2$$ more edges.
If we then collapse the collapsible edge $$a$$ corresponding to the direction $$d \in D(\alpha)$$
to obtain $$\tau^\alpha_a$$,
the new $$\gamma_w$$ is $$sbtu^2t^{-1}\bar b\bar\alpha t\alpha s^2$$,
which has $$2$$ fewer edges.

![The marked graphs of groups obtained by blowing up and then collapsing](/assets/img/blowupanddown.jpeg)

This illustrates a general principal:

**Proposition** (Krstić–Vogtmann). If $$\Phi = \{\alpha_1,\ldots,\alpha_k\}$$
is a set of pairwise compatible ideal edges in a reduced marked graph of groups $$\tau = (\mathcal{G},\sigma)$$
and $$\{e_1,\ldots,e_k\}$$ are a set of oriented edges in $$\mathcal{G}$$ which form a forest in
$$\tau^{\alpha_1,\ldots,\alpha_k}$$, we have

$$ \|\tau^{\alpha_1,\ldots,\alpha_k}_{e_1,\ldots,e_k}\| = \|\tau\| 
+ \sum_{i=1}^k \frac{|\alpha_i|}{|\mathcal{G}_{\alpha_i}|} - \sum_{i=1}^k \frac{|e_i|}{|\mathcal{G}_{e_i}|}.$$

## Wrapping up

The *star* of a reduced marked graph of groups $$\tau$$ is the set of marked graphs of groups $$\tau'$$
which collapse onto $$\tau$$.
The *ball of radius $$r$$* is the union of the stars of reduced marked graphs of groups $$\tau$$
with $$\|\tau\| \le r$$.
What Krstić–Vogtmann show is that 
as long as the ball of radius $$r' < r$$ is nonempty,
the ball of radius $$r$$ deformation retracts onto the ball of radius $$r'$$.
They show that for well-chosen $$W$$, there is a single reduced marked graph of groups
of minimal norm, thus proving that $$L$$ is contractible.
To do both of these steps, they make extensive use of the star graph to analyze
the effect of blowing up and collapsing edges in marked graphs of groups.

[shelters]: {% link _posts/2022-03-26-Shelters-in-graphs-of-groups.md %}
[ideal edges]: {% link _posts/2022-03-27-Ideal-edges.md %}
[equivariant outer space]: https://www.researchgate.net/publication/226534036_Equivariant_outer_space_and_automorphisms_of_free-by-finite_groups/link/5762c70508aee61395bef5dc/download
[traintracks]: https://arxiv.org/abs/2102.02848
