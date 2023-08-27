---
title: "Maps of Étale Groupoids"
date: 2022-05-15T15:24:52-04:00
math: true
---
The purpose of this post is to explore two or three notions of a *map* between étale groupoids.
We follow the notation for étale groupoids established in the [last post][étale].

## Functors

If {{< katex >}}$\mathcal{G}${{< /katex >}} and {{< katex >}}$\mathcal{H}${{< /katex >}} are étale groupoids,
which are in particular *categories,* a natural class of maps of étale groupoids to consider would be
the *continuous functors.*
A functor {{< katex >}}$f\colon \mathcal{G} \to \mathcal{H}${{< /katex >}} is a pair of maps
{{< katex >}}$f_0\colon \mathcal{G}_0 \to \mathcal{H}_0${{< /katex >}} and {{< katex >}}$f_1\colon \mathcal{G}_1 \to \mathcal{H}_1${{< /katex >}}
that commute with the various structure maps.
So for example we have {{< katex >}}$\alpha f_1 = f_0 \alpha${{< /katex >}} and {{< katex >}}$\omega f_1 = f_0 \omega${{< /katex >}}.

## Example: Refinement groupoids

Given an étale groupoid {{< katex >}}$\mathcal{G}${{< /katex >}} and an open cover 
{{< katex >}}$\mathcal{U} = \{ U_i \}_{i \in I}${{< /katex >}} of {{< katex >}}$\mathcal{G}_0${{< /katex >}},
we construct a *refinement groupoid* {{< katex >}}$\mathcal{G}^{\mathcal{U}}${{< /katex >}} and a functor
{{< katex >}}$\pi^{\mathcal{U}}\colon \mathcal{G}^{\mathcal{U}} \to \mathcal{G}${{< /katex >}}.
The space of objects is the disjoint union {{< katex >}}$\coprod_{i\in I} U_i${{< /katex >}}.
For {{< katex >}}$x \in U_i${{< /katex >}}, write the corresponding object of {{< katex >}}$\mathcal{G}^{\mathcal{U}}${{< /katex >}} as {{< katex >}}$x_i${{< /katex >}}.
The space of arrows {{< katex >}}$\mathcal{G}^{\mathcal{U}}_1${{< /katex >}} is the set

{{< katex >}}$\{f_{j,i} \colon x_i \to y_j : f\colon x \to y \in \mathcal{G}_1\}.${{< /katex >}}

A basic open set for the topology on {{< katex >}}$\mathcal{G}^{\mathcal{U}}_1${{< /katex >}} is of the form {{< katex >}}$V_{j,i}${{< /katex >}}
where {{< katex >}}$V\subset \mathcal{G}_1${{< /katex >}} is an open set
and {{< katex >}}$V_{j,i} = \{f_{j,i} \colon f \in V\}${{< /katex >}}.
The functor {{< katex >}}$\pi^{\mathcal{U}}${{< /katex >}} is defined on objects as {{< katex >}}$\pi^{\mathcal{U}}_0(x_i) = x${{< /katex >}}
and {{< katex >}}$\pi^{\mathcal{U}}_1(f_{j,i}) = f${{< /katex >}}.

Like all functors, {{< katex >}}$\pi^{\mathcal{U}}${{< /katex >}} induces a continuous map of orbit spaces
{{< katex >}}$\overline{\pi^{\mathcal{U}}}\colon \mathcal{G}^{\mathcal{U}}_1\backslash\mathcal{G}^{\mathcal{U}}_0 
\to \mathcal{G}_1\backslash\mathcal{G}_0${{< /katex >}}
and for each point {{< katex >}}$x \in \mathcal{G}^{\mathcal{U}}_0${{< /katex >}}, a homomorphism of isotropy groups
{{< katex >}}$\pi^{\mathcal{U}}_x \colon \mathcal{G}^{\mathcal{U}}_x \to \mathcal{G}_{\pi^{\mathcal{U}}_0(x)}${{< /katex >}}.
The functor {{< katex >}}$\pi^{\mathcal{U}}${{< /katex >}} is an *equivalence* in the sense that
the map {{< katex >}}$\pi_0^{\mathcal{U}}${{< /katex >}} is étale, the map {{< katex >}}$\overline{\pi^{\mathcal{U}}}${{< /katex >}} is a homeomorphism
and each {{< katex >}}$\pi^{\mathcal{U}}_x${{< /katex >}} is an isomorphism.

