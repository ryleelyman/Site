---
title: "Ideal Edges"
date: 2022-03-27T15:11:03-04:00
math: true
---
Let's once again fix a group {{< katex >}}$G${{< /katex >}} that acts cocompactly on a tree {{< katex >}}$T${{< /katex >}}.
In the [previous post][shelters] we defined what it meant for an edge of {{< katex >}}$T${{< /katex >}} 
to be *surviving* or *collapsible.*
Collapsing orbits of collapsible edges in {{< katex >}}$T${{< /katex >}} yields
a new tree {{< katex >}}$T'${{< /katex >}} which we say is obtained from {{< katex >}}$T${{< /katex >}} by forest collapse.
Two trees {{< katex >}}$T${{< /katex >}} and {{< katex >}}$T'${{< /katex >}} are in the same *deformation space*
if there are {{< katex >}}$G${{< /katex >}}-equivariant maps {{< katex >}}$T \to T'${{< /katex >}} and {{< katex >}}$T' \to T${{< /katex >}}.
The set of {{< katex >}}$G${{< /katex >}}-equivariant homeomorphism classes of trees in the same deformation space as {{< katex >}}$T${{< /katex >}}
all of whose edges are surviving
is partially ordered under the operation of forest collapse,
and this partial order contains minimal elements, which are *reduced* trees.
To study this poset, or its geometric realization {{< katex >}}$L_T(G)${{< /katex >}},
it would be convenient to understand all trees collapsing onto a given reduced tree.
This is captured in the idea of an *ideal edge,*
which I'd like to describe in this post.
The idea of an ideal edge goes back to Culler and Vogtmann's
[original paper][outer space] on Outer Space;
the treatment here is adapted from a paper of [Krstić and Vogtmann][equivariant outer space].

Again we will work in the quotient graph of groups {{< katex >}}$\mathcal{G}${{< /katex >}},
the construction of which we described in the [previous post][shelters].
We assume that {{< katex >}}$\mathcal{G}${{< /katex >}} is finite and connected,
and that if a vertex {{< katex >}}$v${{< /katex >}} has valence less than 3,
then at least one of the edge-to-vertex group inclusions 
{{< katex >}}$\iota_e\colon\mathcal{G}_e \to \mathcal{G}_v${{< /katex >}} is not surjective.
In tree language this says that {{< katex >}}$T${{< /katex >}} is minimal and has no subdivision vertices.
The graph of groups {{< katex >}}$\mathcal{G}${{< /katex >}} is *marked.*
If we fix a tree {{< katex >}}$T${{< /katex >}} in the deformation space
and identify {{< katex >}}$G${{< /katex >}} with the fundamental group of its quotient graph of groups {{< katex >}}$\mathbb{G}${{< /katex >}},
we may think of the marking as a *homotopy equivalence* in the sense of [my paper][traintracks]
{{< katex >}}$\sigma\colon \mathbb{G} \to \mathcal{G}${{< /katex >}}.

## Directions
Let {{< katex >}}$v${{< /katex >}} be a vertex of {{< katex >}}$\mathcal{G}${{< /katex >}}.
Let {{< katex >}}$\operatorname{st}(v)${{< /katex >}} be the set of oriented edges of {{< katex >}}$\mathcal{G}${{< /katex >}} 
with initial vertex {{< katex >}}$v${{< /katex >}}.
The set of *directions* at {{< katex >}}$v${{< /katex >}}, denoted {{< katex >}}$D_v${{< /katex >}}, is the set

{{< katex >}}$ \coprod_{e \in \operatorname{st}(v)} \mathcal{G}_v/\iota_e(\mathcal{G}_e) \times \{e\}. ${{< /katex >}}

The group {{< katex >}}$\mathcal{G}_v${{< /katex >}} acts on {{< katex >}}$D_v${{< /katex >}} on the left,
and under the identification of {{< katex >}}$\mathcal{G}${{< /katex >}} with the quotient graph of groups of {{< katex >}}$T${{< /katex >}},
if {{< katex >}}$\tilde v${{< /katex >}} is a lift of {{< katex >}}$v${{< /katex >}} to {{< katex >}}$T${{< /katex >}},
there is a {{< katex >}}$\mathcal{G}_v${{< /katex >}}-equivariant bijection 
between {{< katex >}}$D_v${{< /katex >}} and the set {{< katex >}}$\operatorname{st}(\tilde v)${{< /katex >}}.

Suppose {{< katex >}}$T'${{< /katex >}} is a tree such that collapsing the orbit of an edge {{< katex >}}$\tilde e${{< /katex >}} incident to {{< katex >}}$v${{< /katex >}}
yields a tree equivariantly homeomorphic to {{< katex >}}$T${{< /katex >}}.
If we suppose that {{< katex >}}$T'${{< /katex >}} is minimal, has no subdivision vertices
and that every edge of {{< katex >}}$T'${{< /katex >}} is surviving,
we can make the following observations:

