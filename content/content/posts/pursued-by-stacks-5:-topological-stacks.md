---
title: "Pursued by Stacks 5: Topological Stacks"
date: 2022-05-19T15:52:42-04:00
math: true
---
The purpose of this post is to single out the *topological* (or *geometric* or *Artin*) stacks.

## Atlases
We will say that a stack over {{< katex >}}$\mathbf{Top}${{< /katex >}} "is a space" if it is isomorphic as a stack
to {{< katex >}}$\underline{X}${{< /katex >}} for some topological space {{< katex >}}$X${{< /katex >}}.
Following Lerman, we will in fact just drop the underline,
thinking of {{< katex >}}$X${{< /katex >}} as the stack {{< katex >}}$\underline{X}${{< /katex >}}.

An *atlas* for a stack {{< katex >}}$\mathsf{D}${{< /katex >}} is a space {{< katex >}}$X${{< /katex >}}
and a map {{< katex >}}$p\colon X \to \mathsf{D}${{< /katex >}}
such that for any map {{< katex >}}$f\colon Y \to \mathsf{D}${{< /katex >}} of a space into {{< katex >}}$\mathsf{D}${{< /katex >}},
the fiber product {{< katex >}}$Y \times_{\mathsf{D}} X${{< /katex >}} is a space
and the map {{< katex >}}$\pi_1 \colon Y \times_{\mathsf{D}} X \to Y${{< /katex >}}
is an open surjection which admits local sections.

Apparently it is common to say in the literature 
that the map {{< katex >}}$X \to \mathsf{D}${{< /katex >}} is *representable.*
We say that {{< katex >}}$\mathsf{D}${{< /katex >}} is a *topological stack* if it has an atlas.

## Example: {{< katex >}}$\mathsf{B}\mathcal{G}${{< /katex >}}

Let {{< katex >}}$\mathcal{G}${{< /katex >}} be a topological groupoid,
and let {{< katex >}}$\mathsf{B}\mathcal{G}${{< /katex >}} be the category of principal {{< katex >}}$\mathcal{G}${{< /katex >}}-bundles
and {{< katex >}}$\mathcal{G}${{< /katex >}}-equivariant maps.
[Lerman] shows that {{< katex >}}$\mathsf{B}\mathcal{G}${{< /katex >}} is fibered in groupoids over {{< katex >}}$\mathbf{Top}${{< /katex >}};
well, strictly speaking he is talking about Lie groupoids, but the argument works just fine
for spaces and topological groupoids.
In fact it is a stack: just as, you might think,
given a topological group {{< katex >}}$G${{< /katex >}} and a principal {{< katex >}}$G${{< /katex >}}-bundle on an open cover of a space {{< katex >}}$X${{< /katex >}}
with gluing data, you can glue up to form a principal {{< katex >}}$G${{< /katex >}}-bundle on {{< katex >}}$X${{< /katex >}},
you can do the same for groupoids,
and moreover isomorphisms form a sheaf.

Given a topological groupoid {{< katex >}}$\mathcal{G}${{< /katex >}},
we claim that the map {{< katex >}}$p\colon \mathcal{G}_0 \to \mathsf{B}\mathcal{G}${{< /katex >}}
defined (by the 2-Yoneda lemma) by 
the principal {{< katex >}}$\mathcal{G}${{< /katex >}}-bundle {{< katex >}}$\omega\colon \mathcal{G}_1 \to \mathcal{G}_0${{< /katex >}}
is an atlas.

So given any space {{< katex >}}$Y${{< /katex >}} and a map {{< katex >}}$E\colon Y \to \mathsf{B}\mathcal{G}${{< /katex >}}, 
we need to show that {{< katex >}}$Y\times_{\mathsf{B}\mathcal{G}} \mathcal{G}_0${{< /katex >}}
is a space.
First, note that by the 2-Yoneda lemma,
the functor {{< katex >}}$E${{< /katex >}} is determined by a principal {{< katex >}}$\mathcal{G}${{< /katex >}}-bundle {{< katex >}}$E \to Y${{< /katex >}}.
Given a map {{< katex >}}$g\colon Z \to Y${{< /katex >}}, the bundle {{< katex >}}$E(g)${{< /katex >}} is canonically isomorphic
to the pullback {{< katex >}}$g^*E${{< /katex >}}, so to ease notation, we will assume 
that it is actually equal to {{< katex >}}$g^*E${{< /katex >}}.
Similarly given {{< katex >}}$f\colon Z \to \mathcal{G}_0${{< /katex >}}, we will assume
the bundle {{< katex >}}$p(f)${{< /katex >}} is {{< katex >}}$f^*\mathcal{G}_1${{< /katex >}}.
Thus an object of the fiber product over a space {{< katex >}}$Z${{< /katex >}} is a triple
{{< katex >}}$(g,f,\beta)${{< /katex >}}
where {{< katex >}}$g\colon Z \to Y${{< /katex >}} and {{< katex >}}$f\colon Z \to \mathcal{G}_0${{< /katex >}} are maps of spaces
and {{< katex >}}$\beta\colon g^*E \to f^*\mathcal{G}_1${{< /katex >}} is a {{< katex >}}$\mathcal{G}${{< /katex >}}-equivariant map of bundles,
hence an isomorphism.

