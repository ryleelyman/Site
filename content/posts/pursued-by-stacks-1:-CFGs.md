---
title: "Pursued by Stacks 1: CFGs"
date: 2022-05-16T15:34:36-04:00
math: true
---
I've spent the past couple years on and off understanding how to think of graphs of groups
and orbifolds as (being represented by) étale groupoids.
In view of [Lerman's critique], to which his answer is the category of geometric stacks over manifolds,
I thought it might be relevant to try and understand what a stack is.
This is the first in what will likely be several posts towards understanding the definition of a stack;
this one is focused on the concept of a *category fibered in groupoids.*

## Categories fibered in groupoids

Let {{< katex >}}$\mathbf{Top}${{< /katex >}} denote the category of compactly generated topological spaces and continuous maps.
(All spaces I tend to think about are compactly generated, being either manifolds or CW complexes,
so this is not a serious restriction for me.
That being said, I don't immediately understand the desire to restrict to compactly generated spaces,
because my algebraic topology is not strong in that direction.)

A functor {{< katex >}}$\pi \colon \mathsf{C} \to \mathbf{Top}${{< /katex >}} 
is a *category fibered in groupoids over {{< katex >}}$\mathbf{Top}${{< /katex >}}*
if the following conditions hold.

- Given a continuous map {{< katex >}}$f\colon X \to Y${{< /katex >}} and an object {{< katex >}}$\xi \in \mathsf{C}${{< /katex >}}
    with {{< katex >}}$\pi(\xi) = Y${{< /katex >}},
    there is an arrow {{< katex >}}$\tilde f \colon \zeta \to \xi${{< /katex >}} in {{< katex >}}$\mathsf{C}${{< /katex >}} such that
    {{< katex >}}$\pi(\tilde f) = f${{< /katex >}}.
    Apparently we are supposed to think of {{< katex >}}$\zeta${{< /katex >}} as a *pullback* of {{< katex >}}$\xi${{< /katex >}} along {{< katex >}}$f${{< /katex >}}.
- Given a diagram of the following form

{{< katex >}}$$\begin{CD}
        \xi'' @>f>> \xi \\
        @. @| \\
        \xi' @>h>> \xi
\end{CD}$${{< /katex >}}

in {{< katex >}}$\mathsf{C}${{< /katex >}} such that there exists a continuous map {{< katex >}}$g\colon \pi(\xi'') \to \pi(\xi')${{< /katex >}}
making the following diagram commute

{{< katex >}}$$\begin{CD}
    \pi(\xi'') @>\pi(f)>> \pi(\xi) \\
    @VgVV @| \\
    \pi(\xi') @>\pi(h)>> \pi(\xi),
\end{CD}$${{< /katex >}}

There exists a unique arrow {{< katex >}}$\tilde g\colon \xi'' \to \xi'${{< /katex >}}
such that {{< katex >}}$h\tilde g = f${{< /katex >}} and {{< katex >}}$\pi(\tilde g) = g${{< /katex >}}.
In other words, there is a unique way to lift the map {{< katex >}}$g${{< /katex >}} to make the diagram commute in {{< katex >}}$\mathsf{C}${{< /katex >}}.

In understanding stacks, I'm trying to follow [Lerman's paper] 
and also [Fantechi's survey paper], so there are two main examples:
Lerman gives the example of the category {{< katex >}}$\mathsf{B}\mathcal{G}${{< /katex >}} of principal {{< katex >}}$\mathcal{G}${{< /katex >}}-bundles
with arrows {{< katex >}}$\mathcal{G}${{< /katex >}}-equivariant maps.
Fantechi gives the example of vector bundles of rank {{< katex >}}$r${{< /katex >}} and bundle isomorphisms.
I'll give Fantechi's example.

## Example: Vector bundles of constant rank

Recall that a *vector bundle of rank {{< katex >}}$r${{< /katex >}}* over a topological space {{< katex >}}$X${{< /katex >}}
is a space {{< katex >}}$E${{< /katex >}} equipped with a continuous surjection {{< katex >}}$\pi\colon E \to X${{< /katex >}}
such that for each point {{< katex >}}$x \in X${{< /katex >}}, the space {{< katex >}}$\pi^{-1}(x)${{< /katex >}} is a real vector space of dimension {{< katex >}}$r${{< /katex >}}
and such that for each {{< katex >}}$x \in X${{< /katex >}}, there exists an open neighborhood {{< katex >}}$U${{< /katex >}} of {{< katex >}}$x${{< /katex >}}
and a homeomorphism {{< katex >}}$\varphi\cong U\times \mathbb{R}^r \to \pi^{-1}(U)${{< /katex >}}
with the property that {{< katex >}}$\pi\varphi(y,\vec v) = y${{< /katex >}}
and the property that the map {{< katex >}}$\vec v \mapsto \varphi(y,\vec v)${{< /katex >}} is a linear isomorphism
from {{< katex >}}$\mathbb{R}^r${{< /katex >}} to {{< katex >}}$\pi^{-1}(y)${{< /katex >}}
for all {{< katex >}}$y \in U${{< /katex >}}.

There is a category {{< katex >}}$\mathsf{Vect}_r${{< /katex >}} of rank-{{< katex >}}$r${{< /katex >}} vector bundles
where the arrows are *vector bundle maps of rank {{< katex >}}$r${{< /katex >}}:* commutative diagrams of the form

{{< katex >}}$$\begin{CD}
E_1 @>\tilde f>> E_2 \\
@VV\pi_1V @VV\pi_2V \\
X_1 @>f>> X_2
\end{CD}$${{< /katex >}}

with the property that each map {{< katex >}}$\pi_1^{-1}(x) \to \pi_2^{-1}(f(x))${{< /katex >}} is a linear isomorphism of vector spaces.
We will abuse notation, writing {{< katex >}}$\tilde f\colon E_1 \to E_2${{< /katex >}} to mean the bundle map above.

The claim is that the functor (also called {{< katex >}}$\pi${{< /katex >}}) 
sending a rank-{{< katex >}}$r${{< /katex >}} vector bundle {{< katex >}}$\pi\colon E \to X${{< /katex >}} to its base {{< katex >}}$X${{< /katex >}}
defines a category fibered in groupoids over {{< katex >}}$\mathbf{Top}${{< /katex >}}.

To see this, suppose that {{< katex >}}$\pi\colon E \to X${{< /katex >}} is a vector bundle and {{< katex >}}$f\colon Y \to X${{< /katex >}} is a continuous map.
We need a pullback {{< katex >}}$\tilde f \colon \xi \to E${{< /katex >}} for some vector bundle {{< katex >}}$\xi${{< /katex >}} over {{< katex >}}$Y${{< /katex >}}.
Let us take the literal pullback, that is,

{{< katex >}}$ \xi = \{ (y,e) \in Y \times E : f(y) = \pi(e) \}${{< /katex >}}

There is an obvious projection {{< katex >}}$\pi\colon \xi \to Y${{< /katex >}} given by projection to the first factor.
Given {{< katex >}}$x \in X${{< /katex >}}, let {{< katex >}}$U${{< /katex >}} be the neighborhood of {{< katex >}}$x${{< /katex >}} 
with the homeomorphism {{< katex >}}$\varphi \colon U \times \mathbb{R}^r \to \pi^{-1}(U)${{< /katex >}}.
Write {{< katex >}}$V = f^{-1}(U)${{< /katex >}} and define
{{< katex >}}$\psi\colon V \times \mathbb{R}^r \to \pi^{-1}(V)${{< /katex >}} by the rule

{{< katex >}}$\psi(y,\vec v) = (y,(\varphi(f(y),\vec v)).${{< /katex >}}

It is clear that {{< katex >}}$\pi\psi(y,\vec v) = y${{< /katex >}} for all {{< katex >}}$y \in V${{< /katex >}}.
Conversely, given {{< katex >}}$(y,e) \in \pi^{-1}(V)${{< /katex >}}, note that {{< katex >}}$\varphi^{-1}(e) = (f(y),\vec v)${{< /katex >}} 
for some {{< katex >}}$\vec v \in \mathbb{R}^r${{< /katex >}};
put another way, the map {{< katex >}}$(y,e) \mapsto (y,\vec v)${{< /katex >}}, where {{< katex >}}$\vec v${{< /katex >}} is the {{< katex >}}$\mathbb{R}^r${{< /katex >}} component
of {{< katex >}}$\varphi^{-1}(e)${{< /katex >}}, is an inverse homeomorphism for {{< katex >}}$\psi${{< /katex >}}.
The map {{< katex >}}$\vec v \mapsto \psi(y,\vec v)${{< /katex >}} is a linear isomorphism because {{< katex >}}$\vec v \mapsto \varphi(f(y),\vec v)${{< /katex >}}
is a linear isomorphism.
Therefore {{< katex >}}$\xi${{< /katex >}} is a rank-{{< katex >}}$r${{< /katex >}} vector bundle over {{< katex >}}$Y${{< /katex >}}.

There is a map {{< katex >}}$\tilde f \colon \xi \to E${{< /katex >}} given by projection to the second factor.
The map {{< katex >}}$\pi^{-1}(y) \to \pi^{-1}(f(y))${{< /katex >}} given by {{< katex >}}$(y, e) \mapsto e${{< /katex >}} is a linear isomorphism.
To see this, note that we have the following commutative diagram

{{< katex >}}$$\begin{CD}
\pi^{-1}(y) @>f>> \pi^{-1}(f(y)) \\
@A\psi AA @A\varphi AA \\
\mathbb{R}^r @= \mathbb{R}^r
\end{CD}
\qquad
\begin{CD}
\psi(y,\vec v) @>>> \varphi(f(y),\vec v) \\
@AAA @AAA \\
\vec v @= \vec v
\end{CD}$${{< /katex >}}

and the vertical maps are isomorphisms.
Therefore the map {{< katex >}}$\tilde f\colon \xi \to E${{< /katex >}} is an arrow of {{< katex >}}$\mathsf{Vect}_r${{< /katex >}}.

Given maps of vector bundles {{< katex >}}$\tilde f\colon \xi'' \to \xi${{< /katex >}} and {{< katex >}}$\tilde h\colon \xi' \to \xi${{< /katex >}}
such that there exists a continuous map {{< katex >}}$g \colon \pi(\xi'') \to \pi(x')${{< /katex >}} making the following diagram commute

{{< katex >}}$$\begin{CD}
\pi(\xi'') @>f>> \pi(\xi) \\
@VVgV @| \\
\pi(\xi') @>h>> \pi(\xi),
\end{CD}$${{< /katex >}}

we claim that there is a unique bundle map {{< katex >}}$\tilde g\colon \xi'' \to \xi'${{< /katex >}} making the appropriate diagram commute.
Given {{< katex >}}$x \in \pi(\xi'')${{< /katex >}}, note that {{< katex >}}$\tilde f${{< /katex >}} and {{< katex >}}$\tilde g${{< /katex >}}
induce linear isomorphisms {{< katex >}}$\pi^{-1}(x) \to \pi^{-1}(f(x))${{< /katex >}} and 
{{< katex >}}$\pi^{-1}(g(x)) \to \pi^{-1}(hg(x)) = \pi^{-1}(f(x))${{< /katex >}}.
Call these isomorphisms {{< katex >}}$f_x${{< /katex >}} and {{< katex >}}$h_{g(x)}${{< /katex >}}.
Therefore define {{< katex >}}$\tilde g${{< /katex >}} as

{{< katex >}}$\tilde g(\tilde x) = h_{g(\pi(\tilde x))}^{-1}f_{\pi(\tilde x)}(\tilde x)${{< /katex >}}.

It is clear that {{< katex >}}$\tilde g${{< /katex >}} is a bundle map making the relevant diagram commute
and that conversely {{< katex >}}$\tilde g${{< /katex >}} is the only definition we could have made.
Therefore {{< katex >}}$\mathsf{Vect}_r${{< /katex >}} defines a category fibered in groupoids over {{< katex >}}$\mathbf{Top}${{< /katex >}}.

[Lerman's critique]: {{< ref "more-maps:-Lerman's-critique.md" >}}
[Lerman's paper]: https://ems.press/content/serial-article-files/6839
[Fantechi's survey paper]: https://www.math.uni-bielefeld.de/~rehmann/ECM/cdrom/3ecm/pdfs/pant3/fantechi.pdf
