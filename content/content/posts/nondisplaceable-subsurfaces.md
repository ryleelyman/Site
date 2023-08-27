---
title: "Nondisplaceable Subsurfaces"
date: 2022-08-12T16:12:26-04:00
math: true
---
This is the second post in a series on Katie Mann and Kasra Rafi's paper
[Large-scale geometry of big mapping class groups](https://arxiv.org/abs/1912.10914).
The purpose of this post is to introduce the main obstruction to coarse boundedness
of subsets of a big mapping class group: nondisplaceable finite-type subsurfaces.
I also define the mapping class group in this post.

## The mapping class group

Mapping class groups of finite-type surfaces are central objects in modern mathematics,
bridging fields as disparate as algebraic geometry and low-dimensional topology.
Informally one should think of the mapping class group as the group of "symmetries" of a space.
The following definition makes sense for a topological space {{< katex >}}$X${{< /katex >}},
but is not the only reasonable definition for a surface.
The *mapping class group* of a surface {{< katex >}}$\Sigma${{< /katex >}} is the group
of isotopy classes of orientation-preserving homeomorphisms of {{< katex >}}$\Sigma${{< /katex >}},

{{< katex >}}$$\operatorname{Map}(\Sigma) = \pi_0(\operatorname{Homeo}^+(\Sigma)) 
= \operatorname{Homeo}^+(\Sigma)/\operatorname{Homeo}_0(\Sigma),$${{< /katex >}}

where {{< katex >}}$\operatorname{Homeo}^+(\Sigma)${{< /katex >}} is the group of homeomorphisms
{{< katex >}}$f \colon \Sigma \to \Sigma${{< /katex >}} and {{< katex >}}$\operatorname{Homeo}_0(\Sigma)${{< /katex >}}
is the normal subgroup comprising those homeomorphisms {{< katex >}}$f${{< /katex >}} which are *isotopic to the identity,*
in the sense that there exists 
a continuous one-parameter family of homeomorphisms {{< katex >}}$f_t\colon \Sigma \to \Sigma${{< /katex >}}
with {{< katex >}}$f_0 = f${{< /katex >}} and {{< katex >}}$f_1${{< /katex >}} equal to the identity homeomorphism.
If we give {{< katex >}}$\operatorname{Homeo}^+(\Sigma)${{< /katex >}} 
the [compact–open topology](https://en.wikipedia.org/wiki/Compact-open_topology),
an isotopy is a *path* in {{< katex >}}$\operatorname{Homeo}(\Sigma)${{< /katex >}},
so if we care only about isotopy classes of homeomorphisms,
we are taking path-components in {{< katex >}}$\operatorname{Homeo}^+(\Sigma)${{< /katex >}},
hence the notation above.

For a closed (hence finite-type) surface {{< katex >}}$\Sigma${{< /katex >}},
every homotopy equivalence {{< katex >}}$f\colon \Sigma \to \Sigma${{< /katex >}} is homotopic to a homeomorphism,
every homeomorphism is isotopic to a diffeomorphism,
two homeomorphisms are isotopic if and only if they are homotopic, and
every outer automorphism of {{< katex >}}$\pi_1(\Sigma)${{< /katex >}} can be realized as a homotopy equivalence of {{< katex >}}$\Sigma${{< /katex >}},
so there are a number of equivalent definitions of {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}.
Not all of these facts remain true for infinite-type surfaces.

I punted on defining the compact–open topology to Wikipedia;
for us the essential feature of the topology on {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}
is the following: a neighborhood basis of the identity is given by

{{< katex >}}$U_S = \{[f] \in \operatorname{Map}(\Sigma) : f|_S = 1 \},${{< /katex >}}

where {{< katex >}}$S${{< /katex >}} is a finite-type subsurface of {{< katex >}}$\Sigma${{< /katex >}}.

## Nondisplaceable subsurfaces

Recall from [post "zero"] that {{< katex >}}$A \subset \operatorname{Map}(\Sigma)${{< /katex >}} is coarsely bounded
if and only if {{< katex >}}$A${{< /katex >}} has bounded orbits in any continuous action of {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}
by isometries on a metric space. 

A connected, finite-type subsurface {{< katex >}}$S${{< /katex >}} of {{< katex >}}$\Sigma${{< /katex >}} is *nondisplaceable*
if for every homeomorphism {{< katex >}}$f \colon \Sigma \to \Sigma${{< /katex >}},
we have {{< katex >}}$f(S) \cap S \ne \varnothing${{< /katex >}}.
If {{< katex >}}$S${{< /katex >}} is not connected, we say {{< katex >}}$S${{< /katex >}} is nondisplaceable if for each component {{< katex >}}$C${{< /katex >}} of {{< katex >}}$S${{< /katex >}}
and every homeomorphism {{< katex >}}$f \colon \Sigma \to \Sigma${{< /katex >}},
we have {{< katex >}}$f(C) \cap S \ne \varnothing${{< /katex >}}.
Mann and Rafi prove that the existence of nondisplaceable finite-type subsurfaces
obstructs coarse boundedness.

Say that a mapping class is *supported* on a subsurface {{< katex >}}$S${{< /katex >}} 
if there exists a representative homeomorphism {{< katex >}}$f\colon \Sigma \to \Sigma${{< /katex >}} such that

{{< katex >}}$\{x \in \Sigma : f(x) \ne x\} \subset S.${{< /katex >}}

Here is a precise statement of Mann–Rafi's result.

>**Theorem** (cf. [Mann–Rafi](https://arxiv.org/abs/1912.10914)
Theorem 1.9, Proposition 2.8, Lemma 5.2).
Suppose that {{< katex >}}$\Sigma${{< /katex >}} contains a finite-type nondisplaceable subsurface {{< katex >}}$S${{< /katex >}}.
Then {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}} is not coarsely bounded.
More generally, if {{< katex >}}$S${{< /katex >}} is sufficiently complex 
as measured by the Euler characteristic of each of its components,
any subgroup of {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}} containing the mapping classes supported on {{< katex >}}$S${{< /katex >}}
is not coarsely bounded in {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}.

We finish this post by sketching the idea of the proof,
with the simplifying assumption that {{< katex >}}$S${{< /katex >}} is a connected finite-type subsurface of {{< katex >}}$\Sigma${{< /katex >}}
with the property that every homeomorphism of {{< katex >}}$\Sigma${{< /katex >}} leaves {{< katex >}}$S${{< /katex >}} invariant up to isotopy
and such that the *curve graph* of {{< katex >}}$S${{< /katex >}} is connected and has infinite diameter.

The *curve graph* {{< katex >}}$\mathcal{C}(S)${{< /katex >}} of a finite-type surface {{< katex >}}$S${{< /katex >}} is the simplicial graph
with vertex set the set of isotopy classes of *essential, simple* closed curves on {{< katex >}}$S${{< /katex >}},
where a curve is *essential* if it is not null-homotopic nor homotopic 
to a puncture or boundary component of {{< katex >}}$S${{< /katex >}},
and *simple* if it does not intersect itself.
Two vertices (essential simple closed curves) {{< katex >}}$\gamma_1${{< /katex >}} and {{< katex >}}$\gamma_2${{< /katex >}} are adjacent in
{{< katex >}}$\mathcal{C}(S)${{< /katex >}} if and only if {{< katex >}}$\gamma_1${{< /katex >}} and {{< katex >}}$\gamma_2${{< /katex >}} have disjoint representatives.
It is an important fact in geometric group theory that if {{< katex >}}$S${{< /katex >}} 
is not drawn from a finite list of exceptions,
{{< katex >}}$\mathcal{C}(S)${{< /katex >}} with the *graph metric* assigning each edge length one
is connected, infinite-diameter and Gromov hyperbolic,
that {{< katex >}}$\operatorname{Map}(S)${{< /katex >}} acts on {{< katex >}}$\mathcal{C}(S)${{< /katex >}} by isometries
and that a certain class of elements {{< katex >}}$f${{< /katex >}} of {{< katex >}}$\operatorname{Map}(S)${{< /katex >}} 
called *pseudo-Anosov* mapping classes
act on {{< katex >}}$\mathcal{C}(S)${{< /katex >}} with positive stable translation length,
in the sense that

{{< katex >}}$\lim_{n\to\infty}\frac{d(\gamma, f^n(\gamma))}{n} > 0${{< /katex >}}

for some and hence every vertex {{< katex >}}$\gamma${{< /katex >}} of {{< katex >}}$\mathcal{C}(S)${{< /katex >}}.
There exist such a pseudo-Anosov mapping classes 
with representatives that may be taken to restrict to the identity
on the boundary of {{< katex >}}$S${{< /katex >}}.

Anyway, in the special case where every homeomorphism of {{< katex >}}$\Sigma${{< /katex >}}
leaves the isotopy class of {{< katex >}}$S${{< /katex >}} invariant,
restriction to {{< katex >}}$S${{< /katex >}} defines a continuous action of {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}
on {{< katex >}}$\mathcal{C}(S)${{< /katex >}}.
If a homeomorphism {{< katex >}}$f \colon S \to S${{< /katex >}} restricts to the identity on {{< katex >}}$\partial S${{< /katex >}},
extending by the identity on {{< katex >}}$\Sigma - S${{< /katex >}} defines a homeomorphism (and thus a mapping class)
of {{< katex >}}$\Sigma${{< /katex >}} whose action on {{< katex >}}$\mathcal{C}(S)${{< /katex >}} agrees with the action of {{< katex >}}$[f]${{< /katex >}}.
Taking {{< katex >}}$f${{< /katex >}} to be pseudo-Anosov on {{< katex >}}$S${{< /katex >}} 
proves that {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}} does not have bounded orbits
in the action on {{< katex >}}$\mathcal{C}(S)${{< /katex >}},
so {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}} and any subgroup containing the extension of {{< katex >}}$f${{< /katex >}} to {{< katex >}}$\Sigma${{< /katex >}},
for example {{< katex >}}$U_R${{< /katex >}} for some finite-type subsurface {{< katex >}}$R${{< /katex >}} 
whose isotopy class is disjoint from that of {{< katex >}}$S${{< /katex >}},
is not coarsely bounded in {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}.

## Examples 

Suppose as a first case that {{< katex >}}$0 < \operatorname{genus}(\Sigma) < \infty${{< /katex >}}.
Then any finite-type subsurface {{< katex >}}$S${{< /katex >}} of {{< katex >}}$\Sigma${{< /katex >}} with genus equal to that of {{< katex >}}$\Sigma${{< /katex >}}
is nondisplaceable for the reason that it contains all the isotopy classes of 
essential simple closed curves of {{< katex >}}$\Sigma${{< /katex >}} that are non-separating,
and homeomorphisms send non-separating curves to non-separating curves.

As another example, suppose {{< katex >}}$\Sigma${{< /katex >}} has at least three but finitely many maximal ends,
in the sense of the preorder introduced in the [previous post].
Then any finite-type subsurface which separates each maximal end from each other is nondisplaceable.
As an example, the subsurface indicated in the figure below
separates the maximal ends of the subsurface considered in the previous post.
It is certainly not the only such subsurface.

![The indicated finite-type subsurface separates the three maximal ends of the surface](/img/infinitetypenondisplaceable.jpeg)

[post "zero"]: {{< ref "groups-as-metric-spaces.md" >}}
[previous post]: {{< ref "ends-of-surfaces.md" >}}

