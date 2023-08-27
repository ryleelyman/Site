---
title: "Pursued by Stacks 4: Fiber Products"
date: 2022-05-18T15:47:29-04:00
math: true
---
Okay, we're closing in on the definition of a geometric stack over {{< katex >}}$\mathbf{Top}${{< /katex >}}.
Actually, the nLab tells me such stacks are called *topological,* so I'll try and say that.
But! Before we get there, we need the construction 
of the 2-fiber product of categories fibered in groupoids over {{< katex >}}$\mathbf{Top}${{< /katex >}}.
The purpose of this post is to discuss this construction, which I think is adorable.
I cannot shake the feeling that I've talked through the 2-fiber product of categories
before, but I have no idea where or why I might have done this
except possibly the last time I tried to learn about stacks.

Friends of the blog [will recall] the categorical definition of a pullback.
This notion makes sense for categories (after all, categories assemble into a category),
but because of the existence of natural transformations, the universal property looks
a little bit different.
Namely, suppose we have three categories {{< katex >}}$\mathsf{C}${{< /katex >}}, {{< katex >}}$\mathsf{D}${{< /katex >}} and {{< katex >}}$\mathsf{E}${{< /katex >}}
and two functors {{< katex >}}$F\colon \mathsf{C} \to \mathsf{E}${{< /katex >}} and {{< katex >}}$G\colon \mathsf{D} \to \mathsf{E}${{< /katex >}}.
The *2-fiber product* {{< katex >}}$\mathsf{C}\times_{\mathsf{E}} \mathsf{D}${{< /katex >}} makes the following diagram
commute

{{< katex >}}$$\require{AMScd}\begin{CD}
\mathsf{C}\times_{\mathsf{E}}\mathsf{D} @>\pi_1>> \mathsf{C} \\
@V\pi_2VV @VFVV \\
\mathsf{D} @>G>> \mathsf{E}
\end{CD}$${{< /katex >}}

up to natural isomorphism {{< katex >}}$\eta\colon F\pi_1 \Rightarrow G\pi_2${{< /katex >}}
and is *universal* for this property in the following slightly complicated sense.
Given any category {{< katex >}}$\mathsf{X}${{< /katex >}}, maps {{< katex >}}$H\colon \mathsf{X} \to \mathsf{C}${{< /katex >}}
and {{< katex >}}$K\colon \mathsf{X} \to \mathsf{D}${{< /katex >}}
with a natural isomorphism {{< katex >}}$\epsilon \colon FH \Rightarrow GK${{< /katex >}},
there is a functor {{< katex >}}$P\colon\mathsf{X} \to \mathsf{C}\times_{\mathsf{E}}\mathsf{D}${{< /katex >}}
and natural isomorphisms {{< katex >}}$\alpha\colon H \Rightarrow \pi_1P${{< /katex >}} 
and {{< katex >}}$\beta\colon K\Rightarrow \pi_2P${{< /katex >}}
with the property that {{< katex >}}$(G\beta)^{-1} \circ \eta P \circ F\alpha = \epsilon${{< /katex >}}.
This is summarized in the following diagram.

![The 2-pullback diagram](/img/2pullback.jpeg)

Given another functor {{< katex >}}$Q\colon \mathsf{X} \to \mathsf{C}\times_{\mathsf{E}}\mathsf{D}${{< /katex >}}
and natural isomorphisms {{< katex >}}$\gamma\colon H\Rightarrow \pi_1Q${{< /katex >}}
and {{< katex >}}$\delta\colon K \Rightarrow \pi_2Q${{< /katex >}} as above,
there exists a unique natural isomorphism {{< katex >}}$\lambda \colon P \Rightarrow Q${{< /katex >}}
with the property that {{< katex >}}$\pi_1\lambda \colon \pi_1P \Rightarrow \pi_1Q${{< /katex >}}
equals {{< katex >}}$\gamma\circ\alpha^{-1}${{< /katex >}} and {{< katex >}}$\pi_2\lambda = \delta\circ\beta^{-1}${{< /katex >}}.

