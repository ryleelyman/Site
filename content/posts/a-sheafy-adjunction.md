---
title: "A Sheafy Adjunction"
date: 2020-07-26T13:47:07-04:00
math: true
---
Given a topological space {{< katex >}}$X${{< /katex >}} and a continuous map {{< katex >}}$\pi\colon X \to Y${{< /katex >}},
there is an adjunction between the categories of sheaves on {{< katex >}}$X${{< /katex >}} and sheaves on {{< katex >}}$Y${{< /katex >}}.
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
unit {{< katex >}}$\eta_\mathscr{F} \colon \mathscr{F} \to \pi_\ast\pi^{-1}\mathscr{F}${{< /katex >}}
"shreds a section {{< katex >}}$f${{< /katex >}} into pieces," while the counit
{{< katex >}}$\epsilon_{\mathscr{G}} \colon \pi^{-1}\pi_\ast\mathscr{G} \to \mathscr{G}${{< /katex >}}
recognizes that these "shredded up" sections assemble into sections of {{< katex >}}$\mathscr{G}${{< /katex >}}.


## Adjunctions
Remember, given categories {{< katex >}}$C${{< /katex >}} and {{< katex >}}$D${{< /katex >}}, a pair of functors
{{< katex >}}$F \colon C \to D${{< /katex >}} and {{< katex >}}$G \colon D \to C${{< /katex >}} form an *adjoint pair*
when there exists an isomorphism

{{< katex >}}$D(Fc,d) \cong C(c,Gd)${{< /katex >}}

which is natural in {{< katex >}}$c${{< /katex >}} and {{< katex >}}$d${{< /katex >}}.
We say {{< katex >}}$F${{< /katex >}} is *left adjoint* to {{< katex >}}$G${{< /katex >}},
or equivalently that {{< katex >}}$G${{< /katex >}} is *right adjoint* to {{< katex >}}$F${{< /katex >}}.
In particular, setting {{< katex >}}$d = Fc${{< /katex >}}, we have

{{< katex >}}$D(Fc,Fc) \cong C(c,GFc).${{< /katex >}}

which gives us a natural transformation {{< katex >}}$\eta \colon 1_C \Longrightarrow GF${{< /katex >}}.
Similarly, we have {{< katex >}}$\epsilon\colon FG \Longrightarrow 1_D${{< /katex >}}.
The natural transformation {{< katex >}}$\eta${{< /katex >}} is called the *unit* of the adjunction,
and {{< katex >}}$\epsilon${{< /katex >}} is the *counit.*
In fact, the existence of these natural transformations
could be taken to be the *definition* of an adjunction,
provided the natural transformations satisfy the identities

{{< katex >}}$\epsilon F \circ F\eta = 1_F \quad\text{and}\quad G\epsilon \circ \eta G = 1_G,${{< /katex >}}

which says that for all {{< katex >}}$c \in C${{< /katex >}} and {{< katex >}}$d \in D${{< /katex >}}, the compositions

{{< katex >}}$$
\begin{CD}
Fc @>{F\eta_c}>> FGFc @>{\epsilon_{Fc}}>> Fc
\end{CD}$${{< /katex >}}

and 

{{< katex >}}$$\begin{CD}
Gd @>{\eta_{Gd}}>> GFGd @>{G\epsilon_d}>> Gd
\end{CD}$${{< /katex >}}

are the identity.

My goal in this blog post is to show that the functors I am interested in
satisfy this latter definition of an adjunction.

## Sheaves
Given a pair of spaces {{< katex >}}$X${{< /katex >}} and {{< katex >}}$Y${{< /katex >}}, and a continuous map {{< katex >}}$\pi \colon X \to Y${{< /katex >}},
we have functors {{< katex >}}$\pi_\ast \colon \operatorname{Sh}_X \to \operatorname{Sh}_Y${{< /katex >}}
and {{< katex >}}$\pi^{-1}\colon \operatorname {Sh}_Y \to \operatorname{Sh}_X${{< /katex >}} from the category
of sheaves on {{< katex >}}$X${{< /katex >}} to the category of sheaves on {{< katex >}}$Y${{< /katex >}} and *vice versa.*
The former is simple to describe: if {{< katex >}}$\mathscr{G}${{< /katex >}} is a sheaf on {{< katex >}}$X${{< /katex >}},
the *pushforward sheaf* {{< katex >}}$\pi_\ast\mathscr{G}${{< /katex >}} on {{< katex >}}$Y${{< /katex >}} is the assignment

