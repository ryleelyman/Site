---
title: "Two Approaches to the Cotangent Space"
date: 2020-07-10T13:38:06-04:00
math: true
---
There is a "sheaf-theoretic" definition of something like a *cotangent space at a point*
for a locally-ringed space.
In the case of the sheaf of differentiable functions on a smooth manifold,
the two definitions—sheaf-theoretic and the usual one in differential geometry—agree.
What's more, modulo the appropriate background technology in both subjects,
the proof is beautiful and simple—I feel like shouting it from the rooftops
at the moment, so this blog post will try and give a little exposition.
I'll try to move briskly without assuming total familiarity with either side of things.

## The Algebraic Cotangent Space

Let {{< katex >}}$X${{< /katex >}} be a smooth manifold of dimension {{< katex >}}$n${{< /katex >}}.
The *sheaf* of differentiable functions on {{< katex >}}$X${{< /katex >}} is a
contravariant functor from the category of open subsets of {{< katex >}}$X${{< /katex >}} to the category of rings
that assigns to an open set {{< katex >}}$U${{< /katex >}}
the ring {{< katex >}}$\mathscr{O}(U)${{< /katex >}} of differentiable functions {{< katex >}}$f\colon U \to \mathbb{R}${{< /katex >}}—addition
and multiplication in {{< katex >}}$\mathscr{O}(U)${{< /katex >}} are done pointwise in {{< katex >}}$\mathbb{R}${{< /katex >}}.

The sheaf is not so important for us;
what we are interested in today are the *stalks.*
The idea is that elements of the *stalk,*
called *germs,* capture the "infinitesimal behavior"
of smooth functions at a point.
Here is the formal definition.
Given a point {{< katex >}}$p \in X${{< /katex >}}, 
the *stalk* of *germs* of smooth functions at {{< katex >}}$p${{< /katex >}} is the ring

{{< katex >}}$$ \mathscr{O}_p = \{(f,U) : f \in \mathscr{O}(U),\ p\in U \}/\sim. $${{< /katex >}}

