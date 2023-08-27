---
title: "Pursued by Stacks 2: Descent"
date: 2022-05-16T15:37:33-04:00
math: true
---
A stack, so I'm told, is a category fibered in groupoids satisfying some extra conditions.
The stacks we're interested in are *geometric* stacks, so this won't be the last post on stacks,
but with any luck we'll see the definition in this post.

Let {{< katex >}}$\mathsf{C}${{< /katex >}} be a category fibered in groupoids over {{< katex >}}$\mathbf{Top}${{< /katex >}}.
We say an object {{< katex >}}$\xi \in \mathsf{C}${{< /katex >}} is *over* a space {{< katex >}}$X${{< /katex >}}
if {{< katex >}}$\pi(\xi) = X${{< /katex >}}.
Both Lerman and Fantechi adopt the following convention:
for every continuous map {{< katex >}}$f\colon Y \to X${{< /katex >}} and every object {{< katex >}}$\xi{{< katex >}}$ over ${{< /katex >}}X${{< /katex >}},
we choose a lift {{< katex >}}$f_\xi \colon f^*\xi \to \xi${{< /katex >}}
that we call "the" pullback of {{< katex >}}$\xi{{< katex >}}$ along ${{< /katex >}}f${{< /katex >}}.

Notice that if we had another choice {{< katex >}}$f'\colon \xi' \to \xi${{< /katex >}} of pullback,
then in {{< katex >}}$\mathbf{Top}${{< /katex >}} we have the following rather silly commutative diagram

{{< katex >}}$$\begin{CD}
Y @>f>> X \\
@| @| \\
Y @>f>> X,
\end{CD}$${{< /katex >}}

so by the second item in the definition of a category fibered in groupoids,
there are unique maps {{< katex >}}$g\colon f^*\xi \to \xi'{{< katex >}}$ and ${{< /katex >}}g'\colon \xi' \to f^*\xi${{< /katex >}}
such that, for example, the following diagram commutes

{{< katex >}}$$\begin{CD}
f^*\xi @>f_\xi>> \xi \\
@VgVV @| \\
\xi' @>f'>> \xi.
\end{CD}$${{< /katex >}}

It's not hard to see that {{< katex >}}$g{{< katex >}}$ and ${{< /katex >}}g'${{< /katex >}} are therefore inverse isomorphisms.
By the way, if {{< katex >}}$f{{< katex >}}$ is the identity of ${{< /katex >}}X${{< /katex >}}, we see that this argument implies that
the category of objects above {{< katex >}}$X${{< /katex >}} is a groupoid: every arrow is an isomorphism.
Hence the name, I suppose.
In fact, if {{< katex >}}$f\colon Y \to X${{< /katex >}} is a continuous map
and {{< katex >}}$\alpha\colon \xi \to \xi'${{< /katex >}} is an arrow (necessarily an isomorphism)
of objects over {{< katex >}}$X${{< /katex >}}, a clever application of the second item again shows that
there is a unique isomorphism {{< katex >}}$f^*\alpha\colon f^*\xi \to f^*\xi'${{< /katex >}}
such that the following diagram commutes

{{< katex >}}$$\begin{CD}
f^*\xi @>f_\xi>> \xi \\
@VVf^*\alpha V @VV\alpha V \\
f^*\xi' @>f_{\xi'}>> \xi'.
\end{CD}$${{< /katex >}}

Notice as well that we do not require (and probably cannot in general)
that {{< katex >}}$g^*f^*\xi = (fg)^*\xi${{< /katex >}}, merely that they are canonically isomorphic.

## Descent data

The idea of descent is that given, say, a vector bundle defined 
open set by open set on a space {{< katex >}}$X${{< /katex >}}
satisfying certain gluing conditions,
this data *descends* to a vector bundle on {{< katex >}}$X${{< /katex >}}.

More formally, let {{< katex >}}$\mathcal{U} = \{U_i\}_{i\in I}{{< katex >}}$ be an open cover of ${{< /katex >}}X${{< /katex >}},
and for each {{< katex >}}$i{{< katex >}}$, let ${{< /katex >}}\iota_i \colon U_i \to X${{< /katex >}} be the inclusion.
We have inclusions {{< katex >}}$\iota_{ji}\colon (U_j \cap U_i) \to U_j${{< /katex >}}
and {{< katex >}}$\iota_{ij}\colon (U_j \cap U_i) \to U_i${{< /katex >}} for each double intersection
and {{< katex >}}$\iota^i_{ijk}{{< katex >}}$, ${{< /katex >}}\iota^j_{ijk}{{< katex >}}$ and ${{< /katex >}}\iota^k_{ijk}${{< /katex >}} for inclusions from the triple
intersection {{< katex >}}$U_i \cap U_j \cap U_k${{< /katex >}} to the various double intersections,
where the superscript indicates the omitted subscript in the target of the inclusion.
A *descent datum* for {{< katex >}}$\mathsf{C}{{< katex >}}$ over ${{< /katex >}}X${{< /katex >}} is the following.
- An object {{< katex >}}$\xi_i{{< katex >}}$ over ${{< /katex >}}U_i{{< katex >}}$ for each ${{< /katex >}}i${{< /katex >}}.
- For each pair {{< katex >}}$i{{< katex >}}$ and ${{< /katex >}}j${{< /katex >}}, an isomorphism 
{{< katex >}}$\alpha_{ji} \colon \iota_{ij}^*\xi_i \to \iota_{ji}^*\xi_j${{< /katex >}}
in the fiber over {{< katex >}}$U_i \cap U_j${{< /katex >}}.
- The isomorphisms above satisfy the *cocycle condition*
(so named for reasons of Čech cohomology probably, so way over my head)