{{< katex >}}$U \mapsto \mathscr{F}(\pi^{-1}(U))${{< /katex >}}

for all open subsets {{< katex >}}$U${{< /katex >}} of {{< katex >}}$Y${{< /katex >}}.
If {{< katex >}}$\psi \colon \mathscr{G} \to \mathscr{G}'${{< /katex >}} is a morphism of sheaves on {{< katex >}}$X${{< /katex >}},
the morphism {{< katex >}}$\pi_\ast\psi${{< /katex >}} is defined by the rule

{{< katex >}}$(\pi_\ast\psi)(U) = \psi(\pi^{-1}(U)).${{< /katex >}}

The latter is slightly more complicated.
Recall that if {{< katex >}}$\mathscr{F}${{< /katex >}} is a sheaf on {{< katex >}}$Y${{< /katex >}},
there is a space {{< katex >}}$F${{< /katex >}} equipped with a local homeomorphism {{< katex >}}$\rho \colon F \to Y${{< /katex >}}.
The sheaf {{< katex >}}$\mathscr{F}${{< /katex >}} is the sheaf of local sections of {{< katex >}}$\rho${{< /katex >}};
{{< katex >}}$F${{< /katex >}} is called the *espace étalé* for the sheaf {{< katex >}}$\mathscr{F}${{< /katex >}}.
The set of points of {{< katex >}}$F${{< /katex >}} above {{< katex >}}$y \in Y${{< /katex >}} is the *stalk* {{< katex >}}$\mathscr{F}_y${{< /katex >}}.

As usual, a section {{< katex >}}$s\colon U \to F${{< /katex >}} of the projection {{< katex >}}$\rho \colon F \to X${{< /katex >}}
is an element {{< katex >}}$(s_y)_{y \in U}${{< /katex >}} of {{< katex >}}$\prod_{y \in U} \mathscr{F}_y${{< /katex >}}.
In our case, continuity of {{< katex >}}$s${{< /katex >}} is the following condition

{{< katex >}}$$\begin{equation}\label{star}\tag{$\ast$}
\text{for all } y \in U, \text{ there exists an open neighborhood }
U_y \text{ of } y\\  \text{ and } f\in\mathscr{F}(U_y) \text{ such that }
f_x = s_x \text{ for all } x \in U_y.
\end{equation}$${{< /katex >}}

Given that {{< katex >}}$F${{< /katex >}} and {{< katex >}}$X${{< /katex >}} admit maps to {{< katex >}}$Y${{< /katex >}}, we can form their pullback,

{{< katex >}}$$\begin{CD}
\pi^{-1}F @>>> F \\
@VVV @VV{\rho}V \\
X @>{\pi}>> Y
\end{CD}$${{< /katex >}}

which as a set is  {{< katex >}}$\{ (x,f_y) \in X \times F : \pi(x) = y\}${{< /katex >}}.
The topology on {{< katex >}}$\pi^{-1}F${{< /katex >}} is induced from the product topology on {{< katex >}}$X \times F${{< /katex >}}.
The *inverse image sheaf* {{< katex >}}$\pi^{-1}\mathscr{F}${{< /katex >}} is the sheaf of sections of {{< katex >}}$\pi^{-1}F \to X${{< /katex >}}.
The universal property of the pullback ensures that this really defines a functor
from the category of sheaves on {{< katex >}}$Y${{< /katex >}} to the category of sheaves on {{< katex >}}$X${{< /katex >}}.

Condition {{< katex >}}$\eqref{star}${{< /katex >}} for continuity of a section {{< katex >}}$s\colon V \to \pi^{-1}F${{< /katex >}}—that is,
a tuple {{< katex >}}$(s_{\pi(x)})_{x \in V}${{< /katex >}} in {{< katex >}}$\prod_{x \in V}\mathscr{F}_{\pi(x)}${{< /katex >}}—says
that for all {{< katex >}}$x \in V${{< /katex >}} there exists an open neighborhood {{< katex >}}$V_x${{< /katex >}} of {{< katex >}}$x${{< /katex >}}
and an open neighborhood {{< katex >}}$U_x${{< /katex >}} in {{< katex >}}$Y${{< /katex >}} such that {{< katex >}}$\pi(V_x) \subset U_x${{< /katex >}}.
Furthermore there exists a section {{< katex >}}$f \in \mathscr{F}(U_x)${{< /katex >}} 
such that {{< katex >}}$f_{\pi(v)} = s_{\pi(v)}${{< /katex >}} for all {{< katex >}}$v \in V_x${{< /katex >}}.

