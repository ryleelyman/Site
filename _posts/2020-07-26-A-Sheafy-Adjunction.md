---
layout: post
math: true
---
Given a topological space $$X$$ and a continuous map $$\pi\colon X \to Y$$,
there is an adjunction between the categories of sheaves on $$X$$ and sheaves on $$Y$$.
The adjunction is somewhat mysterious to me as I begin to write this,
so the hope is that by writing about it, I'll begin to understand.

The functors in question are the *pushforward* and *inverse image* functors,
which arise naturally in algebraic geometry (so I am led to believe).
What makes the adjunction difficult to understand is that the definitions
of the functors in question don't seem to play nicely with each other.

The proof (with a little setting the stage) appears below.
The method of proof, like most category-theoretic proofs,
is a story of careful bookkeeping with functors and natural transformations,
along with simple calculations to check.
The idea essentially seems to be that the 
unit $$\eta_\mathscr{F} \colon \mathscr{F} \to \pi_\ast\pi^{-1}\mathscr{F}$$
"shreds a section $$f$$ into pieces," while the counit
$$\epsilon_{\mathscr{G}} \colon \pi^{-1}\pi_\ast\mathscr{G} \to \mathscr{G}$$
recognizes that these "shredded up" sections assemble into sections of $$\mathscr{G}$$.


## Adjunctions
Remember, given categories $$C$$ and $$D$$, a pair of functors
$$F \colon C \to D$$ and $$G \colon D \to C$$ form an *adjoint pair*
when there exists an isomorphism

$$D(Fc,d) \cong C(c,Gd)$$

which is natural in $$c$$ and $$d$$.
We say $$F$$ is *left adjoint* to $$G$$,
or equivalently that $$G$$ is *right adjoint* to $$F$$.
In particular, setting $$d = Fc$$, we have

$$D(Fc,Fc) \cong C(c,GFc).$$

which gives us a natural transformation $$\eta \colon 1_C \Longrightarrow GF$$.
Similarly, we have $$\epsilon\colon FG \Longrightarrow 1_D$$.
The natural transformation $$\eta$$ is called the *unit* of the adjunction,
and $$\epsilon$$ is the *counit.*
In fact, the existence of these natural transformations
could be taken to be the *definition* of an adjunction,
provided the natural transformations satisfy the identities

$$\epsilon F \circ F\eta = 1_F \quad\text{and}\quad G\epsilon \circ \eta G = 1_G,$$

which says that for all $$c \in C$$ and $$d \in D$$, the compositions

$$\require{AMScd}
\begin{CD}
Fc @>{F\eta_c}>> FGFc @>{\epsilon_{Fc}}>> Fc
\end{CD}$$

and 

$$\begin{CD}
Gd @>{\eta_{Gd}}>> GFGd @>{G\epsilon_d}>> Gd
\end{CD}$$

are the identity.

My goal in this blog post is to show that the functors I am interested in
satisfy this latter definition of an adjunction.

## Sheaves
Given a pair of spaces $$X$$ and $$Y$$, and a continuous map $$\pi \colon X \to Y$$,
we have functors $$\pi_\ast \colon \operatorname{Sh}_X \to \operatorname{Sh}_Y$$
and $$\pi^{-1}\colon \operatorname {Sh}_Y \to \operatorname{Sh}_X$$ from the category
of sheaves on $$X$$ to the category of sheaves on $$Y$$ and *vice versa.*
The former is simple to describe: if $$\mathscr{F}$$ is a sheaf on $$X$$,
the sheaf $$\pi_\ast\mathscr{F}$$ on $$Y$$ is the assignment

$$U \mapsto \mathscr{F}(\pi^{-1}(U))$$

for all open subsets $$U$$ of $$Y$$.

The latter is slightly more complicated.
Recall that if $$\mathscr{F}$$ is a sheaf on $$Y$$,
there is a space $$F$$ equipped with a local homeomorphism $$\rho \colon F \to Y$$.
The sheaf $$\mathscr{F}$$ is the sheaf of local sections of $$\rho$$;
$$F$$ is called the *espace étale* for the sheaf $$\mathscr{F}$$.
The set of points of $$F$$ above $$y \in Y$$ is the *stalk* $$\mathscr{F}_y$$.