In the case of categories fibered in groupoids over {{< katex >}}$\mathbf{Top}${{< /katex >}},
the 2-fiber product has the following definition.
Objects of {{< katex >}}$\mathsf{C}\times_{\mathsf{E}} \mathsf{D}${{< /katex >}} are triples
{{< katex >}}$(c,d,\alpha)${{< /katex >}}, where {{< katex >}}$c \in \mathsf{C}${{< /katex >}} and {{< katex >}}$d \in \mathsf{D}${{< /katex >}} are objects
over the same space {{< katex >}}$X${{< /katex >}}
and {{< katex >}}$\alpha\colon F(c) \to G(d)${{< /katex >}} is an arrow over the identity map of {{< katex >}}$X${{< /katex >}}.
Arrows of {{< katex >}}$\mathsf{C}\times_{\mathsf{E}}\mathsf{D}${{< /katex >}} are pairs of arrows
{{< katex >}}$u\colon c_1 \to c_2${{< /katex >}} and {{< katex >}}$v\colon d_1 \to d_2${{< /katex >}}
over the same map of spaces {{< katex >}}$f\colon X \to Y${{< /katex >}}
with the property that the following diagram commutes in {{< katex >}}$\mathsf{E}${{< /katex >}}

{{< katex >}}$$\begin{CD}
F(c_1) @>\alpha_1>> G(d_1) \\
@VVF(u)V @VVG(v)V \\
F(c_2) @>\alpha_2>> G(d_2).
\end{CD}$${{< /katex >}}

There is an obvious functor {{< katex >}}$\pi\colon \mathsf{C}\times_{\mathsf{E}}\mathsf{D} \to \mathbf{Top}${{< /katex >}}
sending an object {{< katex >}}$(c,d,\alpha)${{< /katex >}} to the space {{< katex >}}$X${{< /katex >}} that {{< katex >}}$c${{< /katex >}} and {{< katex >}}$d${{< /katex >}} are over
and sending an arrow {{< katex >}}$(u,v)${{< /katex >}} to the map {{< katex >}}$f\colon X \to Y${{< /katex >}} that {{< katex >}}$u${{< /katex >}} and {{< katex >}}$v${{< /katex >}} are over.
We'd like to show that {{< katex >}}$\mathsf{C}\times_{\mathsf{E}}\mathsf{D}${{< /katex >}} is fibered in groupoids.
Given an object {{< katex >}}$\xi = (c,d,\alpha)${{< /katex >}} over {{< katex >}}$X${{< /katex >}} and a map {{< katex >}}$f\colon Y \to X${{< /katex >}},
we need a "pullback" {{< katex >}}$f^*\xi${{< /katex >}} over {{< katex >}}$Y${{< /katex >}}.
It would be simplest to define {{< katex >}}$f^*\xi = (f^*c,f^*d,f^*\alpha)${{< /katex >}},
but we don't necessarily have {{< katex >}}$f^*F(c) = F(f^*c)${{< /katex >}}, 
merely that they are canonically isomorphic via an isomorphism 
{{< katex >}}$\sigma_{F,f}\colon F(f^*c) \to f^*F(c)${{< /katex >}}
such that {{< katex >}}$F(f_c) = f_{F(c)} \sigma_{F,f}${{< /katex >}}.
So we will in fact define {{< katex >}}$f^\xi = (f^*c, f^*d, \sigma_{G,f}^{-1} f^*\alpha \sigma_{F,f})${{< /katex >}}.
The map {{< katex >}}$f_\xi \colon f^*\xi \to \xi${{< /katex >}}
is the map {{< katex >}}$(f_c,f_d)${{< /katex >}}. We check