If {{< katex >}}$\phi\colon \mathscr{F} \to \mathscr{F}'${{< /katex >}} is a morphism of sheaves on {{< katex >}}$Y${{< /katex >}},
the resulting morphism {{< katex >}}$\pi^{-1}\phi \colon \pi^{-1}\mathscr{F} \to \pi^{-1}\mathscr{F}'${{< /katex >}}
is defined by 

{{< katex >}}$(\pi^{-1}\phi)(V)\left[(s_{\pi(x)})_{x \in V}\right] = \left(\phi_{\pi(x)}(s_{\pi(x)})\right)_{x \in V}.${{< /katex >}}

One needs to demonstrate that the right-hand side satisfies condition {{< katex >}}$\eqref{star}${{< /katex >}};
the check is simple, so I'll leave it to the reader.


The claim is that {{< katex >}}$\pi^{-1}${{< /katex >}} is left adjoint to {{< katex >}}$\pi_\ast${{< /katex >}}.
Therefore we should expect natural transformations
{{< katex >}}$\eta \colon 1_{\operatorname{Sh}_Y} \Longrightarrow \pi_\ast\pi^{-1}${{< /katex >}}
and {{< katex >}}$\epsilon \colon \pi^{-1}\pi_\ast \Longrightarrow 1_{\operatorname{Sh}_X}${{< /katex >}}.

### The Unit of the Adjunction

So let {{< katex >}}$\mathscr{F}${{< /katex >}} be a sheaf on {{< katex >}}$Y${{< /katex >}},
and let {{< katex >}}$U${{< /katex >}} be an open set in {{< katex >}}$Y${{< /katex >}}.
Since {{< katex >}}$\pi_\ast\pi^{-1}\mathscr{F}(U) = \pi^{-1}\mathscr{F}(\pi^{-1}(U))${{< /katex >}},
we can think of {{< katex >}}$s \in \pi_\ast\pi^{-1}\mathscr{F}(U)${{< /katex >}} as
a section {{< katex >}}$s \colon \pi^{-1}(U) \to \pi^{-1}F${{< /katex >}},
i.e. a tuple {{< katex >}}$(s_{\pi(x)})_{x \in \pi^{-1}(U)}${{< /katex >}}
satisfying the compatibility condition above.

Note that in particular if {{< katex >}}$U \subset Y${{< /katex >}} is open
and {{< katex >}}$f \in \mathscr{F}(U)${{< /katex >}}, the continuity condition {{< katex >}}$\eqref{star}${{< /katex >}}
for a section {{< katex >}}$\pi^{-1}(U)\to \pi^{-1}F${{< /katex >}} is satisfied by the section
{{< katex >}}$(f_{\pi(x)})_{x \in \pi^{-1}(U)}${{< /katex >}},
and thus defines an element of {{< katex >}}$\pi_\ast\pi^{-1}\mathscr{F}(U)${{< /katex >}}.

Let us thus define a map {{< katex >}}$\eta_{\mathscr{F}}(U)\colon \mathscr{F}(U) \to \pi_\ast\pi^{-1}\mathscr{F}(U)${{< /katex >}} 
as

{{< katex >}}$\eta_{\mathscr{F}}(U)(f) = (f_{\pi(x)})_{x\in\pi^{-1}(U)}.${{< /katex >}}

(Let's parse the notation: a natural transformation {{< katex >}}$\eta${{< /katex >}} yields
a map of sheaves {{< katex >}}$\eta_{\mathscr{F}}${{< /katex >}} for each sheaf {{< katex >}}$\mathscr{F}${{< /katex >}}.
This is the definition of that map on the open subset {{< katex >}}$U \subset Y${{< /katex >}}.)