The equivalence relation {{< katex >}}$\sim${{< /katex >}} is defined as follows:
we say {{< katex >}}$(f,U) \sim (g,V)${{< /katex >}} if there exists an open neighborhood
{{< katex >}}$U' \subset U \cap V${{< /katex >}} such that {{< katex >}}$f|_{U'} = g|_{U'}${{< /katex >}}.
The equivalence class of {{< katex >}}$(f,U)${{< /katex >}} is its *germ.*
The ring {{< katex >}}$\mathscr{O}_p${{< /katex >}} is the direct limit of the {{< katex >}}$\mathscr{O}(U)${{< /katex >}}
as {{< katex >}}$U${{< /katex >}} varies over the open neighborhoods of {{< katex >}}$p${{< /katex >}}.

Notice that there is a surjection {{< katex >}}$\mathscr{O}_p \to \mathbb{R}${{< /katex >}}
that sends the germ of {{< katex >}}$f${{< /katex >}} at {{< katex >}}$p${{< /katex >}} to {{< katex >}}$f(p)\in \mathbb{R}${{< /katex >}}.
The definition is independent of the choice of representative {{< katex >}}$f${{< /katex >}}.
Since {{< katex >}}$\mathbb{R}${{< /katex >}} is a field, the kernel of the map
is a maximal ideal; let's call it {{< katex >}}$\mathfrak{m}_p${{< /katex >}}.
Observe that 
{{< katex >}}$\mathfrak{m}_p/\mathfrak{m}_p^2${{< /katex >}} is a module over
{{< katex >}}$\mathscr{O}_p/\mathfrak{m}_p \cong \mathbb{R}${{< /katex >}}, 
i.e. a real vector space;
we will call it the *algebraic cotangent space at {{< katex >}}$p${{< /katex >}}.*

## The Usual Cotangent Space

We retain our manifold {{< katex >}}$X${{< /katex >}} and point {{< katex >}}$p${{< /katex >}} from the previous section.
The *tangent space at {{< katex >}}$p${{< /katex >}},* denoted {{< katex >}}$T_pX${{< /katex >}}
can be thought of as the space of "directions" in {{< katex >}}$X${{< /katex >}} at {{< katex >}}$p${{< /katex >}}.
This is made precise by defining it to be the space of
directional *derivatives* at {{< katex >}}$p${{< /katex >}}.
I won't attempt to make this more precise, except to note that
after we choose local coordinates {{< katex >}}$(x_1,\dotsc,x_n)${{< /katex >}} near {{< katex >}}$p = (p_1,\dotsc,p_n)${{< /katex >}},
a basis for {{< katex >}}$T_pX${{< /katex >}} is given by

{{< katex >}}$$ \frac{\partial}{\partial x_1}\bigg|_p,\dotsc, \frac{\partial}{\partial x_n}\bigg|_p. $${{< /katex >}}


The *cotangent space,* which we are more interested in, is the
*dual* of the tangent space and is denoted {{< katex >}}$T_p^\ast X${{< /katex >}}.
Elements of the cotangent space are *linear functionals* on tangent vectors.
Given coordinates {{< katex >}}$x_1,\dotsc,x_n${{< /katex >}},
the *dual basis* of the cotangent space is given by

{{< katex >}}$$ dx_1,\dotsc, dx_n, $${{< /katex >}}

so we have {{< katex >}}$dx_i\left( \frac{\partial}{\partial x_j}|_p\right)${{< /katex >}} equal to {{< katex >}}$1${{< /katex >}}
when {{< katex >}}$i = j${{< /katex >}} and equal to {{< katex >}}$0${{< /katex >}} otherwise.
(There perhaps ought to be some notational inclusion of the point {{< katex >}}$p${{< /katex >}},
but we will suppress this.)

## The Algebraic Cotangent Space Agrees With the Usual One

If {{< katex >}}$f${{< /katex >}} is a smooth function on an open neighborhood of {{< katex >}}$p${{< /katex >}}
satisfying {{< katex >}}$f(p) = 0${{< /katex >}},
abusing notation, we shall write the corresponding element of
{{< katex >}}$\mathfrak{m}_p/\mathfrak{m}_p^2${{< /katex >}}
as {{< katex >}}$f + \mathfrak{m}_p^2${{< /katex >}}.
Given such an element,
I claim we can interpret {{< katex >}}$f${{< /katex >}} as a linear functional on tangent vectors at {{< katex >}}$p${{< /katex >}}
by sending a tangent vector {{< katex >}}$v${{< /katex >}} to the value of the derivative of {{< katex >}}$f${{< /katex >}} at {{< katex >}}$p${{< /katex >}} in the direction {{< katex >}}$v${{< /katex >}}.
For instance, in local coordinates {{< katex >}}$(x_1,\dotsc,x_n)${{< /katex >}},
the vector {{< katex >}}$\frac{\partial}{\partial x_i}|_p${{< /katex >}} is sent to {{< katex >}}$ \frac{\partial f}{\partial x_i}(p) ${{< /katex >}}.
Extending linearly defines a linear functional on {{< katex >}}$T_pX${{< /katex >}},
which we shall denote {{< katex >}}$df_p${{< /katex >}}.
The value of the directional derivative of a function depends only on its germ
essentially by definition,
and the product rule from calculus tells us that the assignment
{{< katex >}}$f \mapsto df_p${{< /katex >}} sends elements of {{< katex >}}$\mathfrak{m}_p^2${{< /katex >}} to the zero functional.
The linearity of the derivative implies that {{< katex >}}$\mathbb{R}${{< /katex >}}-linear combinations
of germs are sent to {{< katex >}}$\mathbb{R}${{< /katex >}}-linear combinations of functionals,
so the assignment

{{< katex >}}$$ f + \mathfrak{m}_p^2 \mapsto df_p $${{< /katex >}}

really defines a map {{< katex >}}$\mathfrak{m}_p/\mathfrak{m}_p^2 \to T_p^\ast X${{< /katex >}}.

We claim this map is an isomorphism, for which it suffices to define an inverse.
Choose local coordinates {{< katex >}}$\vec x = (x_1,\dotsc,x_n)${{< /katex >}} around {{< katex >}}$\vec p = (p_1,\dotsc,p_n)${{< /katex >}}.
A general element {{< katex >}}$\alpha${{< /katex >}} of {{< katex >}}$T_p^\ast X${{< /katex >}}
may be written as the linear combination
{{< katex >}}$ \alpha = a_1\mathop{dx_1} + \dotsb + a_n\mathop{dx_n}. ${{< /katex >}}
Write {{< katex >}}$\vec a = (a_1,\dotsc,a_n)${{< /katex >}}.
The function {{< katex >}}$f_\alpha${{< /katex >}} defined as

{{< katex >}}$$ f_\alpha(\vec x) = \vec a\cdot(\vec x - \vec p) $${{< /katex >}}

clearly has germ belonging to {{< katex >}}$\mathfrak{m}_p${{< /katex >}},
and tracing the double composition,
we see that we have {{< katex >}}$a \mapsto f_\alpha + \mathfrak{m}_p^2 \mapsto d(f_\alpha)_p = \alpha${{< /katex >}}.
This map will be an isomorphism as soon as we can show that the germ of
{{< katex >}}$f - f_{df_p}${{< /katex >}} belongs to {{< katex >}}$\mathfrak{m}_p^2${{< /katex >}}, i.e.
can be written as {{< katex >}}$ g_1h_1 + \dotsb g_kh_k${{< /katex >}} for some
smooth functions {{< katex >}}$g_i${{< /katex >}} and {{< katex >}}$h_i${{< /katex >}} whose germs belong to {{< katex >}}$\mathfrak{m}_p${{< /katex >}}.
This is the statement of Taylor's theorem!

Even better, the map {{< katex >}}$\mathfrak{m}_p/\mathfrak{m}_p^2 \to T_p^\ast X${{< /katex >}}
is a *natural isomorphism,* in the sense that given a smooth map
{{< katex >}}$\varphi\colon X \to Y${{< /katex >}} of smooth manifolds such that
{{< katex >}}$\varphi(p) = q${{< /katex >}}, the following diagram commutes

{{< katex >}}$$
	\begin{CD}
		\mathfrak{m}_q/\mathfrak{m}_q^2 @>{\cong}>> T_q^\ast Y \\
		@VV{\varphi^\ast}V @VV{\varphi^\ast}V \\
		\mathfrak{m}_p/\mathfrak{m}_p^2 @>{\cong}>> T_p^\ast X.
	\end{CD}
$${{< /katex >}}

To verify this, we shall follow an element {{< katex >}}$f + \mathfrak{m}_q^2${{< /katex >}}
around the diagram

{{< katex >}}$$
	\begin{CD}
		f + \mathfrak{m}^2_q @>>> df_q \\
		@VVV @VVV \\
		f\varphi + \mathfrak{m}_p^2 @>>> d(f\varphi)_p = \mathop{df_q}\mathop{d\varphi_p},
	\end{CD}
$${{< /katex >}}

and the fact that equality holds is the multi-variable chain rule!

Having exploited our knowledge of undegraduate calculus to prove a satisfying
natural isomorphism,
I'll leave you with one final reason this proof excites me.
If we had wanted to, we could have replaced "differentiable" with "continuous"
in our definition of the algebraic cotangent space,
and we would still end up with a real vector space associated to every stalk.
In some sense, I guessed that this says that the only reason one never speaks of a (co)tangent
space associated to a point in a general topological space is that
there's no reason—like Taylor's theorem—for the space to be finite-dimensional!

Actually, the truth is slightly more subtle:
every continuous function has a continuous "square root" in the sense
that we can always write {{< katex >}}$f(x) = \operatorname{sgn}(f(x))\sqrt{f(x)}\sqrt{f(x)}${{< /katex >}},
and the functions {{< katex >}}$\sqrt{f}${{< /katex >}} and {{< katex >}}$\operatorname{sgn}(f)\sqrt(f)${{< /katex >}} are continuous.
Therefore it is {{< katex >}}$\mathfrak{m}_p${{< /katex >}} that is infinite-dimensional,
while {{< katex >}}$\mathfrak{m}_p/\mathfrak{m}_p^2 = 0${{< /katex >}}.
(Thanks to Curtis Heberle and Christopher Davis for pointing out my error!)



