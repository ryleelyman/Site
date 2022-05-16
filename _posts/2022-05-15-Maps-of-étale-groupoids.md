---
layout: post
math: true
---
The purpose of this post is to explore two or three notions of a *map* between étale groupoids.
We follow the notation for étale groupoids established in the [last post][étale].

## Functors

If $$\mathcal{G}$$ and $$\mathcal{H}$$ are étale groupoids,
which are in particular *categories,* a natural class of maps of étale groupoids to consider would be
the *continuous functors.*
A functor $$f\colon \mathcal{G} \to \mathcal{H}$$ is a pair of maps
$$f_0\colon \mathcal{G}_0 \to \mathcal{H}_0$$ and $$f_1\colon \mathcal{G}_1 \to \mathcal{H}_1$$
that commute with the various structure maps.
So for example we have $$\alpha f_1 = f_0 \alpha$$ and $$\omega f_1 = f_0 \omega$$.

## Example: Refinement groupoids

Given an étale groupoid $$\mathcal{G}$$ and an open cover 
$$\mathcal{U} = \{ U_i \}_{i \in I}$$ of $$\mathcal{G}_0$$,
we construct a *refinement groupoid* $$\mathcal{G}^{\mathcal{U}}$$ and a functor
$$\pi^{\mathcal{U}}\colon \mathcal{G}^{\mathcal{U}} \to \mathcal{G}$$.
The space of objects is the disjoint union $$\coprod_{i\in I} U_i$$.
For $$x \in U_i$$, write the corresponding object of $$\mathcal{G}^{\mathcal{U}}$$ as $$x_i$$.
The space of arrows $$\mathcal{G}^{\mathcal{U}}_1$$ is the set

$$\{f_{j,i} \colon x_i \to y_j : f\colon x \to y \in \mathcal{G}_1\}.$$

A basic open set for the topology on $$\mathcal{G}^{\mathcal{U}}_1$$ is of the form $$V_{j,i}$$
where $$V\subset \mathcal{G}_1$$ is an open set
and $$V_{j,i} = \{f_{j,i} \colon f \in V\}$$.
The functor $$\pi^{\mathcal{U}}$$ is defined on objects as $$\pi^{\mathcal{U}}_0(x_i) = x$$
and $$\pi^{\mathcal{U}}_1(f_{j,i}) = f$$.

Like all functors, $$\pi^{\mathcal{U}}$$ induces a continuous map of orbit spaces
$$\overline{\pi^{\mathcal{U}}}\colon \mathcal{G}^{\mathcal{U}}_1\backslash\mathcal{G}^{\mathcal{U}}_0 
\to \mathcal{G}_1\backslash\mathcal{G}_0$$
and for each point $$x \in \mathcal{G}^{\mathcal{U}}_0$$, a homomorphism of isotropy groups
$$\pi^{\mathcal{U}}_x \colon \mathcal{G}^{\mathcal{U}}_x \to \mathcal{G}_{\pi^{\mathcal{U}}_0(x)}$$.
The functor $$\pi^{\mathcal{U}}$$ is an *equivalence* in the sense that
the map $$\pi_0^{\mathcal{U}}$$ is étale, the map $$\overline{\pi^{\mathcal{U}}}$$ is a homeomorphism
and each $$\pi^{\mathcal{U}}_x$$ is an isomorphism.

One can show that in fact $$\pi^{\mathcal{U}}$$
is an *equivalence of categories* in the sense that it is *full, faithful* and *essentially surjective.*
Here *full* and *faithful* refer to the fact that for every pair of objects $$x$$ and $$y$$
in $$\mathcal{G}^{\mathcal{U}}$$, the map of sets 

$$\{f\colon x \to y\} \to \{f\colon \pi^{\mathcal{U}}_0(x) \to \pi^{\mathcal{U}}_0(y)\}$$

is surjective and injective, respectively.
(This is packaged up in the fact that the map of orbit spaces is injective and that the maps on isotropy groups
are isomorphisms.)
*Essentially surjective* means that every object in $$\mathcal{G}$$ is isomorphic
to an object in the image of $$\pi^{\mathcal{U}}$$.
(This is packaged up in the fact that the map of orbit spaces is surjective.)
You should probably think of the étale condition on $$\pi^{\mathcal{U}}_0$$
as being the extra sauce that distinguishes a continuous bijection from a homeomorphism.

Notice, however, that $$\pi^{\mathcal{U}}$$ typically fails to have an inverse functor,
even up to natural transformation (about which more in a second).
I talked a little about this failure [a long time ago][axiom of choice].

