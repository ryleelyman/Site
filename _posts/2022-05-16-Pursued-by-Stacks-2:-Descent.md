---
layout: post
math: true
---
A stack, so I'm told, is a category fibered in groupoids satisfying some extra conditions.
The stacks we're interested in are *geometric* stacks, so this won't be the last post on stacks,
but with any luck we'll see the definition in this post.

Let $$\mathsf{C}$$ be a category fibered in groupoids over $$\mathbf{Top}$$.
We say an object $$\xi \in \mathsf{C}$$ is *over* a space $$X$$
if $$\pi(\xi) = X$$.
Both Lerman and Fantechi adopt the following convention:
for every continuous map $$f\colon Y \to X$$ and every object $$\xi$$ over $$X$$,
we choose a lift $$f_\xi \colon f^*\xi \to \xi$$
that we call "the" pullback of $$\xi$$ along $$f$$.

Notice that if we had another choice $$f'\colon \xi' \to \xi$$ of pullback,
then in $$\mathbf{Top}$$ we have the following rather silly commutative diagram

$$\require{AMScd}\begin{CD}
Y @>f>> X \\
@| @| \\
Y @>f>> X,
\end{CD}$$

so by the second item in the definition of a category fibered in groupoids,
there are unique maps $$g\colon f^*\xi \to \xi'$$ and $$g'\colon \xi' \to f^*\xi$$
such that, for example, the following diagram commutes

$$\begin{CD}
f^*\xi @>f_\xi>> \xi \\
@VgVV @| \\
\xi' @>f'>> \xi.
\end{CD}$$

It's not hard to see that $$g$$ and $$g'$$ are therefore inverse isomorphisms.
By the way, if $$f$$ is the identity of $$X$$, we see that this argument implies that
the category of objects above $$X$$ is a groupoid: every arrow is an isomorphism.
Hence the name, I suppose.
In fact, if $$f\colon Y \to X$$ is a continuous map
and $$\alpha\colon \xi \to \xi'$$ is an arrow (necessarily an isomorphism)
of objects over $$X$$, a clever application of the second item again shows that
there is a unique isomorphism $$f^*\alpha\colon f^*\xi \to f^*\xi'$$
such that the following diagram commutes

$$\begin{CD}
f^*\xi @>f_\xi>> \xi \\
@VVf^*\alpha V @VV\alpha V \\
f^*\xi' @>f_{\xi'}>> \xi'.
\end{CD}$$

Notice as well that we do not require (and probably cannot in general)
that $$g^*f^*\xi = (fg)^*\xi$$, merely that they are canonically isomorphic.

## Descent data

The idea of descent is that given, say, a vector bundle defined 
open set by open set on a space $$X$$
satisfying certain gluing conditions,
this data *descends* to a vector bundle on $$X$$.

More formally, let $$\mathcal{U} = \{U_i\}_{i\in I}$$ be an open cover of $$X$$,
and for each $$i$$, let $$\iota_i \colon U_i \to X$$ be the inclusion.
We have inclusions $$\iota_{ji}\colon (U_j \cap U_i) \to U_j$$
and $$\iota_{ij}\colon (U_j \cap U_i) \to U_i$$ for each double intersection
and $$\iota^i_{ijk}$$, $$\iota^j_{ijk}$$ and $$\iota^k_{ijk}$$ for inclusions from the triple
intersection $$U_i \cap U_j \cap U_k$$ to the various double intersections,
where the superscript indicates the omitted subscript in the target of the inclusion.
A *descent datum* for $$\mathsf{C}$$ over $$X$$ is the following.
- An object $$\xi_i$$ over $$U_i$$ for each $$i$$.
- For each pair $$i$$ and $$j$$, an isomorphism 
$$\alpha_{ji} \colon \iota_{ij}^*\xi_i \to \iota_{ji}^*\xi_j$$
in the fiber over $$U_i \cap U_j$$.
- The isomorphisms above satisfy the *cocycle condition*
(so named for reasons of Čech cohomology probably, so way over my head)

$$(\iota_{ijk}^j)^*\alpha_{ki} = (\iota_{ijk}^i)^*\alpha_{kj} \circ (\iota_{ijk}^k)^*\alpha_{ji}$$

The descent datum is *effective* if there exists an object $$\xi$$ over $$X$$
with isomorphisms $$\alpha_i \colon \iota_i^*\xi \to \xi_i$$ in the fiber over $$U_i$$
with the property that $$\alpha_{ji} = \iota_{ji}^*\alpha_j\circ (\iota_{ij}^*\alpha_i)^{-1}$$.

In plainer words, a *descent datum* is that open set by open set construction 
of something you'd like to exist in $$\mathsf{C}$$,
and saying that the descent datum is *effective* says that the wished-for object really exists
and is moreover obtained by gluing together it patch by patch.

Finally, we say that *isomorphisms are a sheaf* for $$\mathsf{C}$$ if,
roughly, isomorphisms between elements of $$\mathsf{C}$$ over any space $$X$$
are determined uniquely by their restriction to any open cover of $$X$$.
More formally,
we require that for any space $$X$$, 
every pair of objects $$\xi$$ and $$\xi'$$ in the fiber over $$X$$,
every open cover $$\{U_i\}_{i \in I}$$ of $$X$$
and every collection of isomorphisms $$\alpha_i\colon \iota_i^*\xi \to \iota_i^*\xi'$$
with the property that $$\iota_{ij}^*\alpha_i = \iota_{ji}^*\alpha_j$$
on $$U_i \cap U_j$$,
there exists a unique isomorphism $$\alpha\colon \xi \to \xi'$$
such that $$\iota_i^*\alpha = \alpha_i$$.

Our category fibered in groupoids $$\mathsf{C}$$ is a *stack*
if isomorphisms are a sheaf and every descent datum is effective.

A map of stacks $$\mathsf{C} \to \mathsf{D}$$ over $$\mathbf{Top}$$ is a functor
$$F\colon \mathsf{C} \to \mathsf{D}$$ with the property that
$$\pi F = \pi$$, where we abuse notation by writing both $$\pi\colon \mathsf{C} \to \mathbf{Top}$$
and $$\pi\colon \mathsf{D} \to \mathbf{Top}$$.
A *natural transformation* of maps $$F$$, $$G\colon \mathsf{C} \to \mathsf{D}$$
is a natural transformation $$\eta\colon F \Rightarrow G$$
with the property that for each $$\xi \in \mathsf{C}$$,
we have $$\pi(\eta_\xi) = 1_{\pi(\xi)}$$.
Notice that because $$F\xi$$ and $$G\xi$$ are in the fiber over $$\pi(\xi)$$,
the map $$\eta_\xi$$ is automatically an isomorphism,
so all natural transformations are natural isomorphisms.
An *isomorphism* of stacks is an equivalence of categories over $$\mathbf{Top}$$,
i.e. $$F\colon \mathsf{C} \to \mathsf{D}$$ is full, faithful and essentially surjective.
Since we love the [axiom of choice] around here,
this is equivalent to the existence of an inverse functor up to natural isomorphism.

[pullbacks]: {% link _posts/2021-06-17-Pullbacks-and-Intersections.md %}
[axiom of choice]: {% link _posts/2020-08-02-The-Axiom-of-Choice-is-False-for-Manifolds.md %}