{{< katex >}}$$ \alpha F(f_c) = \alpha f_{F(c)} \sigma_{F,f} = f_{G(d)} f^*\alpha \sigma_{F,f} 
= G(f_d) \sigma_{G,f}^{-1} f^*\alpha \sigma_{F,f}, $${{< /katex >}}

so this really does give a map {{< katex >}}$f_\xi \colon f^*\xi \to \xi${{< /katex >}}.

Given a pair of arrows {{< katex >}}$(u_1,v_1)\colon (c_1,d_1,\alpha_1) \to (c,d,\alpha)${{< /katex >}}
and {{< katex >}}$(u_2,v_2)\colon (c_2,d_2,\alpha_2) \to (c,d,\alpha)${{< /katex >}}
over maps {{< katex >}}$f \colon Y \to X${{< /katex >}} and {{< katex >}}$g\colon Z \to X${{< /katex >}}
such that there exists a map of spaces {{< katex >}}$h\colon Y \to Z${{< /katex >}} with {{< katex >}}$gh = f${{< /katex >}},
we need a unique pair of maps {{< katex >}}$h_{\mathsf{C}}\colon c_1 \to c_2${{< /katex >}} and 
{{< katex >}}$h_{\mathsf{D}}\colon d_1 \to d_2${{< /katex >}}
such that the relevant diagram commutes.
But observe that because {{< katex >}}$u_1${{< /katex >}} and {{< katex >}}$u_2${{< /katex >}} are over {{< katex >}}$f${{< /katex >}} and {{< katex >}}$g${{< /katex >}},
there does exist a unique map {{< katex >}}$h_{\mathsf{C}}\colon c_1 \to c_2${{< /katex >}}
and similarly a unique map {{< katex >}}$h_{\mathsf{D}}\colon d_1 \to d_2${{< /katex >}} lifting the diagram {{< katex >}}$gh = f${{< /katex >}}.
We need to check that the following diagram commutes

{{< katex >}}$$\begin{CD}
F(c_1) @>\alpha_1>> G(d_1) \\
@VVF(h_{\mathsf{C}})V @VVG(h_{\mathsf{D}})V \\
F(c_2) @>\alpha_2>> G(d_2).
\end{CD}$${{< /katex >}}

We will show this by the strategy from the last post:
fitting both paths around the square into the vertical arrow in the following diagram

{{< katex >}}$$\begin{CD}
F(c_1) @>\alpha F(u_1)>> G(d) \\
@VVV @| \\
G(d_2) @>G(v_2)>> G(d);
\end{CD}$${{< /katex >}}

uniqueness then assures equality of the paths around the square.
We have

{{< katex >}}$\alpha F(u_1) = G(v_1)\alpha_1 = G(v_2)G(h_{\mathsf{D}})\alpha_1.${{< /katex >}}

On the other hand we have

{{< katex >}}$\alpha F(u_1) = \alpha F(u_2)F(h_{\mathsf{C}}) = G(v_2) \alpha_2 F(h_{\mathsf{C}}),${{< /katex >}}

how satisfying! This shows that the 2-fiber product really is fibered in groupoids.

On the other hand, we have obvious projections {{< katex >}}$\mathsf{C}\times_{\mathsf{E}}\mathsf{D}${{< /katex >}}
to {{< katex >}}$\mathsf{C}${{< /katex >}} and {{< katex >}}$\mathsf{D}${{< /katex >}}.
Call these {{< katex >}}$\pi_1${{< /katex >}} and {{< katex >}}$\pi_2${{< /katex >}}.
We do not quite have {{< katex >}}$F\pi_1 = G\pi_2${{< /katex >}},
merely that there is a natural isomorphism {{< katex >}}$\eta\colon F\pi_1 \Rightarrow G\pi_2${{< /katex >}}
defined by {{< katex >}}$\eta(c,d,\alpha) = \alpha${{< /katex >}}! Adorable, right?
Showing that {{< katex >}}$\eta${{< /katex >}} really is natural is cute, but I'll leave it to you.

