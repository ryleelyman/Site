---
title: "Graphs of Groups as Étale Groupoids"
date: 2022-05-14T15:22:36-04:00
math: true
---
It's been a while since I talked about étale groupoids!
Time to rectify this situation.
The purpose of this post is to explain how to see graphs of groups as étale groupoids.
In a later post I'd like to explore the notion of maps between étale groupoids.

## Groupoids

A *groupoid* is a small category {{< katex >}}$\mathcal{G}${{< /katex >}} in which all arrows are invertible.
Thus there are two sets, {{< katex >}}$\mathcal{G}_0${{< /katex >}} and {{< katex >}}$\mathcal{G}_1${{< /katex >}} of objects and arrows respectively,
and several structure maps:
- {{< katex >}}$\alpha${{< /katex >}}, {{< katex >}}$\omega\colon \mathcal{G}_1 \to \mathcal{G}_0${{< /katex >}} sending an arrow {{< katex >}}$f\colon x \to y${{< /katex >}}
to its *source* {{< katex >}}$x${{< /katex >}} and *target* {{< katex >}}$y${{< /katex >}} respectively.
- An injection {{< katex >}}$\iota\colon \mathcal{G}_0 \to \mathcal{G}_1${{< /katex >}} sending an object {{< katex >}}$x${{< /katex >}} to the identity arrow
{{< katex >}}$1_x\colon x \to x${{< /katex >}}.
- An inversion map {{< katex >}}$(\cdot)^{-1}\colon \mathcal{G}_1 \to \mathcal{G}_1${{< /katex >}}
sending an arrow {{< katex >}}$f\colon x \to y${{< /katex >}} to its inverse {{< katex >}}$f^{-1}\colon y \to x${{< /katex >}}.
- A multiplication map {{< katex >}}$\circ\colon \mathcal{G}_1 \times_{\mathcal{G}_0} \mathcal{G}_1 \to \mathcal{G}_1${{< /katex >}}
sending a pair of arrows {{< katex >}}$f${{< /katex >}} and {{< katex >}}$g${{< /katex >}} with {{< katex >}}$\alpha(f) = \omega(g)${{< /katex >}} to their composite
{{< katex >}}$g\circ f = gf${{< /katex >}}.

The maps are required to satisfy certain identities saying,
for instance, that composition is associative.
A *topological groupoid* is a groupoid equipped with a topology on {{< katex >}}$\mathcal{G}_0${{< /katex >}} and {{< katex >}}$\mathcal{G}_1${{< /katex >}}
making all the structure maps continuous.
A topological groupoid is *étale* if {{< katex >}}$\alpha${{< /katex >}} and {{< katex >}}$\omega${{< /katex >}} are étale maps, i.e. local homeomorphisms.

Given an étale groupoid and a point {{< katex >}}$x \in \mathcal{G}_0${{< /katex >}},
its *orbit* is the set 

{{< katex >}}$\mathcal{G}\cdot x = \{ y \in \mathcal{G}_0 : \exists f\colon x \to y\}.${{< /katex >}}

The orbits partition {{< katex >}}$\mathcal{G}_0${{< /katex >}} and the *space of orbits* {{< katex >}}$\mathcal{G}_1\backslash\mathcal{G}_0${{< /katex >}}
is the quotient space given the quotient topology.
We may also define the *isotropy group* {{< katex >}}$\mathcal{G}_x${{< /katex >}} as

{{< katex >}}$\mathcal{G}_x = \{ f \in \mathcal{G}_1 : \alpha(f) = \omega(f) = x \}.${{< /katex >}}

Since {{< katex >}}$\mathcal{G}${{< /katex >}} is étale, it turns out that {{< katex >}}$\mathcal{G}_x${{< /katex >}} is discrete as a subspace of {{< katex >}}$\mathcal{G}_1${{< /katex >}}.

## Graphs of groups as étale groupoids

I think I've mentioned how orbifolds may be thought of as étale groupoids.
Indeed, Haefliger describes this in Chapter III.{{< katex >}}$\mathcal{G}${{< /katex >}} of 
[Metric Spaces of Nonpositive Curvature][TheBible].
(Incidentally, I like to cheekily use the citation command "TheBible" for that book,
even though my research has called for citing it less frequently than I originally expected.)
What is maybe less well-known (although Haefliger also covers this)
is how to view a graph of groups (or more generally a *complex* of groups) as an étale groupoid.
I'll describe how to do this for *effective* graphs of groups,
where the construction is a little slicker,
although one could give a "hands-on" construction in the general case without too much difficulty.

