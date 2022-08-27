---
layout: post
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
The following definition makes sense for a topological space $$X$$,
but is not the only reasonable definition for a surface.
The *mapping class group* of a surface $$\Sigma$$ is the group
of isotopy classes of orientation-preserving homeomorphisms of $$\Sigma$$,

$$\operatorname{Map}(\Sigma) = \pi_0(\operatorname{Homeo}^+(\Sigma)) 
= \operatorname{Homeo}^+(\Sigma)/\operatorname{Homeo}_0(\Sigma),$$

where $$\operatorname{Homeo}^+(\Sigma)$$ is the group of homeomorphisms
$$f \colon \Sigma \to \Sigma$$ and $$\operatorname{Homeo}_0(\Sigma)$$
is the normal subgroup comprising those homeomorphisms $$f$$ which are *isotopic to the identity,*
in the sense that there exists 
a continuous one-parameter family of homeomorphisms $$f_t\colon \Sigma \to \Sigma$$
with $$f_0 = f$$ and $$f_1$$ equal to the identity homeomorphism.
If we give $$\operatorname{Homeo}^+(\Sigma)$$ 
the [compact–open topology](https://en.wikipedia.org/wiki/Compact-open_topology),
an isotopy is a *path* in $$\operatorname{Homeo}(\Sigma)$$,
so if we care only about isotopy classes of homeomorphisms,
we are taking path-components in $$\operatorname{Homeo}^+(\Sigma)$$,
hence the notation above.

For a closed (hence finite-type) surface $$\Sigma$$,
every homotopy equivalence $$f\colon \Sigma \to \Sigma$$ is homotopic to a homeomorphism,
every homeomorphism is isotopic to a diffeomorphism,
two homeomorphisms are isotopic if and only if they are homotopic, and
every outer automorphism of $$\pi_1(\Sigma)$$ can be realized as a homotopy equivalence of $$\Sigma$$,
so there are a number of equivalent definitions of $$\operatorname{Map}(\Sigma)$$.
Not all of these facts remain true for infinite-type surfaces.

I punted on defining the compact–open topology to Wikipedia;
for us the essential feature of the topology on $$\operatorname{Map}(\Sigma)$$
is the following: a neighborhood basis of the identity is given by

$$U_S = \{[f] \in \operatorname{Map}(\Sigma) : f|_S = 1 \},$$

where $$S$$ is a finite-type subsurface of $$\Sigma$$.

## Nondisplaceable subsurfaces

Recall from [post "zero"] that $$A \subset \operatorname{Map}(\Sigma)$$ is coarsely bounded
if and only if $$A$$ has bounded orbits in any continuous action of $$\operatorname{Map}(\Sigma)$$
by isometries on a metric space. 

A connected, finite-type subsurface $$S$$ of $$\Sigma$$ is *nondisplaceable*
if for every homeomorphism $$f \colon \Sigma \to \Sigma$$,
we have $$f(S) \cap S \ne \varnothing$$.
If $$S$$ is not connected, we say $$S$$ is nondisplaceable if for each component $$C$$ of $$S$$
and every homeomorphism $$f \colon \Sigma \to \Sigma$$,
we have $$f(C) \cap S \ne \varnothing$$.
Mann and Rafi prove that the existence of nondisplaceable finite-type subsurfaces
obstructs coarse boundedness.

Say that a mapping class is *supported* on a subsurface $$S$$ 
if there exists a representative homeomorphism $$f\colon \Sigma \to \Sigma$$ such that

$$\{x \in \Sigma : f(x) \ne x\} \subset S.$$

Here is a precise statement of Mann–Rafi's result.

>**Theorem** (cf. [Mann–Rafi](https://arxiv.org/abs/1912.10914)
Theorem 1.9, Proposition 2.8, Lemma 5.2).
Suppose that $$\Sigma$$ contains a finite-type nondisplaceable subsurface $$S$$.
Then $$\operatorname{Map}(\Sigma)$$ is not coarsely bounded.
More generally, if $$S$$ is sufficiently complex 
as measured by the Euler characteristic of each of its components,
any subgroup of $$\operatorname{Map}(\Sigma)$$ containing the mapping classes supported on $$S$$
is not coarsely bounded in $$\operatorname{Map}(\Sigma)$$.

We finish this post by sketching the idea of the proof,
with the simplifying assumption that $$S$$ is a connected finite-type subsurface of $$\Sigma$$
with the property that every homeomorphism of $$\Sigma$$ leaves $$S$$ invariant up to isotopy
and such that the *curve graph* of $$S$$ is connected and has infinite diameter.

The *curve graph* $$\mathcal{C}(S)$$ of a finite-type surface $$S$$ is the simplicial graph
with vertex set the set of isotopy classes of *essential, simple* closed curves on $$S$$,
where a curve is *essential* if it is not null-homotopic nor homotopic 
to a puncture or boundary component of $$S$$,
and *simple* if it does not intersect itself.
Two vertices (essential simple closed curves) $$\gamma_1$$ and $$\gamma_2$$ are adjacent in
$$\mathcal{C}(S)$$ if and only if $$\gamma_1$$ and $$\gamma_2$$ have disjoint representatives.
It is an important fact in geometric group theory that if $$S$$ 
is not drawn from a finite list of exceptions,
$$\mathcal{C}(S)$$ with the *graph metric* assigning each edge length one
is connected, infinite-diameter and Gromov hyperbolic,
that $$\operatorname{Map}(S)$$ acts on $$\mathcal{C}(S)$$ by isometries
and that a certain class of elements $$f$$ of $$\operatorname{Map}(S)$$ 
called *pseudo-Anosov* mapping classes
act on $$\mathcal{C}(S)$$ with positive stable translation length,
in the sense that

$$\lim_{n\to\infty}\frac{d(\gamma, f^n(\gamma))}{n} > 0$$

for some and hence every vertex $$\gamma$$ of $$\mathcal{C}(S)$$.
There exist such a pseudo-Anosov mapping classes 
with representatives that may be taken to restrict to the identity
on the boundary of $$S$$.

Anyway, in the special case where every homeomorphism of $$\Sigma$$
leaves the isotopy class of $$S$$ invariant,
restriction to $$S$$ defines a continuous action of $$\operatorname{Map}(\Sigma)$$
on $$\mathcal{C}(S)$$.
If a homeomorphism $$f \colon S \to S$$ restricts to the identity on $$\partial S$$,
extending by the identity on $$\Sigma - S$$ defines a homeomorphism (and thus a mapping class)
of $$\Sigma$$ whose action on $$\mathcal{C}(S)$$ agrees with the action of $$[f]$$.
Taking $$f$$ to be pseudo-Anosov on $$S$$ 
proves that $$\operatorname{Map}(\Sigma)$$ does not have bounded orbits
in the action on $$\mathcal{C}(S)$$,
so $$\operatorname{Map}(\Sigma)$$ and any subgroup containing the extension of $$f$$ to $$\Sigma$$,
for example $$U_R$$ for some finite-type subsurface $$R$$ 
whose isotopy class is disjoint from that of $$S$$,
is not coarsely bounded in $$\operatorname{Map}(\Sigma)$$.

## Examples 

Suppose as a first case that $$0 < \operatorname{genus}(\Sigma) < \infty$$.
Then any finite-type subsurface $$S$$ of $$\Sigma$$ with genus equal to that of $$\Sigma$$
is nondisplaceable for the reason that it contains all the isotopy classes of 
essential simple closed curves of $$\Sigma$$ that are non-separating,
and homeomorphisms send non-separating curves to non-separating curves.

As another example, suppose $$\Sigma$$ has at least three but finitely many maximal ends,
in the sense of the preorder introduced in the [previous post].
Then any finite-type subsurface which separates each maximal end from each other is nondisplaceable.
As an example, the subsurface indicated in the figure below
separates the maximal ends of the subsurface considered in the previous post.
It is certainly not the only such subsurface.

![The indicated finite-type subsurface separates the three maximal ends of the surface](/assets/img/infinitetypenondisplaceable.jpeg)

[post "zero"]: {% link _posts/2022-08-10-Groups-as-Metric-Spaces.md %}
[previous post]: {% link _posts/2022-08-11-Ends-of-Surfaces.md %}