Recall that 

{{< katex >}}$f^*\mathcal{G}_1 = \{(z,h) \in Z \times \mathcal{G}_1 : f(z) = \omega(h) \}.${{< /katex >}}

The map {{< katex >}}$z \mapsto (z,1_{f(z)})${{< /katex >}} defines a global section {{< katex >}}$\sigma${{< /katex >}} of this bundle.
We claim that the isomorphism {{< katex >}}$\beta^{-1}\colon f^*\mathcal{G}_1 \to g^*E${{< /katex >}}
is determined uniquely by the image of {{< katex >}}$\sigma${{< /katex >}}.
Indeed, given {{< katex >}}$\beta^{-1}(\sigma(z)) = (z,e)${{< /katex >}},
we must have {{< katex >}}$\beta^{-1}(z,h) = \beta^{-1}(\sigma(z).h) = (z,e).h${{< /katex >}},
for all appropriate {{< katex >}}$h \in \mathcal{G}_1${{< /katex >}},
so fiber by fiber the bundle map {{< katex >}}$\beta^{-1}${{< /katex >}} 
is determined by the point {{< katex >}}$\beta^{-1}(\sigma(z))${{< /katex >}}.
This gives us a map {{< katex >}}$\tau\colon Z \to E${{< /katex >}} 
defined as {{< katex >}}$z \mapsto e${{< /katex >}} such that {{< katex >}}$\pi \tau = g${{< /katex >}},
where {{< katex >}}$\pi\colon E \to Y${{< /katex >}} is the defining map of the principal bundle {{< katex >}}$E${{< /katex >}}.
Notice that the anchor map of, for instance, {{< katex >}}$g^*E${{< /katex >}} is
{{< katex >}}$(z,e) \mapsto a(e)${{< /katex >}}, where {{< katex >}}$a \colon E \to \mathcal{G}_0${{< /katex >}} is the anchor map.
We have

{{< katex >}}$$f = f\pi\sigma = \omega f_{\mathcal{G}_1} \sigma 
= \alpha (\cdot)^{-1} f_{\mathcal{G}_1} \sigma = \alpha f_{\mathcal{G}_1}\sigma,$${{< /katex >}}

since {{< katex >}}$\sigma(z) = (z,1_{f(z)})${{< /katex >}}. But then

{{< katex >}}$\alpha f_{\mathcal{G}_1\sigma} = a g_E \beta^{-1} \sigma,${{< /katex >}}

since the isomorphism {{< katex >}}$\beta${{< /katex >}} intertwines the actions and thus preserves anchor maps.
Finally,

{{< katex >}}$a g_E \beta^{-1} \sigma = a \tau.${{< /katex >}}

Conversely, given any map {{< katex >}}$\tau \colon Z \to E${{< /katex >}}, 
we reconstruct {{< katex >}}$(g,f,\beta)${{< /katex >}} as follows: the map {{< katex >}}$g \colon Z \to Y${{< /katex >}} is {{< katex >}}$\pi\tau${{< /katex >}},
the map {{< katex >}}$f${{< /katex >}} is {{< katex >}}$a\tau${{< /katex >}},
Finally we need a map {{< katex >}}$\beta \colon g^*E \to f^*\mathcal{G}_1${{< /katex >}}.
By definition we have

{{< katex >}}$$g^*E = \{(z,e) \in Z\times E : \pi\tau(z) = \pi(e) \} \quad\text{and}\quad
f^*\mathcal{G}_1 = \{(z,h) \in Z \times \mathcal{G}_1 : a\tau(z) = \omega(h) \}.$${{< /katex >}}

Define {{< katex >}}$\beta(z,\tau(z)) = (z,1_{a\tau(z)})${{< /katex >}} and extend equivariantly.
It is clear that these constructions are mutually inverse,
and we conclude that objects of the 2-fiber product are (isomorphic to) maps of spaces to {{< katex >}}$E${{< /katex >}}.