Let us set notation. A *graph of groups* {{< katex >}}$(\Gamma,\mathscr{G})${{< /katex >}} is a connected graph {{< katex >}}$\Gamma${{< /katex >}}
together with an assignment of groups {{< katex >}}$\mathscr{G}_v${{< /katex >}} and {{< katex >}}$\mathscr{G}_e${{< /katex >}} to each vertex {{< katex >}}$v${{< /katex >}} and edge {{< katex >}}$e${{< /katex >}}
of {{< katex >}}$\Gamma${{< /katex >}}.
When the oriented edge {{< katex >}}$e${{< /katex >}} has initial vertex {{< katex >}}$v${{< /katex >}},
we require the existence of an injective homomorphism {{< katex >}}$\mathscr{G}_e \to \mathscr{G}_v${{< /katex >}}.

Given a vertex {{< katex >}}$v${{< /katex >}}, write {{< katex >}}$\operatorname{st}(v)${{< /katex >}} for the set of oriented edges {{< katex >}}$e${{< /katex >}} with initial vertex {{< katex >}}$v${{< /katex >}}.
Let {{< katex >}}$\tau(e)${{< /katex >}} denote the terminal vertex of the oriented edge {{< katex >}}$e${{< /katex >}}.
Let {{< katex >}}$\widetilde{\operatorname{st}}(v)${{< /katex >}} be the quotient of the disjoint union

{{< katex >}}$ \coprod_{e\in\operatorname{st}(v)} \mathscr{G}_v/\iota_e(\mathscr{G}_e) \times (e \setminus \tau(e))${{< /katex >}}

by the equivalence relation that identifies the initial vertex of all of these oriented edges.
(To make the resulting groupoid étale, we need to remove the terminal vertices.)
Call the identified vertex {{< katex >}}$v${{< /katex >}}.
There is a natural action of {{< katex >}}$\mathscr{G}_v${{< /katex >}} on {{< katex >}}$\widetilde{\operatorname{st}}(v)${{< /katex >}} by multiplication in the labels.
This action fixes {{< katex >}}$v${{< /katex >}}.

A graph of groups is *effective* if only the family of trivial subgroups of each {{< katex >}}$\mathscr{G}_v${{< /katex >}}
satisfies the following conditions:
- For each vertex $v$, we have a normal subgroup {{< katex >}}$N_v\le \mathscr{G}_v${{< /katex >}}.
- For each edge {{< katex >}}$e${{< /katex >}} of {{< katex >}}$\Gamma${{< /katex >}} with initial vertex {{< katex >}}$v${{< /katex >}} and terminal vertex {{< katex >}}$w${{< /katex >}},
there is a subgroup {{< katex >}}$N_e${{< /katex >}} of {{< katex >}}$\mathscr{G}_e${{< /katex >}} such that {{< katex >}}$\iota_e(N_e) = N_v${{< /katex >}} and {{< katex >}}$\iota_{\bar e}(N_e) = N_w${{< /katex >}}.

Let {{< katex >}}$\mathcal{G}_0${{< /katex >}} be the disjoint union of the spaces {{< katex >}}$\widetilde{\operatorname{st}}(v)${{< /katex >}}
as {{< katex >}}$v${{< /katex >}} varies over the vertices of {{< katex >}}$\Gamma${{< /katex >}}.
Each element of each {{< katex >}}$\mathscr{G}_v${{< /katex >}} acts as a homeomorphism of an open neighborhood of {{< katex >}}$\mathcal{G}_0${{< /katex >}}.
The orientation reversal of the interior of an oriented edge {{< katex >}}$e\mapsto \bar e${{< /katex >}}
also defines a homeomorphism of an open neighborhood of {{< katex >}}$\mathcal{G}_0${{< /katex >}} for each pair of lifts
of the interiors of {{< katex >}}$e${{< /katex >}} and {{< katex >}}$\bar e${{< /katex >}} to {{< katex >}}$\mathcal{G}_0${{< /katex >}}.
We may consider the *pseudogroup* generated by these local homeomorphisms.