Suppose the open cover $$\mathcal{V} = \{V_j\}_{j \in J}$$ is a refinement of the open cover $$\mathcal{U}$$,
in the sense that for each $$j \in J$$,
there exists $$i \in I$$ such that $$V_j \subset U_i$$.
A choice for each $$j$$ of $$\varphi(j) \in I$$ with this property
defines a *refinement function* $$\varphi \colon J \to I$$.
Associated to the choice of $$\varphi$$, there is a continuous functor 
$$\pi^{\varphi}\colon \mathcal{G}^{\mathcal{V}} \to \mathcal{G}^{\mathcal{U}}$$
defined on objects as $$\pi^\varphi(x_j) = x_{\varphi(j)}$$ and on arrows as
$$\pi^{\varphi}(f_{j,i}) = f_{\varphi(j),\varphi(i)}$$.
This functor is also an equivalence and satisfies $$\pi^{\mathcal{U}}\pi^\varphi = \pi^{\mathcal{V}}$$.

## Natural transformations 

A *natural transformation* $$\eta\colon \phi \Rightarrow \psi$$ of (continuous) functors
$$\phi$$, $$\psi\colon \mathcal{G} \to \mathcal{H}$$ is a continuous map
$$\eta\colon \mathcal{G}_0 \to \mathcal{H}_1$$ such that for each arrow $$f\colon x \to y$$
in $$\mathcal{G}$$, we have $$\eta(y)\circ \phi(f) = \psi(f) \circ \eta(x)$$.
(There's a commutative square I'm deciding to omit. 
Drawing it yourself when demonstrating naturality is very instructive.)
Notice that because all arrows in groupoids are invertible,
$$\eta$$ is automatically a *natural isomorphism.*