To prove the claim that {{< katex >}}$\eta${{< /katex >}} is a natural transformation,
we need to show that given a map {{< katex >}}$\phi \colon \mathscr{F} \to \mathscr{F}'${{< /katex >}}
of sheaves on {{< katex >}}$Y${{< /katex >}}, the following diagram commutes

{{< katex >}}$$\begin{CD}
\mathscr{F} @>{\eta_{\mathscr{F}}}>> \pi_\ast\pi^{-1}\mathscr{F} \\
@V{\phi}VV @VV{\pi_\ast\pi^{-1}\phi}V \\
\mathscr{F}' @>{\eta_{\mathscr{F}'}}>> \pi_\ast\pi^{-1}\mathscr{F}'.
\end{CD}$${{< /katex >}}

Given {{< katex >}}$f \in \mathscr{F}(U)${{< /katex >}}, commutativity of the square is the claim that
the following equality holds

{{< katex >}}$$ \left((\phi(U)(f))_{\pi(x)}\right)_{x \in \pi^{-1}(U)} 
= \left(\phi_{\pi(x)}(f_{\pi(x)})\right)_{x \in \pi^{-1}(U)}.$${{< /katex >}}

This is in fact true, since taking the stalk at {{< katex >}}$x${{< /katex >}} is functorial.

### The Counit of the Adjunction

Now suppose that {{< katex >}}$\mathscr{G}${{< /katex >}} is a sheaf on {{< katex >}}$X${{< /katex >}}.
Let {{< katex >}}$\pi_\ast G${{< /katex >}} denote the *espace étalé* over {{< katex >}}$Y${{< /katex >}} for the sheaf {{< katex >}}$\pi_\ast\mathscr{G}${{< /katex >}}.

A section {{< katex >}}$s \colon V \to \pi^{-1}\pi_\ast G${{< /katex >}}
is a tuple {{< katex >}}$(s_{\pi(x)})_{x \in V}${{< /katex >}} taking values in {{< katex >}}$\pi_\ast\mathscr{G}_{\pi(x)}${{< /katex >}}
satisfying the continuity condition {{< katex >}}$\eqref{star}${{< /katex >}},
which in our particular case asserts the existence,
for each {{< katex >}}$x \in V${{< /katex >}}, of an open neighborhood {{< katex >}}$V_x${{< /katex >}} of {{< katex >}}$x${{< /katex >}} and an open neighborhood
{{< katex >}}$U_x${{< /katex >}} in {{< katex >}}$Y${{< /katex >}} satisfying {{< katex >}}$\pi(V_x) \subset U_x${{< /katex >}}.
Furthermore there exists {{< katex >}}$g \in \pi_\ast\mathscr{G}(U_x) = \mathscr{G}(\pi^{-1}(U_x))${{< /katex >}}
such that the image of {{< katex >}}$s_{\pi(x)}${{< /katex >}} in {{< katex >}}$\mathscr{G}_x${{< /katex >}} under the natural map
{{< katex >}}$\pi_\ast\mathscr{G}_{\pi(x)} \to \mathscr{G}_x${{< /katex >}} is equal to {{< katex >}}$g_x${{< /katex >}}.

Since the sets {{< katex >}}$\pi^{-1}(U_x)${{< /katex >}} cover {{< katex >}}$V${{< /katex >}} by assumption,
sheafiness of {{< katex >}}$\mathscr{G}${{< /katex >}} implies the existence of a unique {{< katex >}}$g \in \mathscr{G}(V)${{< /katex >}}
such that {{< katex >}}$g_x${{< /katex >}} is equal to the image of {{< katex >}}$s_{\pi(x)}${{< /katex >}}
under the natural map {{< katex >}}$\pi_\ast\mathscr{G}_{\pi(x)} \to \mathscr{G}_x${{< /katex >}}
for *all* {{< katex >}}$x \in V${{< /katex >}}.
Let us thus define a map {{< katex >}}$\epsilon_{\mathscr{G}}(V) \colon \pi^{-1}\pi_\ast\mathscr{G}(V) \to \mathscr{G}(V)${{< /katex >}}
sending {{< katex >}}$(s_{\pi(x)})_{x\in V}${{< /katex >}} to {{< katex >}}$g${{< /katex >}}.