By the way, are you still thinking vector bundles? I know I am;
it's helpful to pretend that there really is a projection from {{< katex >}}$\xi \in \mathsf{C}${{< /katex >}}
down to the space {{< katex >}}$X${{< /katex >}} it is over.

## The universal property

I'd like to conclude this post by showing that the fiber product 
really has its universal property.
Given a category {{< katex >}}$\mathsf{X}${{< /katex >}} fibered in groupoids over {{< katex >}}$\mathbf{Top}${{< /katex >}}
with functors {{< katex >}}$H \colon \mathsf{X} \to \mathsf{C}${{< /katex >}} and {{< katex >}}$K\colon \mathsf{X} \to \mathsf{D}${{< /katex >}}
and a natural isomorphism {{< katex >}}$\epsilon\colon FH \Rightarrow GK${{< /katex >}},
the obvious functor {{< katex >}}$P${{< /katex >}} to {{< katex >}}$\mathsf{C}\times_{\mathsf{E}}\mathsf{D}${{< /katex >}}
is defined on objects as {{< katex >}}$x \mapsto (H(x),K(x),\epsilon(x))${{< /katex >}}
and on arrows {{< katex >}}$(u\colon x \to y) \mapsto (H(u),K(u))${{< /katex >}}.
Naturality of {{< katex >}}$\epsilon${{< /katex >}} assures that this is really a functor.
In this case, the isomorphisms {{< katex >}}$\alpha\colon H \Rightarrow \pi_1P${{< /katex >}} 
and {{< katex >}}$\beta\colon K \Rightarrow \pi_2P${{< /katex >}}
are the identity: these diagrams commute on the nose.
Now suppose we have another functor 
{{< katex >}}$Q\colon \mathsf{X} \to \mathsf{C}\times_{\mathsf{E}}\mathsf{D}${{< /katex >}}
and natural isomorphisms {{< katex >}}$\gamma \colon H \Rightarrow \pi_1Q${{< /katex >}}
and {{< katex >}}$\delta\colon K \Rightarrow \pi_2Q${{< /katex >}}.
Define {{< katex >}}$\lambda \colon P \Rightarrow Q${{< /katex >}} by the rule
{{< katex >}}$\lambda(x) = (\gamma(x),\delta(x))\colon (H(x),K(x),\epsilon(x)) \to Q(x)${{< /katex >}}.
We write {{< katex >}}$Q(x) = (c,d,\alpha)${{< /katex >}}. We need the following diagram to commute

{{< katex >}}$$\begin{CD}
FH(x) @>\epsilon(x)>> GK(x) \\
@VVF\gamma(x)V @VVG\delta(x)V \\
F(c) @>\alpha>> G(d).
\end{CD}$${{< /katex >}}

But this is exactly the condition at {{< katex >}}$x${{< /katex >}} for the equality
{{< katex >}}$(G\delta)^{-1}\eta Q F\gamma = \epsilon${{< /katex >}},
so {{< katex >}}$\lambda(x)${{< /katex >}} really defines an arrow.
Given an arrow {{< katex >}}$u\colon x \to y${{< /katex >}} in {{< katex >}}$\mathsf{X}${{< /katex >}},
we need to check naturality:

{{< katex >}}$$\begin{CD}
(H(x),K(x),\epsilon(x)) @>\lambda(x)>> Q(x) \\
@VV(H(u),K(u))V @VVQ(u)V \\
(H(y),K(y),\epsilon(y)) @>\lambda(y)>> Q(y).
\end{CD}$${{< /katex >}}

This is true in each factor, for example in {{< katex >}}$\mathsf{C}${{< /katex >}} we have
{{< katex >}}$\pi_1 Q(u) \gamma(x) = \gamma(y) H(u)${{< /katex >}}.
Therefore both paths around the square give equal arrows.
It is clear from the construction that {{< katex >}}$\lambda${{< /katex >}} is unique.

[will recall]: {{< ref "pullbacks-and-intersections.md" >}}