Thus a section $$s \colon U \to F$$ is an element $$(s_y)_{y \in U}$$ of $$\prod_{y \in U} \mathscr{F}_y$$.
Continuity of $$s$$ is the condition that for all $$y \in U$$, there exists
an open neighborhood $$U_y$$ of $$y$$ and an element $$f \in \mathscr{F}(U_y)$$
such that $$f_x = s_x$$ for all $$x \in U_y$$.

Given that $$F$$ and $$X$$ admit maps to $$Y$$, we can form their pullback,

$$\begin{CD}
\pi^{-1}F @>>> F \\
@VVV @VV{\rho}V \\
X @>{\pi}>> Y
\end{CD}$$

which as a set is  $$\{ (x,f_y) \in X \times F : \pi(x) = y\}$$.
The topology on $$\pi^{-1}F$$ is induced from the product topology on $$X \times F$$.
The sheaf $$\pi^{-1}\mathscr{F}$$ is the sheaf of sections of $$\pi^{-1}F \to X$$.
The universal property of the pullback ensures that this really defines a functor
from the category of sheaves on $$Y$$ to the category of sheaves on $$X$$.

The claim is that $$\pi^{-1}$$ is left adjoint to $$\pi_\ast$$.
Therefore we should expect natural transformations
$$\eta \colon 1_{\operatorname{Sh}_Y} \Longrightarrow \pi_\ast\pi^{-1}$$
and $$\epsilon \colon \pi^{-1}\pi_\ast \Longrightarrow 1_{\operatorname{Sh}_X}$$.

### The Unit of the Adjunction

So let $$\mathscr{F}$$ be a sheaf on $$Y$$.
A section $$s \colon \pi^{-1}(U) \to \pi^{-1}F$$
is a map 

$$x \mapsto (x,s_{\pi(x)}) \qquad\text{for } x \in \pi^{-1}(U),\  s_{\pi(X)} \in \mathscr{F}_{\pi(x)}$$

satisfying the following compatibility condition:
for each point $$x \in \pi^{-1}(U)$$, there exists
an open neighborhood $$V_x \subset \pi^{-1}(U)$$ containing $$x$$
and an open neighborhood $$U_x$$ in $$Y$$ such that
$$\pi(V_x) \subset U_x$$.
Furthermore there exists a section $$f \in \mathscr{F}(U_x)$$
such that $$f_{\pi(v)} = s_{\pi(v)}$$ for all $$v \in V_x$$.

In particular, if $$U \subset Y$$ is an open set and $$f$$ is a section in
$$\mathscr{F}(U)$$, the assignment $$x \mapsto (x,f_{\pi(x)})$$ for $$x \in \pi^{-1}(U)$$
defines a section in $$\pi_\ast\pi^{-1}\mathscr{F}(U) = \pi^{-1}\mathscr{F}(\pi^{-1}(U))$$.
Let us thus define a map $$\eta_{\mathscr{F}}(U)\colon \mathscr{F}(U) \to \pi_\ast\pi^{-1}\mathscr{F}(U)$$ 
by the rule

$$\eta_{\mathscr{F}}(U)(f) = [x \mapsto (x,f_{\pi(x)}),\ x \in \pi^{-1}(U)].$$

(Let's parse the notation: a natural transformation $$\eta$$ yields
a map of sheaves $$\eta_{\mathscr{F}}$$ for each sheaf $$\mathscr{F}$$.
This is the definition of that map on the open subset $$U \subset Y$$.)

To prove the claim that $$\eta$$ is a natural transformation,
we need to show that given a map $$\phi \colon \mathscr{F} \to \mathscr{F}'$$
of sheaves on $$Y$$, the following diagram commutes

$$\begin{CD}
\mathscr{F} @>{\eta_{\mathscr{F}}}>> \pi_\ast\pi^{-1}\mathscr{F} \\
@V{\phi}VV @VV{\pi_\ast\pi^{-1}\phi}V \\
\mathscr{F}' @>{\eta_{\mathscr{F}'}}>> \pi_\ast\pi^{-1}\mathscr{F}'.
\end{CD}$$