One can show that in fact {{< katex >}}$\pi^{\mathcal{U}}${{< /katex >}}
is an *equivalence of categories* in the sense that it is *full, faithful* and *essentially surjective.*
Here *full* and *faithful* refer to the fact that for every pair of objects {{< katex >}}$x${{< /katex >}} and {{< katex >}}$y${{< /katex >}}
in {{< katex >}}$\mathcal{G}^{\mathcal{U}}${{< /katex >}}, the map of sets 

{{< katex >}}$\{f\colon x \to y\} \to \{f\colon \pi^{\mathcal{U}}_0(x) \to \pi^{\mathcal{U}}_0(y)\}${{< /katex >}}

is surjective and injective, respectively.
(This is packaged up in the fact that the map of orbit spaces is injective and that the maps on isotropy groups
are isomorphisms.)
*Essentially surjective* means that every object in {{< katex >}}$\mathcal{G}${{< /katex >}} is isomorphic
to an object in the image of {{< katex >}}$\pi^{\mathcal{U}}${{< /katex >}}.
(This is packaged up in the fact that the map of orbit spaces is surjective.)
You should probably think of the étale condition on {{< katex >}}$\pi^{\mathcal{U}}_0${{< /katex >}}
as being the extra sauce that distinguishes a continuous bijection from a homeomorphism.

Notice, however, that {{< katex >}}$\pi^{\mathcal{U}}${{< /katex >}} typically fails to have an inverse functor,
even up to natural transformation (about which more in a second).
I talked a little about this failure [a long time ago][axiom of choice].

Suppose the open cover {{< katex >}}$\mathcal{V} = \{V_j\}_{j \in J}${{< /katex >}} is a refinement of the open cover {{< katex >}}$\mathcal{U}${{< /katex >}},
in the sense that for each {{< katex >}}$j \in J${{< /katex >}},
there exists {{< katex >}}$i \in I${{< /katex >}} such that {{< katex >}}$V_j \subset U_i${{< /katex >}}.
A choice for each {{< katex >}}$j${{< /katex >}} of {{< katex >}}$\varphi(j) \in I${{< /katex >}} with this property
defines a *refinement function* {{< katex >}}$\varphi \colon J \to I${{< /katex >}}.
Associated to the choice of {{< katex >}}$\varphi${{< /katex >}}, there is a continuous functor 
{{< katex >}}$\pi^{\varphi}\colon \mathcal{G}^{\mathcal{V}} \to \mathcal{G}^{\mathcal{U}}${{< /katex >}}
defined on objects as {{< katex >}}$\pi^\varphi(x_j) = x_{\varphi(j)}${{< /katex >}} and on arrows as
{{< katex >}}$\pi^{\varphi}(f_{j,i}) = f_{\varphi(j),\varphi(i)}${{< /katex >}}.
This functor is also an equivalence and satisfies {{< katex >}}$\pi^{\mathcal{U}}\pi^\varphi = \pi^{\mathcal{V}}${{< /katex >}}.

## Natural transformations 

A *natural transformation* {{< katex >}}$\eta\colon \phi \Rightarrow \psi${{< /katex >}} of (continuous) functors
{{< katex >}}$\phi${{< /katex >}}, {{< katex >}}$\psi\colon \mathcal{G} \to \mathcal{H}${{< /katex >}} is a continuous map
{{< katex >}}$\eta\colon \mathcal{G}_0 \to \mathcal{H}_1${{< /katex >}} such that for each arrow {{< katex >}}$f\colon x \to y${{< /katex >}}
in {{< katex >}}$\mathcal{G}${{< /katex >}}, we have {{< katex >}}$\eta(y)\circ \phi(f) = \psi(f) \circ \eta(x)${{< /katex >}}.
(There's a commutative square I'm deciding to omit. 
Drawing it yourself when demonstrating naturality is very instructive.)
Notice that because all arrows in groupoids are invertible,
{{< katex >}}$\eta${{< /katex >}} is automatically a *natural isomorphism.*

