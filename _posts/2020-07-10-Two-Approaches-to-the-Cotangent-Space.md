---
layout: post
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

Let $$X$$ be a smooth manifold of dimension $$n$$.
The *sheaf* of differentiable functions on $$X$$ is a
contravariant functor from the category of open subsets of $$X$$ to the category of rings
that assigns to an open set $$U$$
the ring $$\mathscr{O}(U)$$ of differentiable functions $$f\colon U \to \mathbb{R}$$—addition
and multiplication in $$\mathscr{O}(U)$$ are done pointwise in $$\mathbb{R}$$.

The sheaf is not so important for us;
what we are interested in today are the *stalks.*
The idea is that elements of the *stalk,*
called *germs,* capture the "infinitesimal behavior"
of smooth functions at a point.
Here is the formal definition.
Given a point $$p \in X$$, 
the *stalk* of *germs* of smooth functions at $$p$$ is the ring

$$ \mathscr{O}_p = \{(f,U) : f \in \mathscr{O}(U),\ p\in U \}/\sim. $$

The equivalence relation $$\sim$$ is defined as follows:
we say $$(f,U) \sim (g,V)$$ if there exists an open neighborhood
$$U' \subset U \cap V$$ such that $$f|_{U'} = g|_{U'}$$.
The equivalence class of $$(f,U)$$ is its *germ.*
The ring $$\mathscr{O}_p$$ is the direct limit of the $$\mathscr{O}(U)$$
as $$U$$ varies over the open neighborhoods of $$p$$.

Notice that there is a surjection $$\mathscr{O}_p \to \mathbb{R}$$
that sends the germ of $$f$$ at $$p$$ to $$f(p)\in \mathbb{R}$$.
The definition is independent of the choice of representative $$f$$.
Since $$\mathbb{R}$$ is a field, the kernel of the map
is a maximal ideal; let's call it $$\mathfrak{m}_p$$.
Observe that 
$$\mathfrak{m}_p/\mathfrak{m}_p^2$$ is a module over
$$\mathscr{O}_p/\mathfrak{m}_p \cong \mathbb{R}$$, 
i.e. a real vector space;
we will call it the *algebraic cotangent space at $$p$$.*

## The Usual Cotangent Space

We retain our manifold $$X$$ and point $$p$$ from the previous section.
The *tangent space at $$p$$,* denoted $$T_pX$$
can be thought of as the space of "directions" in $$X$$ at $$p$$.
This is made precise by defining it to be the space of
directional *derivatives* at $$p$$.
I won't attempt to make this more precise, except to note that
after we choose local coordinates $$(x_1,\dotsc,x_n)$$ near $$p = (p_1,\dotsc,p_n)$$,
a basis for $$T_pX$$ is given by

$$ \frac{\partial}{\partial x_1}\bigg|_p,\dotsc, \frac{\partial}{\partial x_n}\bigg|_p. $$


The *cotangent space,* which we are more interested in, is the
*dual* of the tangent space and is denoted $$T_p^\ast X$$.
Elements of the cotangent space are *linear functionals* on tangent vectors.
Given coordinates $$x_1,\dotsc,x_n$$,
the *dual basis* of the cotangent space is given by

$$ dx_1,\dotsc, dx_n, $$

so we have $$dx_i\left( \frac{\partial}{\partial x_j}|_p\right)$$ equal to $$1$$
when $$i = j$$ and equal to $$0$$ otherwise.
(There perhaps ought to be some notational inclusion of the point $$p$$,
but we will suppress this.)

## The Algebraic Cotangent Space Agrees With the Usual One

If $$f$$ is a smooth function on an open neighborhood of $$p$$
satisfying $$f(p) = 0$$,
abusing notation, we shall write the corresponding element of
$$\mathfrak{m}_p/\mathfrak{m}_p^2$$
as $$f + \mathfrak{m}_p^2$$.
Given such an element,
I claim we can interpret $$f$$ as a linear functional on tangent vectors at $$p$$
by sending a tangent vector $$v$$ to the value of the derivative of $$f$$ at $$p$$ in the direction $$v$$.
For instance, in local coordinates $$(x_1,\dotsc,x_n)$$,
the vector $$\frac{\partial}{\partial x_i}|_p$$ is sent to $$ \frac{\partial f}{\partial x_i}(p) $$.
Extending linearly defines a linear functional on $$T_pX$$,
which we shall denote $$df_p$$.
The value of the directional derivative of a function depends only on its germ
essentially by definition,
and the product rule from calculus tells us that the assignment
$$f \mapsto df_p$$ sends elements of $$\mathfrak{m}_p^2$$ to the zero functional.
The linearity of the derivative implies that $$\mathbb{R}$$-linear combinations
of germs are sent to $$\mathbb{R}$$-linear combinations of functionals,
so the assignment

$$ f + \mathfrak{m}_p^2 \mapsto df_p $$

really defines a map $$\mathfrak{m}_p/\mathfrak{m}_p^2 \to T_p^\ast X$$.

We claim this map is an isomorphism, for which it suffices to define an inverse.
Choose local coordinates $$\vec x = (x_1,\dotsc,x_n)$$ around $$\vec p = (p_1,\dotsc,p_n)$$.
A general element $$\alpha$$ of $$T_p^\ast X$$
may be written as the linear combination
$$ \alpha = a_1\mathop{dx_1} + \dotsb + a_n\mathop{dx_n}. $$
Write $$\vec a = (a_1,\dotsc,a_n)$$.
The function $$f_\alpha$$ defined as

$$ f_\alpha(\vec x) = \vec a\cdot(\vec x - \vec p) $$

clearly has germ belonging to $$\mathfrak{m}_p$$,
and tracing the double composition,
we see that we have $$a \mapsto f_\alpha + \mathfrak{m}_p^2 \mapsto d(f_\alpha)_p = \alpha$$.
This map will be an isomorphism as soon as we can show that the germ of
$$f - f_{df_p}$$ belongs to $$\mathfrak{m}_p^2$$, i.e.
can be written as $$ g_1h_1 + \dotsb g_kh_k$$ for some
smooth functions $$g_i$$ and $$h_i$$ whose germs belong to $$\mathfrak{m}_p$$.
This is the statement of Taylor's theorem!

Even better, the map $$\mathfrak{m}_p/\mathfrak{m}_p^2 \to T_p^\ast X$$
is a *natural isomorphism,* in the sense that given a smooth map
$$\varphi\colon X \to Y$$ of smooth manifolds such that
$$\varphi(p) = q$$, the following diagram commutes

$$\require{AMScd}
	\begin{CD}
		\mathfrak{m}_q/\mathfrak{m}_q^2 @>{\cong}>> T_q^\ast Y \\
		@VV{\varphi^\ast}V @VV{\varphi^\ast}V \\
		\mathfrak{m}_p/\mathfrak{m}_p^2 @>{\cong}>> T_p^\ast X.
	\end{CD}
$$

To verify this, we shall follow an element $$f + \mathfrak{m}_q^2$$
around the diagram

$$
	\begin{CD}
		f + \mathfrak{m}^2_q @>>> df_q \\
		@VVV @VVV \\
		f\varphi + \mathfrak{m}_p^2 @>>> d(f\varphi)_p = \mathop{df_q}\mathop{d\varphi_p},
	\end{CD}
$$

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
that we can always write $$f(x) = \operatorname{sgn}(f(x))\sqrt{f(x)}\sqrt{f(x)}$$,
and the functions $$\sqrt{f}$$ and $$\operatorname{sgn}(f)\sqrt(f)$$ are continuous.
Therefore it is $$\mathfrak{m}_p$$ that is infinite-dimensional,
while $$\mathfrak{m}_p/\mathfrak{m}_p^2 = 0$$.
(Thanks to Curtis Heberle and Christopher Davis for pointing out my error!)