{{< katex >}}$(\iota_{ijk}^j)^*\alpha_{ki} = (\iota_{ijk}^i)^*\alpha_{kj} \circ (\iota_{ijk}^k)^*\alpha_{ji}${{< /katex >}}

The descent datum is *effective* if there exists an object {{< katex >}}$\xi{{< katex >}}$ over ${{< /katex >}}X${{< /katex >}}
with isomorphisms {{< katex >}}$\alpha_i \colon \iota_i^*\xi \to \xi_i{{< katex >}}$ in the fiber over ${{< /katex >}}U_i${{< /katex >}}
with the property that {{< katex >}}$\alpha_{ji} = \iota_{ji}^*\alpha_j\circ (\iota_{ij}^*\alpha_i)^{-1}${{< /katex >}}.

In plainer words, a *descent datum* is that open set by open set construction 
of something you'd like to exist in {{< katex >}}$\mathsf{C}${{< /katex >}},
and saying that the descent datum is *effective* says that the wished-for object really exists
and is moreover obtained by gluing together it patch by patch.

Finally, we say that *isomorphisms are a sheaf* for {{< katex >}}$\mathsf{C}${{< /katex >}} if,
roughly, isomorphisms between elements of {{< katex >}}$\mathsf{C}{{< katex >}}$ over any space ${{< /katex >}}X${{< /katex >}}
are determined uniquely by their restriction to any open cover of {{< katex >}}$X${{< /katex >}}.
More formally,
we require that for any space {{< katex >}}$X${{< /katex >}}, 
every pair of objects {{< katex >}}$\xi{{< katex >}}$ and ${{< /katex >}}\xi'{{< katex >}}$ in the fiber over ${{< /katex >}}X${{< /katex >}},
every open cover {{< katex >}}$\{U_i\}_{i \in I}{{< katex >}}$ of ${{< /katex >}}X${{< /katex >}}
and every collection of isomorphisms {{< katex >}}$\alpha_i\colon \iota_i^*\xi \to \iota_i^*\xi'${{< /katex >}}
with the property that {{< katex >}}$\iota_{ij}^*\alpha_i = \iota_{ji}^*\alpha_j${{< /katex >}}
on {{< katex >}}$U_i \cap U_j${{< /katex >}},
there exists a unique isomorphism {{< katex >}}$\alpha\colon \xi \to \xi'${{< /katex >}}
such that {{< katex >}}$\iota_i^*\alpha = \alpha_i${{< /katex >}}.

Our category fibered in groupoids {{< katex >}}$\mathsf{C}${{< /katex >}} is a *stack*
if isomorphisms are a sheaf and every descent datum is effective.

A map of stacks {{< katex >}}$\mathsf{C} \to \mathsf{D}{{< katex >}}$ over ${{< /katex >}}\mathbf{Top}${{< /katex >}} is a functor
{{< katex >}}$F\colon \mathsf{C} \to \mathsf{D}${{< /katex >}} with the property that
{{< katex >}}$\pi F = \pi{{< katex >}}$, where we abuse notation by writing both ${{< /katex >}}\pi\colon \mathsf{C} \to \mathbf{Top}${{< /katex >}}
and {{< katex >}}$\pi\colon \mathsf{D} \to \mathbf{Top}${{< /katex >}}.
A *natural transformation* of maps {{< katex >}}$F{{< katex >}}$, ${{< /katex >}}G\colon \mathsf{C} \to \mathsf{D}${{< /katex >}}
is a natural transformation {{< katex >}}$\eta\colon F \Rightarrow G${{< /katex >}}
with the property that for each {{< katex >}}$\xi \in \mathsf{C}${{< /katex >}},
we have {{< katex >}}$\pi(\eta_\xi) = 1_{\pi(\xi)}${{< /katex >}}.
Notice that because {{< katex >}}$F\xi{{< katex >}}$ and ${{< /katex >}}G\xi{{< katex >}}$ are in the fiber over ${{< /katex >}}\pi(\xi)${{< /katex >}},
the map {{< katex >}}$\eta_\xi${{< /katex >}} is automatically an isomorphism,
so all natural transformations are natural isomorphisms.
An *isomorphism* of stacks is an equivalence of categories over {{< katex >}}$\mathbf{Top}${{< /katex >}},
i.e. {{< katex >}}$F\colon \mathsf{C} \to \mathsf{D}${{< /katex >}} is full, faithful and essentially surjective.
Since we love the [axiom of choice] around here,
this is equivalent to the existence of an inverse functor up to natural isomorphism.

[pullbacks]: {{< ref "pullbacks-and-intersections.md" >}}
[axiom of choice]: {{< ref "the-axiom-of-choice-is-false-for-manifolds.md" >}}