Given $$f \in \mathscr{F}(U)$$, the upper right path of the square sends
$$f$$ to $$[x \mapsto (x,f_{\pi(x)})]$$ and then to
$$[x \mapsto (x,\phi_{\pi(x)}(f_{\pi(x)}))]$$ in $$\pi_\ast\pi^{-1}\mathscr{F}'(U)$$.
On the other hand, the lower left path of the square
sends $$f$$ first to $$\phi(U)(f)$$ and then to
$$[x \mapsto (x,(\phi(U)(f))_{\pi(x)})]$$ in $$\pi_\ast\pi^{-1}\mathscr{F}'(U)$$.
The equality

$$(\phi(U)(f))_{\pi(x)} = \phi_{\pi(x)}(f_{\pi(x)})$$

holds pointwise, since taking the stalk at $$x$$ is functorial.

### The Counit of the Adjunction

Now suppose that $$\mathscr{G}$$ is a sheaf on $$X$$.
Let $$\pi_\ast G$$ denote the *espace étale* over $$Y$$ for the sheaf $$\pi_\ast\mathscr{G}$$.

A section $$s \colon V \to \pi^{-1}\pi_\ast G$$ is a map

$$x \mapsto (x,s_{\pi(x)}) \qquad\text{for } x \in V,\ s_{\pi(x)} \in \pi_\ast\mathscr{G}_{\pi(x)}$$

satisfying the following compatibility condition:
for each point $$x \in V$$, there exists an open neighborhood $$V_x \subset V$$
containing $$x$$ and an open neighborhood $$U_x$$ in $$Y$$
such that $$\pi(V_x) \subset U_x$$.
Furthermore there exists a section $$g \in \pi_\ast\mathscr{G}(U_x) = \mathscr{G}(\pi^{-1}(U_x))$$
such that $$g_{\pi(v)} = s_{\pi(v)}$$ for all $$v \in V_x$$.

Since the sets $$\pi^{-1}(U_x)$$ cover $$V$$ by assumption,
sheafiness of $$\mathscr{G}$$ implies the existence of a unique $$g \in \mathscr{G}(V)$$
such that $$g_x$$ is equal to the image of $$s_{\pi(x)}$$
under the natural map $$\pi_\ast\mathscr{G}_{\pi(x)} \to \mathscr{G}_x$$.
Let us thus define a map $$\epsilon_{\mathscr{G}}(V) \colon \pi^{-1}\pi_\ast\mathscr{G}(V) \to \mathscr{G}(V)$$
sending $$[x \mapsto (x,s_{\pi(x)})]$$ to $$g$$.

We claim that $$\epsilon$$ defines a natural transformation from $$\pi^{-1}\pi_\ast\mathscr{G}$$ to $$\mathscr{G}$$.
To prove the claim, we need to show that given a map $$\psi\colon \mathscr{G} \to \mathscr{G}'$$
of sheaves on $$X$$, the following diagram commutes

$$\begin{CD}
\pi^{-1}\pi_\ast\mathscr{G} @>{\epsilon_{\mathscr{G}}}>> \mathscr{G} \\
@V{\pi^{-1}\pi_\ast\psi}VV @VV{\psi}V \\
\pi^{-1}\pi_\ast \mathscr{G}' @>{\epsilon_{\mathscr{G}'}}>> \mathscr{G}'.
\end{CD}$$

Given $$[x \mapsto (x,s_{\pi(x)})] \in \pi^{-1}\pi_\ast\mathscr{G}(V)$$,
the upper right path of the square sends us first to some $$g \in \mathscr{G}(V)$$
such that $$g_x$$ is the image of $$s_{\pi(x)}$$ in $$\mathscr{G}_x$$ for all $$x \in V$$,
and then sends $$g$$ to $$\psi(V)(g) \in \mathscr{G}'(V)$$.
On the other hand, the lower left path of the square sends
$$[x \mapsto (x,s_{\pi(x)})]$$ first to $$[x \mapsto (x,(\pi_\ast\psi)_{\pi(x)}(s_{\pi(x)}))]$$
in $$\pi^{-1}\pi_\ast\mathscr{G}'(V)$$, and then to
some $$g' \in \mathscr{G}'(V)$$ such that $$g'_x$$ is the image of
$$(\pi_\ast\psi)_{\pi(x)}(s_{\pi(x)})$$ in $$\mathscr{G}'_x$$ for all $$x \in V$$.