We claim that {{< katex >}}$\epsilon${{< /katex >}} defines a natural transformation from {{< katex >}}$\pi^{-1}\pi_\ast\mathscr{G}${{< /katex >}} to {{< katex >}}$\mathscr{G}${{< /katex >}}.
To prove the claim, we need to show that given a map {{< katex >}}$\psi\colon \mathscr{G} \to \mathscr{G}'${{< /katex >}}
of sheaves on {{< katex >}}$X${{< /katex >}}, the following diagram commutes

{{< katex >}}$$\begin{CD}
\pi^{-1}\pi_\ast\mathscr{G} @>{\epsilon_{\mathscr{G}}}>> \mathscr{G} \\
@V{\pi^{-1}\pi_\ast\psi}VV @VV{\psi}V \\
\pi^{-1}\pi_\ast \mathscr{G}' @>{\epsilon_{\mathscr{G}'}}>> \mathscr{G}'.
\end{CD}$${{< /katex >}}

Given {{< katex >}}$(s_{\pi(x)})_{x \in V} \in \pi^{-1}\pi_\ast\mathscr{G}(V)${{< /katex >}},
the upper right path of the square sends us first to some {{< katex >}}$g \in \mathscr{G}(V)${{< /katex >}}
such that {{< katex >}}$g_x${{< /katex >}} is the image of {{< katex >}}$s_{\pi(x)}${{< /katex >}} in {{< katex >}}$\mathscr{G}_x${{< /katex >}} for all {{< katex >}}$x \in V${{< /katex >}},
and then sends {{< katex >}}$g${{< /katex >}} to {{< katex >}}$\psi(V)(g) \in \mathscr{G}'(V)${{< /katex >}}.
On the other hand, the lower left path of the square sends
{{< katex >}}$(s_{\pi(x)})_{x \in V}${{< /katex >}} first to {{< katex >}}$\left((\pi_\ast\psi)_{\pi(x)}(s_{\pi(x)})\right)_{x \in V}${{< /katex >}}
in {{< katex >}}$\pi^{-1}\pi_\ast\mathscr{G}'(V)${{< /katex >}}, and then to
some {{< katex >}}$g' \in \mathscr{G}'(V)${{< /katex >}} such that {{< katex >}}$g'_x${{< /katex >}} is the image of
{{< katex >}}$(\pi_\ast\psi)_{\pi(x)}(s_{\pi(x)})${{< /katex >}} in {{< katex >}}$\mathscr{G}'_x${{< /katex >}} for all {{< katex >}}$x \in V${{< /katex >}}.

If {{< katex >}}$U \subset Y${{< /katex >}} is an open set containing {{< katex >}}$\pi(x)${{< /katex >}} such that
{{< katex >}}$s \in \pi_\ast\mathscr{G}(U) = \mathscr{G}(\pi^{-1}(U))${{< /katex >}} 
represents {{< katex >}}$s_{\pi(x)}${{< /katex >}} for {{< katex >}}$\pi(x) \in U${{< /katex >}},
we have {{< katex >}}$(\pi_\ast\psi)_{\pi(x)}(s_{\pi(x)}) = \psi(\pi^{-1}(U))(s)_{\pi(x)}${{< /katex >}}.
Furthermore we know that {{< katex >}}$g \in \mathscr{G}(V)${{< /katex >}} 
is such that the image of {{< katex >}}$s_{\pi(x)}${{< /katex >}} in {{< katex >}}$\mathscr{G}_x${{< /katex >}}
is {{< katex >}}$g_x${{< /katex >}} for all {{< katex >}}$x \in V${{< /katex >}}.
Therefore we have that
the image of {{< katex >}}$\psi(\pi^{-1}(U))(s)_{\pi(x)}${{< /katex >}}
in {{< katex >}}$\mathscr{G}'_x${{< /katex >}} is equal to {{< katex >}}$\psi(V)(g)_x${{< /katex >}},
as desired.

## The inverse image--pushforward adjunction

To conclude, we just need to show that two double compositions
of natural transformations are the identity.
The first, translated into our particular case,
says that if {{< katex >}}$\mathscr{F}${{< /katex >}} is a sheaf on {{< katex >}}$Y${{< /katex >}},
we have that