Briefly, the *pseudogroup generated* by a collection of homeomorphisms {{< katex >}}$f\colon U \to V${{< /katex >}} 
of open subsets of a topological space {{< katex >}}$X${{< /katex >}}
(such that the unions of the {{< katex >}}$U${{< /katex >}} cover {{< katex >}}$X${{< /katex >}})
is the smallest collection of homeomorphisms containing the given collection 
and satisfying the following properties.
- The restriction of a homeomorphism {{< katex >}}$f\colon U \to V${{< /katex >}} in the collection
to an open subset of {{< katex >}}$U${{< /katex >}} is in the collection.
- The composition {{< katex >}}$gf${{< /katex >}} of any two elements {{< katex >}}$f\colon U \to V${{< /katex >}} and {{< katex >}}$g \colon V \to W${{< /katex >}}
in the collection
is in the collection (note the domain of {{< katex >}}$g${{< /katex >}}).
- The inverse of any homeomorphism in the collection is in the collection.
- If {{< katex >}}$f\colon U \to V${{< /katex >}} is a homeomorphism with the property that
there is an open cover {{< katex >}}$\{U_i\}${{< /katex >}} of {{< katex >}}$U${{< /katex >}} such that {{< katex >}}$f|_{U_i}${{< /katex >}} is in the collection for each {{< katex >}}$i${{< /katex >}},
then {{< katex >}}$f${{< /katex >}} is in the collection.

The space of arrows {{< katex >}}$\mathcal{G}_1${{< /katex >}} is the space of *germs* of elements of the pseudogroup.
A *germ* of a homeomorphism {{< katex >}}$f\colon U \to V${{< /katex >}} at a point {{< katex >}}$x \in U${{< /katex >}}
is its equivalence class under the equivalence relation of agreement under restriction to a neighborhood of {{< katex >}}$x${{< /katex >}}.
The germ therefore has a well-defined *source* {{< katex >}}$\alpha(f) = x${{< /katex >}}
and *target* {{< katex >}}$\omega(f) = f(x)${{< /katex >}}.
We give {{< katex >}}$\mathcal{G}_1${{< /katex >}} the *germ topology:* a basis for this topology is given by sets of the form {{< katex >}}$U_f${{< /katex >}},
where {{< katex >}}$f\colon U \to V${{< /katex >}} is a homeomorphism and {{< katex >}}$U_f${{< /katex >}} 
consists of the germs of {{< katex >}}$f${{< /katex >}} at the various points of {{< katex >}}$U${{< /katex >}}.

To bring things down to earth, if you chase through the definitions,
you see that if {{< katex >}}$v${{< /katex >}} is a vertex of {{< katex >}}$\Gamma${{< /katex >}} thought of as a point of {{< katex >}}$\mathcal{G}_0${{< /katex >}},
then {{< katex >}}$\mathcal{G}_v = \mathscr{G}_v${{< /katex >}}.
The point {{< katex >}}$v${{< /katex >}} is equal to its orbit {{< katex >}}$\mathcal{G}\cdot v${{< /katex >}}.
If {{< katex >}}$x${{< /katex >}} is a point in the interior of an edge {{< katex >}}$e${{< /katex >}},
then {{< katex >}}$x${{< /katex >}} determines an orbit in {{< katex >}}$\mathcal{G}_0${{< /katex >}} comprising all those points 
in each {{< katex >}}$\widetilde{\operatorname{st}}(v)${{< /katex >}}
of the form {{< katex >}}$(g\iota_e(\mathscr{G}_e), x) \subset \mathscr{G}_v/\iota_e(\mathscr{G}_e)\times e \setminus \tau(e)${{< /katex >}}
where {{< katex >}}$e${{< /katex >}} is allowed to occur in either orientation.
Put another way, we have {{< katex >}}$\Gamma = \mathcal{G}_1\backslash\mathcal{G}_0${{< /katex >}}.
The isotropy group {{< katex >}}$\mathcal{G}_x${{< /katex >}} is isomorphic to {{< katex >}}$\mathscr{G}_e${{< /katex >}}.

[TheBible]: https://www.maths.ed.ac.uk/~v1ranick/papers/bridsonhaefligerx.pdf