If $$U \subset Y$$ is an open set containing $$\pi(x)$$ such that
$$s \in \pi_\ast\mathscr{G}(U) = \mathscr{G}(\pi^{-1}(U))$$ 
represents $$s_{\pi(x)}$$ for $$\pi(x) \in U$$,
we have $$(\pi_\ast\psi)_{\pi(x)}(s_{\pi(x)}) = \psi(\pi^{-1}(U))(s)_{\pi(x)}$$.
Furthermore we know that $$g \in \mathscr{G}(V)$$ 
is such that the image of $$s_{\pi(x)}$$ in $$\mathscr{G}_x$$
is $$g_x$$ for all $$x \in V$$.
Therefore we have that
the image of $$\psi(\pi^{-1}(U))(s)_{\pi(x)}$$
in $$\mathscr{G}'_x$$ is equal to $$\psi(V)(g)_x$$,
as desired.

## The inverse image--pushforward adjunction

To conclude, we just need to show that two double compositions
of natural transformations are the identity.
The first, translated into our particular case,
says that if $$\mathscr{F}$$ is a sheaf on $$Y$$,
we have that

$$\begin{CD}
\pi^{-1}\mathscr{F} @>{\pi^{-1}\eta_{\mathscr{F}}}>> \pi^{-1}\pi_\ast\pi^{-1}\mathscr{F} @>{\epsilon_{\pi^{-1}\mathscr{F}}}>>
\pi^{-1}\mathscr{F}
\end{CD}$$

is equal to the identity.
If $$V \subset X$$ is an open set and
$$[x \mapsto (x,s_{\pi(x)})] \in \pi^{-1}\mathscr{F}(V)$$ is a section,
where $$s_{\pi(x)}$$ is an element of the stalk $$\mathscr{F}_{\pi(x)}$$.
The first map sends this section to the section

$$[x \mapsto (x,\eta_{\pi(x)}(s_{\pi(x)}))] \in \pi^{-1}\pi_\ast\pi^{-1}\mathscr{F}(V).$$

The second map sends this section to the unique section $$f$$ in $$\pi^{-1}\mathscr{F}(V)$$
whose image in the stalk at $$\pi(x)$$ is equal to $$\eta_{\pi(x)}(s_{\pi(x)})$$.
But $$\eta$$ is defined such that this is exactly the assignment $$[x \mapsto (x,s_{\pi(x)})]$$!
So far so good.

The second double composition we need to show is equal to the identity is defined 
for a sheaf $$\mathscr{G}$$ on $$X$$ as follows

$$\begin{CD}
\pi_\ast\mathscr{G} @>{\eta_{\pi_\ast\mathscr{G}}}>> \pi_\ast\pi^{-1}\pi_\ast\mathscr{G}
@>{\pi_\ast\epsilon_{\mathscr{G}}}>> \pi_\ast\mathscr{G}.
\end{CD}$$

If $$U \subset Y$$ is an open set and $$g \in \pi_\ast\mathscr{G}(U) = \mathscr{G}(\pi^{-1}(U))$$
is a section,
the first map sends $$g$$ to the section

$$[x \mapsto (x,g_\pi(x))] \in \pi^{-1}\pi_\ast\mathscr{G}(\pi^{-1}(U)) = \pi_\ast\pi^{-1}\pi_\ast\mathscr{G}(U).$$

The second map sends this section to the unique section in $$\mathscr{G}(\pi^{-1}(U)) = \pi_\ast\mathscr{G}(U)$$
whose image in the stalk at $$\pi(x)$$ is $$g_\pi(x)$$. Indeed, $$g$$ is that section!

This completes the proof that inverse image and pushforward form an adjoint pair of functors.