{{< katex >}}$$\begin{CD}
\pi^{-1}\mathscr{F} @>{\pi^{-1}\eta_{\mathscr{F}}}>> \pi^{-1}\pi_\ast\pi^{-1}\mathscr{F} @>{\epsilon_{\pi^{-1}\mathscr{F}}}>>
\pi^{-1}\mathscr{F}
\end{CD}$${{< /katex >}}

is equal to the identity.
The difficulty here seems to be largely notational.
Let {{< katex >}}$V \subset X${{< /katex >}} be an open set.
Suppose {{< katex >}}$(s_{\pi(x)})_{x \in V}${{< /katex >}} is a section in {{< katex >}}$\pi^{-1}\mathscr{F}(V)${{< /katex >}}.
We have

{{< katex >}}$$(\pi^{-1}\eta_{\mathscr{F}})(V)\left[(s_{\pi(x)})_{x\in V}\right]
= \left((\eta_{\mathscr{F}})_{\pi(x)}(s_{\pi(x)})\right)_{x \in V}
\in \pi^{-1}\pi_\ast\pi^{-1}\mathscr{F}(V).$${{< /katex >}}

First observe that the continuity condition {{< katex >}}$\eqref{star}${{< /katex >}} tells us that
there is, for each {{< katex >}}$x \in V${{< /katex >}}, an open neighborhood {{< katex >}}$V_x${{< /katex >}} of {{< katex >}}$x${{< /katex >}} and
an open set {{< katex >}}$U_x \subset Y${{< /katex >}} containing {{< katex >}}$\pi(V_x)${{< /katex >}}.
On this open set we have {{< katex >}}$s \in \mathscr{F}(U_x)${{< /katex >}} such that
{{< katex >}}$\left((\eta_{\mathscr{F}})(U_x)(s)\right)_{\pi(x)} = (\eta_{\mathscr{F}})_{\pi(x)}(s_{\pi(x)})${{< /katex >}}.

We saw above that {{< katex >}}$(\eta_{\mathscr{F}})(U_x)(s)${{< /katex >}} is the section
{{< katex >}}$(s_{\pi(x)})_{x \in \pi^{-1}(U_x)} \in \pi_\ast\pi^{-1}\mathscr{F}(U_x) = 
\pi^{-1}\mathscr{F}(\pi^{-1}(U))${{< /katex >}}.
The map {{< katex >}}$\epsilon_{\pi^{-1}\mathscr F}${{< /katex >}} recognizes that the sections
{{< katex >}}$(s_{\pi(x)})_{x \in \pi^{-1}(U_x)}${{< /katex >}} satisfy the compatibility conditions
to glue up to form a section {{< katex >}}$(s_{\pi(x)})_{x \in V}${{< /katex >}} in {{< katex >}}$\pi^{-1}\mathscr{F}(V)${{< /katex >}},
demonstrating that the double composition is indeed the identity. So far so good.

The second double composition we need to show is equal to the identity is defined 
for a sheaf {{< katex >}}$\mathscr{G}${{< /katex >}} on {{< katex >}}$X${{< /katex >}} as follows

{{< katex >}}$$\begin{CD}
\pi_\ast\mathscr{G} @>{\eta_{\pi_\ast\mathscr{G}}}>> \pi_\ast\pi^{-1}\pi_\ast\mathscr{G}
@>{\pi_\ast\epsilon_{\mathscr{G}}}>> \pi_\ast\mathscr{G}.
\end{CD}$${{< /katex >}}

If {{< katex >}}$U \subset Y${{< /katex >}} is an open set and {{< katex >}}$g \in \pi_\ast\mathscr{G}(U)${{< /katex >}}
is a section,
the first map sends {{< katex >}}$g${{< /katex >}} to the section
{{< katex >}}$(g_{\pi(x)})_{x \in \pi^{-1}(U)} \in \pi_\ast\pi^{-1}\pi_\ast\mathscr{G}(U)${{< /katex >}}.


The second map recognizes that the above section and {{< katex >}}$g \in \mathscr{G}(\pi^{-1}(U)) = \pi_\ast\mathscr{G}${{< /katex >}}
agree on each stalk, and so sends our section back to {{< katex >}}$g${{< /katex >}}.

This completes the proof that inverse image and pushforward form an adjoint pair of functors.