Given two refinement functions {{< katex >}}$\varphi${{< /katex >}}, {{< katex >}}$\varphi'\colon J \to I${{< /katex >}},
there is a natural transformation {{< katex >}}$\eta\colon \pi^{\varphi} \Rightarrow \pi^{\varphi'}${{< /katex >}}
defined as {{< katex >}}$\eta(x_j) = (1_x)_{\varphi'(j),\varphi(j)}${{< /katex >}}.
It's not too hard to see that this is continuous because the assignment {{< katex >}}$x \mapsto 1_x${{< /katex >}} is continuous,
and for each arrow {{< katex >}}$f_{j,i} \colon x_i \to y_j${{< /katex >}} in {{< katex >}}$\mathcal{G}^{\mathcal{V}}${{< /katex >}}
the following diagram commutes

{{< katex >}}$$\begin{CD}
    x_{\varphi(i)} @>{(1_x)_{\varphi'(i),\varphi(i)}}>> x_{\varphi'(i)} \\
    @VV{f_{\varphi(j),\varphi(i)}}V @VV{f_{\varphi'(j),\varphi'(i)}}V \\
    y_{\varphi(j)} @>{(1_y)_{\varphi'(j),\varphi(j)}}>> y_{\varphi'(j)}
\end{CD}$${{< /katex >}}

because {{< katex >}}$1_yf = f 1_x${{< /katex >}}.

## Localizing

Given a category {{< katex >}}$C${{< /katex >}} with a class of arrows {{< katex >}}$W${{< /katex >}} satisfying [certain conditions][category of fractions]
satisfied by the class of equivalences of étale groupoids
one can construct a (relatively nice) category {{< katex >}}$C[W^{-1}]${{< /katex >}}
in which the arrows are *spans* of the form {{< katex >}}$$\begin{CD}x @<w<< y @>f>> z\end{CD},$${{< /katex >}}
where {{< katex >}}$w \in W${{< /katex >}}.
Moerdijk constructed this localization for étale groupoids
after first identifying two functors if they differ by a natural transformation.
A *generalized map* of étale groupoids is a map of this form.
Two groupoids {{< katex >}}$\mathcal{G}${{< /katex >}} and {{< katex >}}$\mathcal{H}${{< /katex >}} are *Morita equivalent* if there is a groupoid {{< katex >}}$\mathcal{K}${{< /katex >}}
and equivalences {{< katex >}}$\mathcal{K} \to \mathcal{G}${{< /katex >}} and {{< katex >}}$\mathcal{K} \to \mathcal{H}${{< /katex >}}.
Morita equivalent groupoids become isomorphic in Moerdijk's localization.

## Maps using refinement groupoids

More concretely, I prefer the following approach.
A *map* of étale groupoids {{< katex >}}$f\colon \mathcal{G} \to \mathcal{H}${{< /katex >}} is a functor
{{< katex >}}$\mathcal{f}^{\mathcal{U}} \colon \mathcal{G}^{\mathcal{U}} \to \mathcal{H}${{< /katex >}},
where {{< katex >}}$\mathcal{G}^{\mathcal{U}}${{< /katex >}} is a refinement groupoid of {{< katex >}}$\mathcal{G}${{< /katex >}}.
Two functors {{< katex >}}$\phi\colon \mathcal{G}^{\mathcal{U}} \to \mathcal{H}${{< /katex >}} 
and {{< katex >}}$\psi\colon \mathcal{G}^{\mathcal{V}} \to \mathcal{H}${{< /katex >}}
*define the same generalized map* if there exists a common refinement 
{{< katex >}}$\mathcal{W}${{< /katex >}} of {{< katex >}}$\mathcal{U}${{< /katex >}} and {{< katex >}}$\mathcal{V}${{< /katex >}}
such that for some (and hence any) choice of refinement functions {{< katex >}}$\varphi\colon \mathcal{W} \to \mathcal{U}${{< /katex >}}
and {{< katex >}}$\varphi'\colon \mathcal{W} \to \mathcal{V}${{< /katex >}},
the following diagram commutes up to a natural transformation 
{{< katex >}}$\eta\colon \phi\pi^{\varphi} \Rightarrow \psi\pi^{\varphi'}${{< /katex >}}

{{< katex >}}$$\begin{CD}
\mathcal{G}^{\mathcal{W}} @>\pi^\varphi>> \mathcal{G}^{\mathcal{U}} \\
@VV\pi^{\varphi'}V  @VV\phi V \\
\mathcal{G}^{\mathcal{V}} @>\psi>> \mathcal{H}.
\end{CD}$${{< /katex >}}

Given maps {{< katex >}}$f\colon \mathcal{G} \to \mathcal{H}${{< /katex >}} and {{< katex >}}$g\colon \mathcal{H} \to \mathcal{K}${{< /katex >}}
represented by functors {{< katex >}}$f^{\mathcal{U}}${{< /katex >}} and {{< katex >}}$g^{\mathcal{V}}${{< /katex >}},
write {{< katex >}}$\mathcal{V} = \{V_j\}_{j\in J}${{< /katex >}} and let {{< katex >}}$\mathcal{W} = \{W_i\}_{i\in I}${{< /katex >}} be a refinement
of {{< katex >}}$\mathcal{U}${{< /katex >}} with the property that there is a function {{< katex >}}$\theta\colon I \to J${{< /katex >}}
such that {{< katex >}}$f^{\mathcal{U}}\pi^{\mathcal{U},\mathcal{W}}(W_i) \subset V_{\theta(i)}${{< /katex >}}
for all {{< katex >}}$i \in I${{< /katex >}}, where 
{{< katex >}}$\pi^{\mathcal{U},\mathcal{W}}\colon \mathcal{G}^{\mathcal{W}} \to \mathcal{G}^{\mathcal{U}}${{< /katex >}} 
is some choice of refinement functor.
There is a functor {{< katex >}}$f^{\mathcal{V},\mathcal{W}}\colon \mathcal{G}^{\mathcal{W}}\to\mathcal{H}^{\mathcal{V}}${{< /katex >}}
defined on objects as

{{< katex >}}$f^{\mathcal{V},\mathcal{W}}(x_i) = (f^{\mathcal{U}}\pi^{\mathcal{U},\mathcal{W}}(x_i))_{\theta(i)}${{< /katex >}}

and on arrows as

{{< katex >}}$$f^{\mathcal{V},\mathcal{W}}(f_{j,i}) =
(f^{\mathcal{U}}\pi^{\mathcal{U},\mathcal{W}}(f_{j,i}))_{\theta(j),\theta(i)}.$${{< /katex >}}

We define the composite map {{< katex >}}$gf\colon \mathcal{G} \to \mathcal{K}${{< /katex >}} to be the map represented by the functor
{{< katex >}}$g^{\mathcal{V}}f^{\mathcal{V},\mathcal{W}} \colon \mathcal{G}^{\mathcal{W}} \to \mathcal{K}${{< /katex >}}.
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
A *right action* of an étale groupoid {{< katex >}}$\mathcal{G}${{< /katex >}} on a space {{< katex >}}$x${{< /katex >}}
is the following data:
- a map {{< katex >}}$a \colon X \to \mathcal{G}_0${{< /katex >}} called the *anchor* and
- a map

{{< katex >}}$$X \times_{\mathcal{G}_0} \mathcal{G}_1 = \{(x,f) \in X \times \mathcal{G}_1 : a(x) = \omega(f)\} 
\to X, \qquad (x,f) \mapsto x.f$${{< /katex >}}

called the *action* such that
  - {{< katex >}}$a(x.f) = \alpha(f)${{< /katex >}} for all {{< katex >}}$x${{< /katex >}} and {{< katex >}}$f${{< /katex >}} for which {{< katex >}}$x.f${{< /katex >}} is defined
  - {{< katex >}}$(x.f).g = x.(fg)${{< /katex >}} when appropriate and
  - {{< katex >}}$x.1_{a(x)} = x${{< /katex >}} for all {{< katex >}}$x \in X${{< /katex >}}.

There is similarly a definition of a *left* action of a groupoid on a space.

If {{< katex >}}$X${{< /katex >}} is equipped with a right action of an étale groupoid {{< katex >}}$\mathcal{G}${{< /katex >}},
we say that {{< katex >}}$X${{< /katex >}} is a *principal (right) {{< katex >}}$\mathcal{G}${{< /katex >}}-bundle over B*
if there is an open surjection {{< katex >}}$\pi\colon X \to B${{< /katex >}} such that the following hold.
- For each {{< katex >}}$b \in B${{< /katex >}}, there exists a neighborhood {{< katex >}}$U${{< /katex >}} of {{< katex >}}$b${{< /katex >}} and a *section*
{{< katex >}}$s\colon U \to X${{< /katex >}} such that {{< katex >}}$\pi s = 1_U${{< /katex >}}. 
(In the case of orbifolds where we're working with smooth manifolds,
the existence of local sections is guaranteed by the property that {{< katex >}}$\pi${{< /katex >}}
is a *submersion.*
In general there are open surjections which do not admit local sections,
so I think we have to build this into the theory.)
- We have {{< katex >}}$\pi(x.f) = \pi(x)${{< /katex >}} for all {{< katex >}}$(x,f) \in X\times_{\mathcal{G}_0} \mathcal{G}_1${{< /katex >}}—we
describe this by saying that {{< katex >}}$\pi${{< /katex >}} is *{{< katex >}}$\mathcal{G}${{< /katex >}}-invariant.*
- The map {{< katex >}}$(x,f) \mapsto (x,x.f)${{< /katex >}} is a homeomorphism
{{< katex >}}$X\times_{\mathcal{G}_0}\mathcal{G}_1 \to X \times_B X${{< /katex >}};
in other words {{< katex >}}$\mathcal{G}${{< /katex >}} acts freely and transitively on the fibers of {{< katex >}}$\pi\colon X \to B${{< /katex >}}.

Given an étale groupoid {{< katex >}}$\mathcal{G}${{< /katex >}}, the target map {{< katex >}}$\omega\colon \mathcal{G}_1 \to \mathcal{G}_0${{< /katex >}}
makes {{< katex >}}$\mathcal{G}_1${{< /katex >}} into a right principal {{< katex >}}$\mathcal{G}${{< /katex >}}-bundle,
where the action of {{< katex >}}$\mathcal{G}${{< /katex >}} is right-multiplication 
and the anchor is {{< katex >}}$\alpha\colon \mathcal{G}_1 \to \mathcal{G}_0${{< /katex >}}.

A *bibundle* from {{< katex >}}$\mathcal{G}${{< /katex >}} to {{< katex >}}$\mathcal{H}${{< /katex >}}
is a space {{< katex >}}$X${{< /katex >}} together with {{< katex >}}$a_L \colon X \to \mathcal{G}_0${{< /katex >}} and {{< katex >}}$a_R \colon X \to \mathcal{H}_0${{< /katex >}}
such that the following properties hold.
- There is a left action of {{< katex >}}$\mathcal{G}${{< /katex >}} on {{< katex >}}$X${{< /katex >}} with respect to the anchor {{< katex >}}$a_L${{< /katex >}}
and a right action of {{< katex >}}$\mathcal{H}${{< /katex >}} on {{< katex >}}$X${{< /katex >}} with respect to the anchor {{< katex >}}$a_R${{< /katex >}}.
These actions commute.
- The map {{< katex >}}$a_L \colon X \to \mathcal{G}_0${{< /katex >}} makes {{< katex >}}$X${{< /katex >}} a principal {{< katex >}}$\mathcal{H}${{< /katex >}}-bundle.
- The map {{< katex >}}$a_R${{< /katex >}} is {{< katex >}}$\mathcal{G}${{< /katex >}}-invariant in the sense that {{< katex >}}$a_R(g.x) = a_R(x)${{< /katex >}} for all {{< katex >}}$(g,x)${{< /katex >}}
for which {{< katex >}}$g.x${{< /katex >}} is defined.

Two bibundles {{< katex >}}$X,Y \colon \mathcal{G} \to \mathcal{H}${{< /katex >}} are *isomorphic*
if there is a {{< katex >}}$\mathcal{G}${{< /katex >}}–{{< katex >}}$\mathcal{H}${{< /katex >}}-equivariant homeomorphism {{< katex >}}$\eta\colon X \to Y${{< /katex >}},
i.e. {{< katex >}}$\eta(g.x.f) = g.\eta(x).f${{< /katex >}} for all triples for which the actions are defined.

## Bibundles defined by functors

Given a functor {{< katex >}}$\phi \colon \mathcal{G} \to \mathcal{H}${{< /katex >}}, there is a bibundle {{< katex >}}$X_\phi${{< /katex >}}
where

{{< katex >}}$X_\phi = \{ (x,f) \in \mathcal{G}_0 \times \mathcal{H}_1 : \phi_0(x) = \omega(f)\}${{< /katex >}}

and {{< katex >}}$B${{< /katex >}} is {{< katex >}}$\mathcal{G}_0${{< /katex >}}. The right action of {{< katex >}}$\mathcal{H}${{< /katex >}} is the restriction of the obvious action
on the product {{< katex >}}$\mathcal{G}_0 \times \mathcal{H}_1${{< /katex >}}.
In other words, {{< katex >}}$(x,f).h = (x,fh)${{< /katex >}}.
The left action of {{< katex >}}$\mathcal{G}${{< /katex >}} over the anchor {{< katex >}}$(x,f) \mapsto x${{< /katex >}}
is defined by {{< katex >}}$g.(x,f) = (\omega(g),\phi_1(g)h)${{< /katex >}}.
It is clear that the actions commute,
and that the map {{< katex >}}$a_R${{< /katex >}} defined by {{< katex >}}$(x,f) \mapsto \alpha(f)${{< /katex >}} is {{< katex >}}$\mathcal{G}${{< /katex >}}-invariant,
since {{< katex >}}$a_R(g.(x,f)) = \alpha(\phi_1(g)f) = \alpha(f)${{< /katex >}}.

Let us check that {{< katex >}}$(x,f) \mapsto x${{< /katex >}} makes {{< katex >}}$X_\phi${{< /katex >}} into a principal {{< katex >}}$\mathcal{H}${{< /katex >}}-bundle.
The projection {{< katex >}}$(x,f) \mapsto x${{< /katex >}} is certainly an open surjection which is {{< katex >}}$\mathcal{H}${{< /katex >}}-invariant.
Consider the map {{< katex >}}$((x,f),g) \mapsto ((x,f),(x,fg))${{< /katex >}}
from {{< katex >}}$X_\phi \times_{\mathcal{H}_0}\mathcal{H}_1 \to X_\phi \times_{\mathcal{G}_0} X_\phi${{< /katex >}}.
We claim that this is a homeomorphism,
indeed that the map {{< katex >}}$((x,f),(x,g)) \mapsto ((x,f),f^{-1}g)${{< /katex >}} is a continuous inverse.
To see that this is well-defined notice that
the multiplication {{< katex >}}$f^{-1}g${{< /katex >}} is defined, since {{< katex >}}$\phi_0(x) = \omega(f) = \omega(g)${{< /katex >}}.

Bibundles may be composed (I'll neglect to mention *how*),
but the composition is only associative up to isomorphism of bibundles.
If one thinks of isomorphisms between bibundles as being akin to natural transformations
(indeed, naturally isomorphic functors have isomorphic associated bibundles),
then the category of étale groupoids with arrows bibundles is what's called a *weak* {{< katex >}}$2${{< /katex >}}-category.

## The equivalence of the two approaches

This post is already quite long, but I wanted to explain how to see that bibundles
give rise to generalized maps in our sense.
So let {{< katex >}}$X \colon \mathcal{G} \to \mathcal{H}${{< /katex >}} be a bibundle.
For each {{< katex >}}$p \in \mathcal{G}_0${{< /katex >}}, there is a local section {{< katex >}}$s_p\colon U_p \to X${{< /katex >}}
defined on a neighborhood of {{< katex >}}$p${{< /katex >}}.
Consider the open cover {{< katex >}}$\mathcal{U} = \{U_p\}_{p \in \mathcal{G}_0}${{< /katex >}} of {{< katex >}}$\mathcal{G}_0${{< /katex >}},
and the space

{{< katex >}}$$X^{\mathcal{U}} = \mathcal{G}^{\mathcal{U}}_0 \times_{\mathcal{G}_0} X
= \{ (p_i,x) \in \mathcal{G}^{\mathcal{U}}_0 \times X : p = a_L(x) \}$${{< /katex  >}}

We claim that map {{< katex >}}$(p_i,x) \mapsto p_i${{< /katex >}} makes {{< katex >}}$X^{\mathcal{U}}${{< /katex >}} into a principal {{< katex >}}$\mathcal{H}${{< /katex >}}-bundle,
where the anchor is {{< katex >}}$(p_i,x) \mapsto a_R(x)${{< /katex >}} and the action is {{< katex >}}$(p_i,x).h = (p_i,x.h)${{< /katex >}}. 
Notice that {{< katex >}}$p = a_L(x.h) = a_L(x)${{< /katex >}} since {{< katex >}}$X${{< /katex >}} is {{< katex >}}$\mathcal{H}${{< /katex >}}-principal, so this is well-defined,
and clearly {{< katex >}}$\mathcal{H}${{< /katex >}}-invariant.
Now consider the map {{< katex >}}$((p_i,x),h) \mapsto ((p_i,x),(p_i,x.h))${{< /katex >}}.
Since {{< katex >}}$(x,h) \mapsto (x,x.h)${{< /katex >}} is a homeomorphism, this map will also be a homeomorphism,
proving the claim.

There is a left action of {{< katex >}}$\mathcal{G}^{\mathcal{U}}${{< /katex >}} on {{< katex >}}$X^{\mathcal{U}}${{< /katex >}}
where the anchor is {{< katex >}}$(p_i,x) \mapsto p_i${{< /katex >}} and the action is {{< katex >}}$g_{j,i}.(p_i,x) = (\omega(g_{j,i}),g.x)${{< /katex >}}. 
By the definition of the left action of {{< katex >}}$\mathcal{G}${{< /katex >}} on {{< katex >}}$X${{< /katex >}}, this is well-defined.
It is clear that the left and right actions commute; we have already shown that {{< katex >}}$X^{\mathcal{U}}${{< /katex >}}
is {{< katex >}}$\mathcal{H}${{< /katex >}}-principal,
and we have {{< katex >}}$(\omega(g_{j,i}),g.x) \mapsto a_R(g.x) = a_R (x)${{< /katex >}}, so the right anchor is left invariant.
Therefore we have a bibundle {{< katex >}}$X^{\mathcal{U}} \colon \mathcal{G}^{\mathcal{U}} \to \mathcal{H}${{< /katex >}}.

The bibundle {{< katex >}}$X^{\mathcal{U}}${{< /katex >}} has a global section {{< katex >}}$p_i \mapsto (p_i,s_i(p))${{< /katex >}}.
If {{< katex >}}$(p_i,x)${{< /katex >}} is another point of {{< katex >}}$X^{\mathcal{U}}${{< /katex >}},
since {{< katex >}}$X^{\mathcal{U}} \times_{\mathcal{H}_0} \mathcal{H}_1${{< /katex >}} is homeomorphic to
{{< katex >}}$X^{\mathcal{U}}\times_{\mathcal{G}^{\mathcal{U}}_0} X^{\mathcal{U}}${{< /katex >}},
there exists a unique arrow {{< katex >}}$h \in \mathcal{H}_1${{< /katex >}} such that {{< katex >}}$(p_i,x) = (p_i,s_i(p)).h${{< /katex >}}.
We claim the map {{< katex >}}$(p_i,x) \mapsto (p_i,h)${{< /katex >}}
from {{< katex >}}$X^{\mathcal{U}}${{< /katex >}} to

{{< katex >}}$\{ (p_i,h) \in \mathcal{G}^{\mathcal{U}}_0\times \mathcal{H}_1 : a_R(s_i(p)) = \omega(h) \}${{< /katex >}}

is a homeomorphism. Indeed, the map {{< katex >}}$(p_i,h) \mapsto (p_i,s_i(p).h)${{< /katex >}} is its inverse.
We claim that the rule {{< katex >}}$\phi_0(p_i) = a_R(s_i(p))${{< /katex >}} defines the action on objects of a functor
{{< katex >}}$\mathcal{G}^{\mathcal{U}} \to \mathcal{H}${{< /katex >}}.
The action on arrows sends {{< katex >}}$g_{j,i} \colon x_i \to y_j${{< /katex >}} to the unique arrow {{< katex >}}$\phi_1(g_{j,i})${{< /katex >}} such that
{{< katex >}}$g_{j,i} . (x_i, s_i(x)) = (y_j, s_j(y)).\phi_1(g_{j,i})${{< /katex >}}.
Given {{< katex >}}$f_{k,j} \colon y_j \to z_k${{< /katex >}}, notice that

{{< katex >}}$$f_{k,j} . g_{j,i} . (x_i, s_i(x)) = f_{k,j} . (y_j, s_j(y)). \phi_1(g_{j,i}) 
= (z_k, s_k(z)) . \phi_1(f_{k,j}) . \phi_1(g_{j,i})$${{< /katex >}}

since the left and right actions commute.
On the other hand,

{{< katex >}}$ (f_{k,j}g_{j,i}) . (x_i, s_i(x)) = (z_k,s_k(z)) .\phi_1(f_{k,j}g_{j,i})${{< /katex >}}

so since the left action is associative, {{< katex >}}$\phi_1${{< /katex >}} indeed defines a functor! Cute.

[étale]: {{< ref "graphs-of-groups-as-etale-groupoids.md" >}}
[axiom of choice]: {{< ref "the-axiom-of-choice-is-false-for-manifolds.md" >}}
[category of fractions]: https://ncatlab.org/nlab/show/calculus+of+fractions
[Lerman]: https://ems.press/content/serial-article-files/6839