Now for arrows! Suppose we have an arrow {{< katex >}}$(u,v)\colon (g_1,f_1,\beta_1) \to (g_2,f_2,\beta_2)${{< /katex >}}
over a map of spaces {{< katex >}}$h\colon Z_1 \to Z_2${{< /katex >}}.
This is a pair of maps {{< katex >}}$u\colon Z_1 \to Z_2${{< /katex >}} and {{< katex >}}$v\colon Z_1 \to Z_2${{< /katex >}}
with the property that the following diagrams commute

{{< katex >}}$$\begin{CD}
Z_1 @>g_1>> Y \\
@VVuV @| \\
Z_2 @>g_2>> Y
\end{CD}\qquad\begin{CD}
Z_1 @>f_1>> \mathcal{G}_0 \\
@VVvV @| \\
Z_2 @>f_2>> \mathcal{G}_0
\end{CD}\qquad \begin{CD}
g_1^*E @>\beta_1>> f_1^*\mathcal{G}_1 \\
@VV\tilde uV @VV\tilde vV \\
g_2^*E @>\beta_2>> f_2^*\mathcal{G}_1,
\end{CD}$${{< /katex >}}

where {{< katex >}}$\tilde u${{< /katex >}} and {{< katex >}}$\tilde v${{< /katex >}} are the unique {{< katex >}}$\mathcal{G}${{< /katex >}}-equivariant maps
satisfying {{< katex >}}$(g_1)_E = (g_2)_E \tilde u${{< /katex >}} 
and {{< katex >}}$(f_1)_{\mathcal{G}_1} = (f_2)_{\mathcal{G}_1}\tilde v${{< /katex >}}.
But because each {{< katex >}}$\beta_i${{< /katex >}} is over the identity map of {{< katex >}}$Z_i${{< /katex >}},
we conclude that in fact {{< katex >}}$u = v${{< /katex >}}.
We have

{{< katex >}}$$\tau_1\pi_1 = (g_1)_E \beta_1^{-1} = (g_2)_E \tilde u \beta_1^{-1}
= (g_2)_E \beta_2^{-1}\tilde v = \tau_2\pi_2 \tilde v = \tau_2 u \pi_1,$${{< /katex >}}

so because {{< katex >}}$\pi_1${{< /katex >}} is an epimorphism, we conclude {{< katex >}}$\tau_1 = \tau_2 u${{< /katex >}}.
Finally, because, for instance, {{< katex >}}$(g_1)_E(z,\tau_1(z).h) = \tau_1(z).h${{< /katex >}}
and {{< katex >}}$(g_2)_E(z,\tau_2(z).h) = \tau_2(z).h${{< /katex >}},
we must have {{< katex >}}$\tilde u(z,\tau_1(z).h) = (u(z),\tau_2u(z)) = (u(z),\tau_1(z))${{< /katex >}}
and similarly {{< katex >}}$\tilde v(z,1_{a\tau_1(z)}) = (v(z),1_{a\tau_2(u(z))}) = (v(z),1_{a\tau_1(z)})${{< /katex >}}.

Conversely, given {{< katex >}}$u \colon Z_1 \to Z_2${{< /katex >}} such that {{< katex >}}$\tau_1 = \tau_2u${{< /katex >}},
observe that {{< katex >}}$g_1 = \pi\tau_1 = \pi\tau_2 u = g_2u${{< /katex >}}
and {{< katex >}}$f_2 = a\tau_1 = a\tau_2 u = f_2u${{< /katex >}}.
We have, for any {{< katex >}}$z \in Z_1${{< /katex >}} and appropriate {{< katex >}}$h \in \mathcal{G}_1${{< /katex >}},

{{< katex >}}$$\begin{gather*}
\tilde v \beta_1(z,\tau_1(z).h) = \tilde v(z,h) = (v(z),h)  = (u(z),h) \\
= \beta_2(u(z),\tau_2u(z).h) = \beta_2(u(z),\tau_1(z).h) = \beta_2\tilde u(z,\tau_1(z).h).
\end{gather*}$${{< /katex >}}

Therefore arrows in the 2-fiber product are (isomorphic to) maps in {{< katex >}}$\underline{E}${{< /katex >}},
and we conclude that the 2-fiber product is the space {{< katex >}}$E${{< /katex >}}.
The map {{< katex >}}$\pi\colon E \to Y${{< /katex >}} is an open surjection which admits local sections
because {{< katex >}}$E${{< /katex >}} is a principal {{< katex >}}$\mathcal{G}${{< /katex >}}-bundle.
Therefore the map {{< katex >}}$p\colon \mathcal{G}_0 \to \mathsf{B}\mathcal{G}${{< /katex >}} is an atlas.


[Lerman]: https://ems.press/content/serial-article-files/6839