Given two refinement functions $$\varphi$$, $$\varphi'\colon J \to I$$,
there is a natural transformation $$\eta\colon \pi^{\varphi} \Rightarrow \pi^{\varphi'}$$
defined as $$\eta(x_j) = (1_x)_{\varphi'(j),\varphi(j)}$$.
It's not too hard to see that this is continuous because the assignment $$x \mapsto 1_x$$ is continuous,
and for each arrow $$f_{j,i} \colon x_i \to y_j$$ in $$\mathcal{G}^{\mathcal{V}}$$
the following diagram commutes

$$\require{AMScd}\begin{CD}
    x_{\varphi(i)} @>{(1_x)_{\varphi'(i),\varphi(i)}}>> x_{\varphi'(i)} \\
    @VV{f_{\varphi(j),\varphi(i)}}V @VV{f_{\varphi'(j),\varphi'(i)}}V \\
    y_{\varphi(j)} @>{(1_y)_{\varphi'(j),\varphi(j)}}>> y_{\varphi'(j)}
\end{CD}$$

because $$1_yf = f 1_x$$.

## Localizing

Given a category $$C$$ with a class of arrows $$W$$ satisfying [certain conditions][category of fractions]
satisfied by the class of equivalences of étale groupoids
one can construct a (relatively nice) category $$C[W^{-1}]$$
in which the arrows are *spans* of the form $$\begin{CD}x @<w<< y @>f>> z\end{CD}$$,
where $$w \in W$$.
Moerdijk constructed this localization for étale groupoids
after first identifying two functors if they differ by a natural transformation.
A *generalized map* of étale groupoids is a map of this form.
Two groupoids $$\mathcal{G}$$ and $$\mathcal{H}$$ are *Morita equivalent* if there is a groupoid $$\mathcal{K}$$
and equivalences $$\mathcal{K} \to \mathcal{G}$$ and $$\mathcal{K} \to \mathcal{H}$$.
Morita equivalent groupoids become isomorphic in Moerdijk's localization.

## Maps using cover groupoids

More concretely, I prefer the following approach.
A *map* of étale groupoids $$f\colon \mathcal{G} \to \mathcal{H}$$ is a functor
$$\mathcal{f}^{\mathcal{U}} \colon \mathcal{G}^{\mathcal{U}} \to \mathcal{H}$$,
where $$\mathcal{G}^{\mathcal{U}}$$ is a refinement groupoid of $$\mathcal{G}$$.
Two functors $$\phi\colon \mathcal{G}^{\mathcal{U}} \to \mathcal{H}$$ 
and $$\psi\colon \mathcal{G}^{\mathcal{V}} \to \mathcal{H}$$
*define the same generalized map* if there exists a common refinement 
$$\mathcal{W}$$ of $$\mathcal{U}$$ and $$\mathcal{V}$$
such that for some (and hence any) choice of refinement functions $$\varphi\colon \mathcal{W} \to \mathcal{U}$$
and $$\varphi'\colon \mathcal{W} \to \mathcal{V}$$,
the following diagram commutes up to a natural transformation 
$$\eta\colon \phi\pi^{\varphi} \Rightarrow \psi\pi^{\varphi'}$$

$$\begin{CD}
\mathcal{G}^{\mathcal{W}} @>\pi^\varphi>> \mathcal{G}^{\mathcal{U}} \\
@VV\pi^{\varphi'}V  @VV\phi V \\
\mathcal{G}^{\mathcal{V}} @>\psi>> \mathcal{H}.
\end{CD}$$

Given maps $$f\colon \mathcal{G} \to \mathcal{H}$$ and $$g\colon \mathcal{H} \to \mathcal{K}$$
represented by functors $$f^{\mathcal{U}}$$ and $$g^{\mathcal{V}}$$,
write $$\mathcal{V} = \{V_j\}_{j\in J}$$ and let $$\mathcal{W} = \{W_i\}_{i\in I}$$ be a refinement
of $$\mathcal{U}$$ with the property that there is a function $$\theta\colon I \to J$$
such that $$f^{\mathcal{U}}\pi^{\mathcal{U},\mathcal{W}}(W_i) \subset V_{\theta(i)}$$
for all $$i \in I$$, where 
$$\pi^{\mathcal{U},\mathcal{W}}\colon \mathcal{G}^{\mathcal{W}} \to \mathcal{G}^{\mathcal{U}}$$ 
is some choice of refinement functor.
There is a functor $$f^{\mathcal{V},\mathcal{W}}\colon \mathcal{G}^{\mathcal{W}}\to\mathcal{H}^{\mathcal{V}}$$
defined on objects as

$$f^{\mathcal{V},\mathcal{W}}(x_i) = (f^{\mathcal{U}}\pi^{\mathcal{U},\mathcal{W}}(x_i))_{\theta(i)}$$

and on arrows as

$$f^{\mathcal{V},\mathcal{W}}(f_{j,i}) =
(f^{\mathcal{U}}\pi^{\mathcal{U},\mathcal{W}}(f_{j,i}))_{\theta(j),\theta(i)}.$$

We define the composite map $$gf\colon \mathcal{G} \to \mathcal{K}$$ to be the map represented by the functor
$$g^{\mathcal{V}}f^{\mathcal{V},\mathcal{W}} \colon \mathcal{G}^{\mathcal{W}} \to \mathcal{K}$$.
It is perhaps not immediately obvious that this composition is well-defined and associative,
but we assure the reader that it is and that the reader probably does not want to read a demonstration.

One can check more or less by hand that every span in the sense above
defines a generalized map in our sense and conversely
so that the category of étale groupoids where the arrows are our generalized maps
coincides with Moerdijk's.

## Bibundles

To me, the less-familiar approach is to use *bibundles.*
In this section I follow [Lerman's article][Lerman].
We begin as follows.
A *right action* of an étale groupoid $$\mathcal{G}$$ on a space $$x$$
is the following data:
- a map $$a \colon X \to \mathcal{G}_0$$ called the *anchor* and
- a map

$$X \times_{\mathcal{G}_0} \mathcal{G}_1 = \{(x,f) \in X \times \mathcal{G}_1 : a(x) = \omega(f)\} 
\to X, \qquad (x,f) \mapsto x.f$$

called the *action* such that
  - $$a(x.f) = \alpha(f)$$ for all $$x$$ and $$f$$ for which $$x.f$$ is defined
  - $$(x.f).g = x.(fg)$$ when appropriate and
  - $$x.1_{a(x)} = x$$ for all $$x \in X$$.

There is similarly a definition of a *left* action of a groupoid on a space.

If $$X$$ is equipped with a right action of an étale groupoid $$\mathcal{G}$$,
we say that $$X$$ is a *principal (right) $$\mathcal{G}$$-bundle over B*
if there is an open surjection $$\pi\colon X \to B$$ such that the following hold.
- For each $$b \in B$$, there exists a neighborhood $$U$$ of $$b$$ and a *section*
$$s\colon U \to X$$ such that $$\pi s = 1_U$$. 
(In the case of orbifolds where we're working with smooth manifolds,
the existence of local sections is guaranteed by the property that $$\pi$$
is a *submersion.*
In general there are open surjections which do not admit local sections,
so I think we have to build this into the theory.)
- We have $$\pi(x.f) = \pi(x)$$ for all $$(x,f) \in X\times_{\mathcal{G}_0} \mathcal{G}_1$$—we
describe this by saying that $$\pi$$ is *$$\mathcal{G}$$-invariant.*
- The map $$(x,f) \mapsto (x,x.f)$$ is a homeomorphism
$$X\times_{\mathcal{G}_0}\mathcal{G}_1 \to X \times_B X$$;
in other words $$\mathcal{G}$$ acts freely and transitively on the fibers of $$\pi\colon X \to B$$.

Given an étale groupoid $$\mathcal{G}$$, the target map $$\omega\colon \mathcal{G}_1 \to \mathcal{G}_0$$
makes $$\mathcal{G}_1$$ into a right principal $$\mathcal{G}$$-bundle,
where the action of $$\mathcal{G}$$ is right-multiplication 
and the anchor is $$\alpha\colon \mathcal{G}_1 \to \mathcal{G}_0$$.

A *bibundle* from $$\mathcal{G}$$ to $$\mathcal{H}$$
is a space $$X$$ together with $$a_L \colon X \to \mathcal{G}_0$$ and $$a_R \colon X \to \mathcal{H}_0$$
such that the following properties hold.
- There is a left action of $$\mathcal{G}$$ on $$X$$ with respect to the anchor $$a_L$$
and a right action of $$\mathcal{H}$$ on $$X$$ with respect to the anchor $$a_R$$.
These actions commute.
- The map $$a_L \colon X \to \mathcal{G}_0$$ makes $$X$$ a principal $$\mathcal{H}$$-bundle.
- The map $$a_R$$ is $$\mathcal{G}$$-invariant in the sense that $$a_R(g.x) = a_R(x)$$ for all $$(g,x)$$
for which $$g.x$$ is defined.

Two bibundles $$X,Y \colon \mathcal{G} \to \mathcal{H}$$ are *isomorphic*
if there is a $$\mathcal{G}$$–$$\mathcal{H}$$-equivariant homeomorphism $$\eta\colon X \to Y$$,
i.e. $$\eta(g.x.f) = g.\eta(x).f$$ for all triples for which the actions are defined.

## Bibundles defined by functors

Given a functor $$\phi \colon \mathcal{G} \to \mathcal{H}$$, there is a bibundle $$X_\phi$$
where

$$X_\phi = \{ (x,f) \in \mathcal{G}_0 \times \mathcal{H}_1 : \phi_0(x) = \omega(f)\}$$

and $$B$$ is $$\mathcal{G}_0$$. The right action of $$\mathcal{H}$$ is the restriction of the obvious action
on the product $$\mathcal{G}_0 \times \mathcal{H}_1$$.
In other words, $$(x,f).h = (x,fh)$$.
The left action of $$\mathcal{G}$$ over the anchor $$(x,f) \mapsto x$$
is defined by $$g.(x,f) = (\omega(g),\phi_1(g)h)$$.
It is clear that the actions commute,
and that the map $$a_R$$ defined by $$(x,f) \mapsto \alpha(f)$$ is $$\mathcal{G}$$-invariant,
since $$a_R(g.(x,f)) = \alpha(\phi_1(g)f) = \alpha(f)$$.

Let us check that $$(x,f) \mapsto x$$ makes $$X_\phi$$ into a principal $$\mathcal{H}$$-bundle.
The projection $$(x,f) \mapsto x$$ is certainly an open surjection which is $$\mathcal{H}$$-invariant.
Consider the map $$((x,f),g) \mapsto ((x,f),(x,fg))$$
from $$X_\phi \times_{\mathcal{H}_0}\mathcal{H}_1 \to X_\phi \times_{\mathcal{G}_0} X_\phi$$.
We claim that this is a homeomorphism,
indeed that the map $$((x,f),(x,g)) \mapsto ((x,f),f^{-1}g)$$ is a continuous inverse.
To see that this is well-defined notice that
the multiplication $$f^{-1}g$$ is defined, since $$\phi_0(x) = \omega(f) = \omega(g)$$.

Bibundles may be composed (I'll neglect to mention *how*),
but the composition is only associative up to isomorphism of bibundles.
If one thinks of isomorphisms between bibundles as being akin to natural transformations
(indeed, naturally isomorphic functors have isomorphic associated bibundles),
then the category of étale groupoids with arrows bibundles is what's called a *weak* $$2$$-category.

## The equivalence of the two approaches

This post is already quite long, but I wanted to explain how to see that bibundles
give rise to generalized maps in our sense.
So let $$X \colon \mathcal{G} \to \mathcal{H}$$ be a bibundle.
For each $$p \in \mathcal{G}_0$$, there is a local section $$s_p\colon U_p \to X$$
defined on a neighborhood of $$p$$.
Consider the open cover $$\mathcal{U} = \{U_p\}_{p \in \mathcal{G}_0}$$ of $$\mathcal{G}_0$$,
and the space

$$X^{\mathcal{U}} = \mathcal{G}^{\mathcal{U}}_0 \times_{\mathcal{G}_0} X
= \{ (p_i,x) \in \mathcal{G}^{\mathcal{U}}_0 \times X : p = a_L(x) \}$$

We claim that map $$(p_i,x) \mapsto p_i$$ makes $$X^{\mathcal{U}}$$ into a principal $$\mathcal{H}$$-bundle,
where the anchor is $$(p_i,x) \mapsto a_R(x)$$ and the action is $$(p_i,x).h = (p_i,x.h)$$. 
Notice that $$p = a_L(x.h) = a_L(x)$$ since $$X$$ is $$\mathcal{H}$$-principal, so this is well-defined,
and clearly $$\mathcal{H}$$-invariant.
Now consider the map $$((p_i,x),h) \mapsto ((p_i,x),(p_i,x.h))$$.
Since $$(x,h) \mapsto (x,x.h)$$ is a homeomorphism, this map will also be a homeomorphism,
proving the claim.

There is a left action of $$\mathcal{G}^{\mathcal{U}}$$ on $$X^{\mathcal{U}}$$
where the anchor is $$(p_i,x) \mapsto p_i$$ and the action is $$g_{j,i}.(p_i,x) = (\omega(g_{j,i}),g.x)$$. 
By the definition of the left action of $$\mathcal{G}$$ on $$X$$, this is well-defined.
It is clear that the left and right actions commute; we have already shown that $$X^{\mathcal{U}}$$
is $$\mathcal{H}$$-principal,
and we have $$(\omega(g_{j,i}),g.x) \mapsto a_R(g.x) = a_R (x)$$, so the right anchor is left invariant.
Therefore we have a bibundle $$X^{\mathcal{U}} \colon \mathcal{G}^{\mathcal{U}} \to \mathcal{H}$$.

The bibundle $$X^{\mathcal{U}}$$ has a global section $$p_i \mapsto (p_i,s_i(p))$$.
If $$(p_i,x)$$ is another point of $$X^{\mathcal{U}}$$,
since $$X^{\mathcal{U}} \times_{\mathal{H}_0} \mathcal{H}_1$$ is homeomorphic to
$$X^{\mathcal{U}}\times_{\mathcal{G}^{\mathcal{U}_0} X^{\mathcal{U}}$$,
there exists a unique arrow $$h \in \mathcal{H}_1$$ such that $$(p_i,x) = (p_i,s_i(p)).h$$.
We claim the map $$(p_i,x) \mapsto (p_i,h)$$
from $$X^{\mathcal{U}}$$ to

$$\{ (p_i,h) \in \mathcal{G}^{\mathcal{U}}_0\times \mathcal{H}_1 : a_R(s_i(p)) = \omega(h) \}$$

is a homeomorphism. Indeed, the map $$(p_i,h) \mapsto (p_i,s_i(p).h)$$ is its inverse.
We claim that the rule $$\phi_0(p_i) = a_R(s_i(p))$$ defines the action on objects of a functor
$$\mathcal{G}^{\mathcal{U}} \to \mathcal{H}$$.
The action on arrows sends $$g_{j,i} \colon x_i \to y_j$$ to the unique arrow $$\phi_1(g_{j,i})$$ such that
$$g_{j,i} . (x_i, s_i(x)) = (y_j, s_j(y)).\phi_1(g_{j,i})$$.
Given $$f_{k,j} \colon y_j \to z_k$$, notice that

$$f_{k,j} . g_{j,i} . (x_i, s_i(x)) = f_{k,j} . (y_j, s_j(y)). \phi_1(g_{j,i}) 
= (z_k, s_k(z)) . \phi_1(f_{k,j}) . \phi_1(g_{j,i})$$

since the left and right actions commute.
On the other hand,

$$ (f_{k,j}g_{j,i}) . (x_i, s_i(x)) = (z_k,s_k(z)) .\phi_1(f_{k,j}g_{j,i})$$

so since the left action is associative, $$\phi_1$$ indeed defines a functor! Cute.

[étale]: {% link _posts/2022-05-14-Graphs-of-groups-as-étale-groupoids.md %}
[axiom of choice]: {% link _posts/2020-08-02-The-Axiom-of-Choice-is-False-for-Manifolds.md %}
[category of fractions]: https://ncatlab.org/nlab/show/calculus+of+fractions
[Lerman]: https://ems.press/content/serial-article-files/6839
