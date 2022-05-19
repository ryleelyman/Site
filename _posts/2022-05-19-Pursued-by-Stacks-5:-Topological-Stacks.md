---
layout: post
math: true
---
The purpose of this post is to single out the *topological* (or *geometric* or *Artin*) stacks.

## Atlases
We will say that a stack over $$\mathbf{Top}$$ "is a space" if it is isomorphic as a stack
to $$\underline{X}$$ for some topological space $$X$$.
Following Lerman, we will in fact just drop the underline,
thinking of $$X$$ as the stack $$\underline{X}$$.

An *atlas* for a stack $$\mathsf{D}$$ is a space $$X$$
and a map $$p\colon X \to \mathsf{D}$$
such that for any map $$f\colon Y \to \mathsf{D}$$ of a space into $$\mathsf{D}$$,
the fiber product $$Y \times_{\mathsf{D}} X$$ is a space
and the map $$\pi_1 \colon Y \times_{\mathsf{D}} X \to Y$$
is an open surjection which admits local sections.

Apparently it is common to say in the literature 
that the map $$X \to \mathsf{D}$$ is *representable.*
We say that $$\mathsf{D}$$ is a *topological stack* if it has an atlas.

## Example: $$\mathsf{B}\mathcal{G}$$

Let $$\mathcal{G}$$ be a topological groupoid,
and let $$\mathsf{B}\mathcal{G}$$ be the category of principal $$\mathcal{G}$$-bundles
and $$\mathcal{G}$$-equivariant maps.
[Lerman] shows that $$\mathsf{B}\mathcal{G}$$ is fibered in groupoids over $$\mathbf{Top}$$;
well, strictly speaking he is talking about Lie groupoids, but the argument works just fine
for spaces and topological groupoids.
In fact it is a stack: just as, you might think,
given a topological group $$G$$ and a principal $$G$$-bundle on an open cover of a space $$X$$
with gluing data, you can glue up to form a principal $$G$$-bundle on $$X$$,
you can do the same for groupoids,
and moreover isomorphisms form a sheaf.

Given a topological groupoid $$\mathcal{G}$$,
we claim that the map $$p\colon \mathcal{G}_0 \to \mathsf{B}\mathcal{G}$$
defined (by the 2-Yoneda lemma) by 
the principal $$\mathcal{G}$$-bundle $$\omega\colon \mathcal{G}_1 \to \mathcal{G}_0$$
is an atlas.

So given any space $$Y$$ and a map $$E\colon Y \to \mathsf{B}\mathcal{G}$$, 
we need to show that $$Y\times_{\mathsf{B}\mathcal{G}} \mathcal{G}_0$$
is a space.
First, note that by the 2-Yoneda lemma,
the functor $$E$$ is determined by a principal $$\mathcal{G}$$-bundle $$E \to Y$$.
Given a map $$g\colon Z \to Y$$, the bundle $$E(g)$$ is canonically isomorphic
to the pullback $$g^*E$$, so to ease notation, we will assume 
that it is actually equal to $$g^*E$$.
Similarly given $$f\colon Z \to \mathcal{G}_0$$, we will assume
the bundle $$p(f)$$ is $$f^*\mathcal{G}_1$$.
Thus an object of the fiber product over a space $$Z$$ is a triple
$$(g,f,\beta)$$
where $$g\colon Z \to Y$$ and $$f\colon Z \to \mathcal{G}_0$$ are maps of spaces
and $$\beta\colon g^*E \to f^*\mathcal{G}_1$$ is a $$\mathcal{G}$$-equivariant map of bundles,
hence an isomorphism.

Recall that 

$$f^*\mathcal{G}_1 = \{(z,h) \in Z \times \mathcal{G}_1 : f(z) = \omega(h) \}.$$

The map $$z \mapsto (z,1_{f(z)})$$ defines a global section $$\sigma$$ of this bundle.
We claim that the isomorphism $$\beta^{-1}\colon f^*\mathcal{G}_1 \to g^*E$$
is determined uniquely by the image of $$\sigma$$.
Indeed, given $$\beta^{-1}(\sigma(z)) = (z,e)$$,
we must have $$\beta^{-1}(z,h) = \beta^{-1}(\sigma(z).h) = (z,e).h$$,
for all appropriate $$h \in \mathcal{G}_1$$,
so fiber by fiber the bundle map $$\beta^{-1}$$ 
is determined by the point $$\beta^{-1}(\sigma(z))$$.
This gives us a map $$\tau\colon Z \to E$$ 
defined as $$z \mapsto e$$ such that $$\pi \tau = g$$,
where $$\pi\colon E \to Y$$ is the defining map of the principal bundle $$E$$.
Notice that the anchor map of, for instance, $$g^*E$$ is
$$(z,e) \mapsto a(e)$$, where $$a \colon E \to \mathcal{G}_0$$ is the anchor map.
We have