- {{< katex >}}$\tilde e${{< /katex >}} separates {{< katex >}}$\operatorname{st}(\tilde v)${{< /katex >}} into two components,
each of which has at least two edges, since {{< katex >}}$T'${{< /katex >}} is minimal
and has no subdivision vertices.
- The stabilizer of {{< katex >}}$\tilde e${{< /katex >}} is a subgroup of the stabilizer of {{< katex >}}$\tilde v${{< /katex >}}
and is equal to the stabilizer of the new vertex {{< katex >}}$\tilde w${{< /katex >}}.
If an edge in {{< katex >}}$\operatorname{st}(\tilde v)${{< /katex >}} now has initial vertex {{< katex >}}$\tilde w${{< /katex >}},
so does every edge in its {{< katex >}}$\operatorname{stab}(\tilde e)${{< /katex >}}-orbit and no others.
- Since {{< katex >}}$\tilde e${{< /katex >}} is surviving, another edge incident to {{< katex >}}$\tilde w${{< /katex >}} must be collapsible;
in other words {{< katex >}}$\operatorname{stab}(\tilde e) = \operatorname{stab}(\tilde e')${{< /katex >}}
for some edge {{< katex >}}$\tilde e'${{< /katex >}} with initial vertex {{< katex >}}$\tilde w${{< /katex >}}.
For the edge {{< katex >}}$\tilde e'${{< /katex >}} to be collapsible,
we need that its terminal vertex is not in the orbit of {{< katex >}}$\tilde w${{< /katex >}}.

Furthermore conversely, if we have a subset of {{< katex >}}$\operatorname{st}(\tilde v)${{< /katex >}}
satisfying the above three properties,
we can "blow up" the tree {{< katex >}}$T${{< /katex >}}, inserting a new edge orbit {{< katex >}}$\tilde e${{< /katex >}}.

## Ideal edges
The idea of an ideal edge in {{< katex >}}$\mathcal{G}${{< /katex >}} is designed to capture the above observations.
To wit, an *ideal edge* based at a vertex {{< katex >}}$v${{< /katex >}} is a subset {{< katex >}}$\alpha \subset D_v${{< /katex >}}
that is required to satisfy the following conditions.
Let {{< katex >}}$\mathcal{G}_\alpha${{< /katex >}} be the subgroup of {{< katex >}}$\mathcal{G}_v${{< /katex >}}
generated by the subgroups {{< katex >}}$g\iota_e(\mathcal{G}_e)g^{-1}${{< /katex >}}
for each direction {{< katex >}}$(g\iota_e(\mathcal{G}_e),e)${{< /katex >}} contained in {{< katex >}}$\alpha${{< /katex >}}.

- There are at least two directions in {{< katex >}}$\alpha${{< /katex >}} and at least two directions not in {{< katex >}}$\alpha${{< /katex >}}.
- If {{< katex >}}$(g\iota_e(\mathcal{G}_e),e) \in \alpha${{< /katex >}},
then the intersection {{< katex >}}$\mathcal{G}_v(g\iota_e(\mathcal{G}_e),e) \cap \alpha${{< /katex >}} equals
{{< katex >}}$\mathcal{G}_\alpha(g\iota_e(\mathcal{G}_e),e)${{< /katex >}}.
- The subgroup {{< katex >}}$\mathcal{G}_\alpha${{< /katex >}} is equal to {{< katex >}}$g\iota_e(\mathcal{G}_e)g^{-1}${{< /katex >}}
for some direction {{< katex >}}$(g\iota_e(\mathcal{G}_e),e) \in \alpha${{< /katex >}}
and no direction with underlying oriented edge {{< katex >}}$\bar e${{< /katex >}} is in {{< katex >}}$\alpha${{< /katex >}}.

We will say an oriented edge {{< katex >}}$e \in \alpha${{< /katex >}} if there is some direction
in {{< katex >}}$\alpha${{< /katex >}} with underlying oriented edge {{< katex >}}$e${{< /katex >}}.
Notice that it follows from the conditions that {{< katex >}}$\alpha${{< /katex >}} contains at least two oriented edges.
Let {{< katex >}}$D(\alpha)${{< /katex >}} be the set of oriented edges supporting a direction
satisfying the third item above.
If {{< katex >}}$\mathcal{G}${{< /katex >}} is reduced and {{< katex >}}$\alpha${{< /katex >}} is an ideal edge 
satisfying {{< katex >}}$\mathcal{G}_\alpha = \mathcal{G}_v${{< /katex >}},
then {{< katex >}}$D_v - \alpha${{< /katex >}} is also an ideal edge.
The first item in the definition is clear.
The second says that for each oriented edge {{< katex >}}$e \in \operatorname{st}(v)${{< /katex >}},
either all directions with underlying oriented edge {{< katex >}}$e${{< /katex >}} are in {{< katex >}}$\alpha${{< /katex >}} or none are,
which is also true of {{< katex >}}$D_v - \alpha${{< /katex >}}.
Since {{< katex >}}$\mathcal{G}${{< /katex >}} is reduced, some and hence every edge {{< katex >}}$e \in D(\alpha)${{< /katex >}}
must form a loop based at {{< katex >}}$v${{< /katex >}} (for otherwise we could collapse {{< katex >}}$e${{< /katex >}}),
so we have {{< katex >}}$\bar e \in D(D_v - \alpha)${{< /katex >}}.
We call {{< katex >}}$D_v - \alpha${{< /katex >}} the *inverse* of {{< katex >}}$\alpha${{< /katex >}}.
Two ideal edges {{< katex >}}$\alpha${{< /katex >}} and {{< katex >}}$\alpha'${{< /katex >}} are *equivalent*
if there exists {{< katex >}}$g \in \mathcal{G}_v${{< /katex >}} such that {{< katex >}}$g.\alpha = \alpha'${{< /katex >}}.

An ideal edge {{< katex >}}$\alpha${{< /katex >}} based at {{< katex >}}$v${{< /katex >}} is *contained in* an ideal edge {{< katex >}}$\beta${{< /katex >}}
if there exists {{< katex >}}$g \in \mathcal{G}_v${{< /katex >}}
such that {{< katex >}}$g.\alpha \subset \beta${{< /katex >}}.
If {{< katex >}}$\alpha${{< /katex >}} and {{< katex >}}$\beta${{< /katex >}} are based at {{< katex >}}$v${{< /katex >}},
the ideal edges are *disjoint* if {{< katex >}}$g.\alpha \cap \beta = \varnothing${{< /katex >}} 
for all {{< katex >}}$g \in \mathcal{G}_v${{< /katex >}}.
If {{< katex >}}$\alpha${{< /katex >}} and {{< katex >}}$\beta${{< /katex >}} are based at different vertices, then they are disjoint.
We say {{< katex >}}$\alpha${{< /katex >}} and {{< katex >}}$\beta${{< /katex >}} are *compatible*
if one is properly contained in the other or if they are disjoint and not inverse.

## Blowing up ideal edges

![Blowing up an ideal edge in a graph of groups](/img/idealedge.jpeg)

Let {{< katex >}}$\alpha${{< /katex >}} be an ideal edge of the marked graph of groups {{< katex >}}$\tau = (\mathcal{G},\sigma)${{< /katex >}}.
We construct a new marked graph of groups {{< katex >}}$\tau^\alpha = (\mathcal{G}^\alpha,\sigma^\alpha)${{< /katex >}}
by *blowing up* {{< katex >}}$\alpha${{< /katex >}} as follows.
The vertices and edges of {{< katex >}}$\mathcal{G}^\alpha${{< /katex >}} 
are the same as the vertices and edges of {{< katex >}}$\mathcal{G}${{< /katex >}}
with one new vertex {{< katex >}}$v_\alpha${{< /katex >}} and one new edge {{< katex >}}$\alpha${{< /katex >}};
the other vertices and edges are *old.*
The old vertex and edge groups are equal to what they are in {{< katex >}}$\mathcal{G}${{< /katex >}}.
We have {{< katex >}}$\mathcal{G}^\alpha_{v_\alpha} = \mathcal{G}_\alpha = \mathcal{G}^\alpha_\alpha${{< /katex >}}.
The new edge {{< katex >}}$\alpha${{< /katex >}} begins at {{< katex >}}$v_\alpha${{< /katex >}} and ends at {{< katex >}}$v${{< /katex >}}.
If {{< katex >}}$e${{< /katex >}} is an old oriented edge in {{< katex >}}$\alpha${{< /katex >}},
then {{< katex >}}$e${{< /katex >}} now has initial vertex {{< katex >}}$v_\alpha${{< /katex >}}
and the inclusion {{< katex >}}$\iota_e\colon \mathcal{G}^\alpha_e \to \mathcal{G}^\alpha_\alpha${{< /katex >}}
is obtained from {{< katex >}}$\iota_e\colon \mathcal{G}_e \to \mathcal{G}_v${{< /katex >}}
by recalling that we have {{< katex >}}$g\iota_e(\mathcal{G_e})g^{-1} \le \mathcal{G}_\alpha${{< /katex >}}
for some {{< katex >}}$g \in \mathcal{G}_v${{< /katex >}}.
Note that there is a choice here of group element {{< katex >}}$g${{< /katex >}};
differing choices will yield *equivalent* markings in a sense that I won't make precise here.
All other oriented edges have their initial vertices and edge-to-vertex group inclusions unchanged.
There is a *collapse map* {{< katex >}}$\mathcal{G}^\alpha \to \mathcal{G}${{< /katex >}}
defined by collapsing the edge {{< katex >}}$\alpha${{< /katex >}} and then "twisting" the edges incident to {{< katex >}}$v_\alpha${{< /katex >}}
by the corresponding choice of group element {{< katex >}}$g \in \mathcal{G}_v${{< /katex >}}.
We'll describe maps of general graphs of groups in another post.
Choose a homotopy inverse {{< katex >}}$f\colon \mathcal{G} \to \mathcal{G}^\alpha${{< /katex >}}
and define {{< katex >}}$\sigma^\alpha = f\sigma${{< /katex >}}.


Observe that if {{< katex >}}$\beta${{< /katex >}} is disjoint from (and not inverse to)
or properly included in {{< katex >}}$\alpha${{< /katex >}},
then {{< katex >}}$\beta${{< /katex >}} may be regarded as an ideal edge of {{< katex >}}$\mathcal{G}^\alpha${{< /katex >}}.
If {{< katex >}}$\alpha${{< /katex >}} are disjoint and not inverse, it's not hard to see that
{{< katex >}}$(\tau^\alpha)^\beta = (\tau^\beta)^\alpha${{< /katex >}}.

An *oriented ideal forest* in a marked graph of groups {{< katex >}}$\tau${{< /katex >}}
is a collection of equivalence classes {{< katex >}}$\{\alpha_1,\ldots,\alpha_k\}${{< /katex >}}
of ideal edges in {{< katex >}}$\tau${{< /katex >}} that are pairwise compatible.
The ideal edges in an oriented ideal forest are partially ordered under inclusion.
By repeatedly blowing up maximal elements of this partial order,
we obtain a marked graph of groups {{< katex >}}$\tau^{\alpha_1,\ldots,\alpha_k}${{< /katex >}}.
Because each ideal edge {{< katex >}}$\alpha${{< /katex >}} in a reduced marked graph of groups {{< katex >}}$\tau${{< /katex >}}
has an oriented edge in {{< katex >}}$D(\alpha)${{< /katex >}},
it follows that each edge of {{< katex >}}$\tau^{\alpha_1,\ldots,\alpha_k}${{< /katex >}} is surviving.

A pair of ideal edges {{< katex >}}$\alpha${{< /katex >}} and {{< katex >}}$\beta${{< /katex >}} are *pre-compatible*
if they are compatible, or {{< katex >}}$\alpha${{< /katex >}} is invertible with inverse {{< katex >}}$\bar\alpha${{< /katex >}}
and {{< katex >}}$\bar\alpha${{< /katex >}} is included in {{< katex >}}$\beta${{< /katex >}}.
It follows that {{< katex >}}$\beta${{< /katex >}} is invertible and that {{< katex >}}$\bar\beta${{< /katex >}} is included in {{< katex >}}$\alpha${{< /katex >}}.
An *ideal forest* is a collection of pairwise pre-compatible ideal edges
containing the inverse of each of its invertible elements.
We can complete each oriented ideal forest {{< katex >}}$\Phi${{< /katex >}} to an ideal forest {{< katex >}}$\Phi^\pm${{< /katex >}} by adding
the inverses of each of its invertible elements.
Krstić and Vogtmann prove for graphs of finite groups
as Lemma 5.7 of [their paper][equivariant outer space]
that if {{< katex >}}$\Phi^\pm = \Psi^\pm${{< /katex >}} as ideal forests
in a reduced marked graph of groups {{< katex >}}$\tau${{< /katex >}},
we have {{< katex >}}$\tau^\Phi = \tau^\Psi${{< /katex >}} as marked graphs of groups.
Again for graphs of finite groups,
Krstić and Vogtmann prove as Proposition 5.9 that the poset of marked graphs of groups in {{< katex >}}$L_T(G)${{< /katex >}}
collapsing to a reduced marked graph of groups {{< katex >}}$\tau${{< /katex >}} 
is isomorphic to the poset of ideal forests in {{< katex >}}$\tau${{< /katex >}}.

[shelters]: {{< ref "shelters-in-graphs-of-groups.md" >}}
[outer space]: https://marc-culler.info/static/home/papers/OuterSpace.pdf
[equivariant outer space]: https://www.researchgate.net/publication/226534036_Equivariant_outer_space_and_automorphisms_of_free-by-finite_groups/link/5762c70508aee61395bef5dc/download
[traintracks]: https://arxiv.org/abs/2102.02848