$$f = f\pi\sigma = \omega f_{\mathcal{G}_1} \sigma 
= \alpha (\cdot)^{-1} f_{\mathcal{G}_1} \sigma = \alpha f_{\mathcal{G}_1}\sigma,$$

since $$\sigma(z) = (z,1_{f(z)})$$. But then

$$\alpha f_{\mathcal{G}_1\sigma} = a g_E \beta^{-1} \sigma,$$

since the isomorphism $$\beta$$ intertwines the actions and thus preserves anchor maps.
Finally,

$$a g_E \beta^{-1} \sigma = a \tau.$$

Conversely, given any map $$\tau \colon Z \to E$$, 
we reconstruct $$(g,f,\beta)$$ as follows: the map $$g \colon Z \to Y$$ is $$\pi\tau$$,
the map $$f$$ is $$a\tau$$,
Finally we need a map $$\beta \colon g^*E \to f^*\mathcal{G}_1$$.
By definition we have

$$g^*E = \{(z,e) \in Z\times E : \pi\tau(z) = \pi(e) \} \quad\text{and}\quad
f^*\mathcal{G}_1 = \{(z,h) \in Z \times \mathcal{G}_1 : a\tau(z) = \omega(h) \}.$$

Define $$\beta(z,\tau(z)) = (z,1_{a\tau(z)})$$ and extend equivariantly.
It is clear that these constructions are mutually inverse,
and we conclude that objects of the 2-fiber product are (isomorphic to) maps of spaces to $$E$$.

Now for arrows! Suppose we have an arrow $$(u,v)\colon (g_1,f_1,\beta_1) \to (g_2,f_2,\beta_2)$$
over a map of spaces $$h\colon Z_1 \to Z_2$$.
This is a pair of maps $$u\colon Z_1 \to Z_2$$ and $$v\colon Z_1 \to Z_2$$
with the property that the following diagrams commute

$$\require{AMScd}\begin{CD}
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
\end{CD}$$

where $$\tilde u$$ and $$\tilde v$$ are the unique $$\mathcal{G}$$-equivariant maps
satisfying $$(g_1)_E = (g_2)_E \tilde u$$ 
and $$(f_1)_{\mathcal{G}_1} = (f_2)_{\mathcal{G}_1}\tilde v$$.
But because each $$\beta_i$$ is over the identity map of $$Z_i$$,
we conclude that in fact $$u = v$$.
We have

$$\tau_1\pi_1 = (g_1)_E \beta_1^{-1} = (g_2)_E \tilde u \beta_1^{-1}
= (g_2)_E \beta_2^{-1}\tilde v = \tau_2\pi_2 \tilde v = \tau_2 u \pi_1,$$

so because $$\pi_1$$ is an epimorphism, we conclude $$\tau_1 = \tau_2 u$$.
Finally, because, for instance, $$(g_1)_E(z,\tau_1(z).h) = \tau_1(z).h$$
and $$(g_2)_E(z,\tau_2(z).h) = \tau_2(z).h$$,
we must have $$\tilde u(z,\tau_1(z).h) = (u(z),\tau_2u(z)) = (u(z),\tau_1(z))$$
and similarly $$\tilde v(z,1_{a\tau_1(z)}) = (v(z),1_{a\tau_2(u(z))}) = (v(z),1_{a\tau_1(z)})$$.

Conversely, given $$u \colon Z_1 \to Z_2$$ such that $$\tau_1 = \tau_2u$$,
observe that $$g_1 = \pi\tau_1 = \pi\tau_2 u = g_2u$$
and $$f_2 = a\tau_1 = a\tau_2 u = f_2u$$.
We have, for any $$z \in Z_1$$ and appropriate $$h \in \mathcal{G}_1$$,

$$\begin{gather*}
\tilde v \beta_1(z,\tau_1(z).h) = \tilde v(z,h) = (v(z),h)  = (u(z),h) \\
= \beta_2(u(z),\tau_2u(z).h) = \beta_2(u(z),\tau_1(z).h) = \beta_2\tilde u(z,\tau_1(z).h).
\end{gather*}$$

Therefore arrows in the 2-fiber product are (isomorphic to) maps in $$\underline{E}$$,
and we conclude that the 2-fiber product is the space $$E$$.
The map $$\pi\colon E \to Y$$ is an open surjection which admits local sections
because $$E$$ is a principal $$\mathcal{G}$$-bundle.
Therefore the map $$p\colon \mathcal{G}_0 \to \mathsf{B}\mathcal{G}$$ is an atlas.


[Lerman]: https://ems.press/content/serial-article-files/6839
