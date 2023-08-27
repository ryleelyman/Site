---
title: "Pursued by Stacks 7: Appendix"
date: 2022-05-19T16:01:00-04:00
math: true
---
This post is, strictly speaking, a follow up to [part three] of my series on stacks,
on the 2-Yoneda lemma.
The classical Yoneda lemma has built into it a naturality statement,
while our 2-Yoneda lemma proved essentially only the fact of the isomorphism.
Let's fix that.

 > **Theorem.** (The 2-Yoneda Lemma)
 The functor 
 {{< katex >}}$\operatorname{よ}\colon \operatorname{Hom}(\underline{X},\mathsf{D}) \to \mathsf{D}(X)${{< /katex >}}
 defined on objects as {{< katex >}}$(F\colon \underline{X} \to \mathsf{D}) \mapsto F(1_X)${{< /katex >}}
 and on arrows as {{< katex >}}$(\alpha\colon F \Rightarrow G) \mapsto \alpha(1_X)${{< /katex >}}
 is an equivalence of categories which is pseudonatural in both arguments.

We have proved all but the (pseudo)-naturality statement,
which is a little convoluted for the following reason.
You see, typically you think of the Yoneda lemma as being about, for instance,
natural transformations from the hom-set functor 
{{< katex >}}$\mathsf{C}(\underline{X},\cdot)${{< /katex >}} to a functor {{< katex >}}$F${{< /katex >}}.
Now, {{< katex >}}$\underline{X}${{< /katex >}} is *not* the functor {{< katex >}}$\mathbf{Top}(X,\cdot)${{< /katex >}},
but rather the functor {{< katex >}}$\mathbf{Top}(\cdot,X)${{< /katex >}} which we think of as being valued not in sets,
but in categories (groupoids, actually),
where the category is the rather uninteresting discrete category
comprising an object for each map {{< katex >}}$Y \to X${{< /katex >}} and only the identity arrows.
Given a map {{< katex >}}$h \colon Y \to Z${{< /katex >}}, 
we get a functor {{< katex >}}$h^*\colon \underline{X}(Z) \to \underline{X}(Y)${{< /katex >}} 
given by {{< katex >}}$h^*(g\colon Z \to X) = gh \colon Y \to X${{< /katex >}}.
This is actually a functor 
(I say, just because I can anticipate that I'm about to write down a not-quite-a-functor).
The only natural transformation between functors is the identity.

Anyway, the point is, we should be expecting to suddenly start thinking of
an arbitrary category fibered in groupoids {{< katex >}}$\mathsf{D}${{< /katex >}} as a *contravariant* functor
from {{< katex >}}$\mathsf{Top}${{< /katex >}} to the category of categories (groupoids, actually),
where the category is {{< katex >}}$\mathsf{D}(Y)${{< /katex >}}.
Given a map {{< katex >}}$h \colon Y \to Z${{< /katex >}},
we should get a functor {{< katex >}}$h^*\colon \mathsf{D}(Z) \to \mathsf{D}(Y)${{< /katex >}}
given by {{< katex >}}$h^*(\xi) = h^*\xi${{< /katex >}}
and we do, actually. The problem, which we mumbled something about earlier,
is that given {{< katex >}}$g \colon X \to Y${{< /katex >}}, we don't necessarily have {{< katex >}}$g^*h^*\xi = (hg)^*\xi${{< /katex >}},
merely that they're canonically isomorphic.
In other words, the operation {{< katex >}}$(\cdot)^*${{< /katex >}} is not a contravariant functor,
just one up to canonical isomorphism.
I super don't actually want to learn what a pseudofunctor is, but I guess that's what this is.

## A digression: pseudofunctors

Let's go slowly: for each object {{< katex >}}$X${{< /katex >}} in {{< katex >}}$\mathbf{Top}${{< /katex >}} 
we have an object in the category of groupoids, namely the groupoid {{< katex >}}$\mathsf{D}(X)${{< /katex >}}.
If we think of the hom-set {{< katex >}}$\mathbf{Top}(X,Y)${{< /katex >}} as a discrete groupoid,
we get a *covariant* functor defined *contravariantly* on objects (which are maps!) 
as {{< katex >}}$(f\colon X\to Y) \mapsto f^*\colon \mathsf{D}(Y) \to \mathsf{D}(X)${{< /katex >}}.
We saw that this is in fact a functor, since given {{< katex >}}$\alpha \colon \xi \to \xi'${{< /katex >}},
there is a unique arrow {{< katex >}}$f^*\alpha \colon f^*\xi \to f^*\xi'${{< /katex >}}.
The arrows of the category {{< katex >}}$\mathbf{Top}(X,Y)${{< /katex >}} are the identity natural isomorphism,
which must go to the identity natural transformation of {{< katex >}}$f^*${{< /katex >}}.
Now, I think we've insisted that {{< katex >}}$1_X^*\xi = \xi${{< /katex >}}, 
and indeed if you pull back a bundle along the identity map, 
I think it's fair to say that you get the same bundle.
This is secretly good, because it lets us ignore isomorphisms involving the identity,
since they are equalities.
Now for the hard part. Given {{< katex >}}$f\colon X \to Y${{< /katex >}} and {{< katex >}}$g \colon Y \to Z${{< /katex >}},
by the defining property of a category fibered in groupoids, 
for each {{< katex >}}$\xi \in \mathsf{D}(Z)${{< /katex >}},
there is a unique isomorphism {{< katex >}}$\eta{f,g}(\xi)${{< /katex >}} making the following diagram commute

{{< katex >}}$$\require{AMScd}\begin{CD}
f^*g^*\xi @>g_{\xi}f_{g^*\xi}>> \xi \\
@VV\eta{f,g}(\xi)V @| \\
(gf)^*\xi @>(gf)_{\xi}>> \xi.
\end{CD}$${{< /katex >}}

Notice that given an arrow {{< katex >}}$\alpha\colon \xi \to \xi'${{< /katex >}},
the following diagram commutes

{{< katex >}}$$\begin{CD}
f^*g^*\xi @>\eta_{f,g}(\xi)>> (gf)^*\xi \\
@VVf^*g^*\alpha V @VV(gf)^*\alpha V \\
f^*g^*\xi' @>\eta_{f,g}(\xi')>> (gf)^*\xi'.
\end{CD}$${{< /katex >}}

This is because of the defining property of categories fibered in groupoids:
both paths around the square make the following diagram commute

{{< katex >}}$$\begin{CD}
f^*g^*\xi @>\alpha g_\xi f_{g^*\xi}>> \xi' \\
@VVV @| \\
(gf)^*\xi' @>(gf)_{\xi'}>> \xi';
\end{CD}$${{< /katex >}}

indeed we calculate

{{< katex >}}$$\alpha g_\xi f_{g^*\xi} = g_{\xi'} g^*\alpha f_{g^*\xi} = g_{\xi'} f_{g^*\xi'} f^*g^*\alpha
= (gf)_{\xi'} \eta_{f,g}(\xi') f^*g^*\alpha$${{< /katex >}}

and

{{< katex >}}$$\alpha g_\xi f_{g^*\xi} = \alpha (gf)_\xi \eta_{f,g}(\xi) 
= (gf)_{\xi'} (gf)^*\alpha \eta_{f,g}(\xi).$${{< /katex >}}

My source (nLab, gulp) suggests that the isomorphism {{< katex >}}$\eta_{f,g}${{< /katex >}} 
should be natural in {{< katex >}}$f${{< /katex >}} and {{< katex >}}$g${{< /katex >}}.
Notice that if {{< katex >}}$f \ne f'${{< /katex >}}, then there are no natural transformations (isomorphisms)
{{< katex >}}$f^* \Rightarrow f'^*${{< /katex >}}.
On the other hand, a family of arrows {{< katex >}}$\alpha(\xi) \colon f^*\xi \to f^*\xi${{< /katex >}},
define a natural isomorphism {{< katex >}}$\alpha \colon f^*\Rightarrow f^*${{< /katex >}}
if for each {{< katex >}}$\beta \colon \xi \to \xi'${{< /katex >}} in the fiber over {{< katex >}}$\mathsf{Y}${{< /katex >}}, we have
{{< katex >}}$\alpha(\xi')f^*\beta = f^*\beta\alpha(\xi)${{< /katex >}}.
Naturality in {{< katex >}}$f${{< /katex >}}, then, is the statement that given {{< katex >}}$\alpha\colon f^* \Rightarrow f^*${{< /katex >}},
the following diagram commutes

{{< katex >}}$$\begin{CD}
f^*g^*\xi @>\eta_{f,g}(\xi)>> (gf)^*\xi \\
@VV\alpha(g^*\xi)V @VVV \\
f^*g^*\xi @>\eta_{f,g}(\xi)>> (gf)^*\xi
\end{CD}$${{< /katex >}}

which can only hold if the righthand arrow is 
{{< katex >}}$\eta_{f,g}(\xi)\alpha(g^*\xi)\eta_{f,g}(\xi)^{-1}${{< /katex >}},
and indeed, I see no other sensible way to define an arrow {{< katex >}}$(gf)^*\xi \to (gf)^*\xi${{< /katex >}}
out of one from {{< katex >}}$f^*\xi \to f^*\xi${{< /katex >}}.
Naturality in {{< katex >}}$g${{< /katex >}} should be similarly silly; I'll leave it to you.

Since function composition is strictly associative (phew)
we just need to check that the following diagram commutes for each {{< katex >}}$\xi \in \mathsf{D}(W)${{< /katex >}}
and each triple of maps {{< katex >}}$f\colon X \to Y${{< /katex >}}, {{< katex >}}$g\colon Y \to Z${{< /katex >}} and {{< katex >}}$h\colon Z \to W${{< /katex >}}

{{< katex >}}$$\begin{CD}
f^*g^*h^*\xi @>f^*(\eta_{g,h}(\xi))>> f^*(hg)^* \xi \\
@VV\eta_{f,g}(h^*\xi)V @VV\eta_{f,gh}(\xi)V \\
(gf)^*h^*\xi @>\eta_{gf,h}(\xi)>> (hgf)^*\xi.
\end{CD}$${{< /katex >}}

This will use our only trick: consider the diagram

{{< katex >}}$$\begin{CD}
f^*g^*h^*\xi @>h_{\xi}g_{h^*\xi}f_{g^*h^*\xi}>> \xi \\
@VVV @| \\
(hgf)^*\xi @>(hgf)_\xi>> \xi.
\end{CD}$${{< /katex >}}

We calculate:

{{< katex >}}$$h_\xi g_{h^*\xi} f_{g^*h^*\xi} = (hg)_\xi \eta_{g,h}(\xi) f_{g^*h^*\xi}
= (hg)_\xi f_{(hg)^*\xi} f^*(\eta_{g,h}(\xi)) = (hgf)_\xi \eta_{f,gh}(\xi) f^*(\eta_{g,h}(\xi))$${{< /katex >}}

and

{{< katex >}}$$h_\xi g_{h^*\xi} f_{g^*h^*\xi} = h_\xi (gf)_{h^*\xi} \eta_{f,g}(h^*\xi)
= (hgf)_\xi \eta_{gf,h}(\xi) \eta_{f,g}(h^*\xi).$${{< /katex >}}

Therefore by the defining property of categories fibered in groupoids,
we have the coherence of the associating isomorphism.
The argument above is summarized in the commuting cube below,
where the unlabeled arrows are the "obvious" ones, for instance {{< katex >}}$h_\xi \colon h^*\xi \to \xi${{< /katex >}}.

![The commuting cube demonstrating the coherence of isomorphisms.](/img/2naturality.jpeg)

## Pseudonaturality in {{< katex >}}$\underline{X}${{< /katex >}}

Okay enough about pseudofunctors.
We already saw in a previous post that functors {{< katex >}}$\underline{Y} \to \underline{X}${{< /katex >}}
are maps {{< katex >}}$f\colon Y \to X${{< /katex >}}.
(Indeed, the proof uses the first part of the 2-Yoneda lemma.)
Such a functor gives us a functor 
{{< katex >}}$$f^*\colon \operatorname{Hom}(\underline{X},\mathsf{D}) 
\to \operatorname{Hom}(\underline{Y},\mathsf{D})$${{< /katex >}}
defined on objects (functors)
as {{< katex >}}$f^*F = Ff${{< /katex >}} and on arrows (natural transformations)
as {{< katex >}}$f^*(\alpha \colon F \Rightarrow G) = \alpha f \colon Ff \Rightarrow Gf${{< /katex >}}.
On the other side of the equation,
we have the functor {{< katex >}}$f^*\colon \mathsf{D}(X) \to \mathsf{D}(Y)${{< /katex >}}
defined extensively above.
Pseudonaturality in {{< katex >}}$X${{< /katex >}} then is the claim that the following diagram commutes

{{< katex >}}$$\begin{CD}
\operatorname{Hom}(\underline{X},\mathsf{D}) @>\operatorname{よ}_X>> \mathsf{D}(X) \\
@VVf^*V @VVf^*V \\
\operatorname{Hom}(\underline{Y},\mathsf{D}) @>\operatorname{よ}_Y>> \mathsf{D}(Y).
\end{CD}$${{< /katex >}}

up to a natural transformation.
And indeed, if {{< katex >}}$F(1_X) = \xi \in \mathsf{D}(X)${{< /katex >}}, we have
{{< katex >}}$f^*\operatorname{よ}_X(F) = f^*\xi${{< /katex >}}
and {{< katex >}}$\operatorname{よ}_Y(f^*F) = (f^*F)(1_Y) = F(f\colon Y \to X)${{< /katex >}}.
Now, recall from [part three] that we write {{< katex >}}$F(Y)${{< /katex >}}, since {{< katex >}}$f\colon Y \to X${{< /katex >}} is understood
and we'd like to consider the arrow {{< katex >}}$F(f) \colon F(Y) \to \xi${{< /katex >}}.
By the definition of categories fibered in groupoids, there is a unique isomorphism
{{< katex >}}$\sigma_{F,f}\colon F(Y) \to f^*\xi${{< /katex >}} satisfying {{< katex >}}$f_\xi \sigma_{F,f} = F(f)${{< /katex >}}.
We claim that {{< katex >}}$\sigma_{F,f}${{< /katex >}} defines a natural transformation making the diagram above commute.
This is the claim that for every natural transformation {{< katex >}}$\alpha\colon F\Rightarrow G${{< /katex >}}
in {{< katex >}}$\operatorname{Hom}(\underline{X},\mathsf{D})${{< /katex >}},
the following diagram commutes in {{< katex >}}$\mathsf{D}(Y)${{< /katex >}}:

{{< katex >}}$$\begin{CD}
\operatorname{よ}_Y(f^*F) @>\sigma_{F,f}>> f^*\operatorname{よ}_X(F) \\
@VV\operatorname{よ}_Y(f^*\alpha)V @VVf^*\operatorname{よ}_X(\alpha)V \\
 \operatorname{よ}_Y(f^*G) @>\sigma_{G,f}>> f^*\operatorname{よ}_X(G).
\end{CD}$${{< /katex >}}

Unwound slightly, if we write {{< katex >}}$G(X) = \xi'${{< /katex >}} and {{< katex >}}$\alpha \colon \xi \to \xi'${{< /katex >}},
this is the same diagram as

{{< katex >}}$$\begin{CD}
F(Y) @>\sigma_{F,f}>> f^*\xi \\
@VV\alpha(Y)V @VVf^*\alpha V \\
G(Y) @>\sigma_{F,f}>> f^*\xi'.
\end{CD}$${{< /katex >}}

The commutativity of this diagram uses our only trick, 
namely the unique way of filling this diagram:

{{< katex >}}$$\begin{CD}
F(Y) @>\alpha F(f)>> \xi' \\
@VVV @| \\
f^*\xi' @>f_{\xi'}>> \xi'.
\end{CD}$${{< /katex >}}

We check

{{< katex >}}$ \alpha F(f) = \alpha f_\xi \sigma_{F,f} = f_{\xi'} f^*\alpha \sigma_{F,f}${{< /katex >}}

and

{{< katex >}}$\alpha F(f) =  G(f)\alpha(Y) = f_{\xi'} \sigma_{G,f} \alpha(Y).${{< /katex >}}

## A loose end from part six

I think this proves a claim from [part six]. 
Let's test it out.
An object {{< katex >}}$\xi \in \mathsf{D}(Y)${{< /katex >}} is a map {{< katex >}}$f\colon \underline{Y} \to \mathsf{D}${{< /katex >}}.
Similarly {{< katex >}}$\xi' \in \mathsf{D}(X)${{< /katex >}} is a map {{< katex >}}$g\colon \underline{X} \to \mathsf{D}${{< /katex >}}.
An arrow {{< katex >}}$\tilde h \colon \xi \to \xi'${{< /katex >}} over a map {{< katex >}}$h\colon Y \to X${{< /katex >}}
should be the map {{< katex >}}$h \colon Y \to X${{< /katex >}} together with a natural transformation
{{< katex >}}$\alpha\colon f \Rightarrow gh${{< /katex >}}.

Let me write things a little more like the above. 
So we have {{< katex >}}$\xi \in \mathsf{D}(Y)${{< /katex >}} 
equal under {{< katex >}}$\operatorname{よ}_Y${{< /katex >}} to {{< katex >}}$F\colon \underline{Y} \to \mathsf{D}${{< /katex >}},
and similarly {{< katex >}}$\xi' = \operatorname{よ}_X(G)${{< /katex >}}.
We have the functor {{< katex >}}$\mathsf{D}(h) = h^*\colon \mathsf{D}(X) \to \mathsf{D}(Y)${{< /katex >}}
which corresponds up to natural transformation to precomposition by {{< katex >}}$h\colon Y \to X${{< /katex >}}.
There is a unique isomorphism {{< katex >}}$\beta${{< /katex >}} making the following diagram commute

{{< katex >}}$$\begin{CD}
\xi @>\tilde h>> \xi' \\
@VV\beta V @| \\
h^*\xi' @>h_{\xi'}>> \xi' \\
@AA\sigma_{G,h}A @| \\
Gh(1_Y) @>G(h)>> \xi'
\end{CD}$${{< /katex >}}

We claim that {{< katex >}}$\sigma_{G,h}^{-1}\beta${{< /katex >}} comes from (or defines) a unique natural transformation
{{< katex >}}$\alpha \colon F \Rightarrow Gh${{< /katex >}} 
(we write {{< katex >}}$Gh${{< /katex >}} to avoid confusion with the functor {{< katex >}}$h^*${{< /katex >}}).
At an object {{< katex >}}$k \colon Z \to Y${{< /katex >}} of {{< katex >}}$\underline{Y}${{< /katex >}},
define {{< katex >}}$\alpha(Z) = \sigma_{G,hk}^{-1} \eta_{k,h}(\xi') k^*\beta \sigma_{F,k}${{< /katex >}},
where {{< katex >}}$\eta_{k,h}(\xi') \colon k^*h^*\xi' \to (hk)^*\xi'${{< /katex >}} 
is the isomorphism defined in the previous section.
Given another object {{< katex >}}$\ell \colon W \to Y${{< /katex >}} and an arrow {{< katex >}}$m \colon Z \to W${{< /katex >}},
we need the following diagram to commute

{{< katex >}}$$\begin{CD}
F(Z) @>\alpha(Z)>> Gh(Z) \\
@VVF(m)V @VVGh(m)V \\
F(W) @>\alpha(W)>> Gh(W).
\end{CD}$${{< /katex >}}

Let's try putting both paths around the square into the diagram

{{< katex >}}$$\begin{CD}
F(Z) @>\tilde h F(k)>> \xi' \\
@VVV @| \\
Gh(W) @>G(h)Gh(\ell)>> \xi'.
\end{CD}$${{< /katex >}}

We calculate

{{< katex >}}$$\begin{gather*}
G(h)Gh(\ell)Gh(m) \alpha(Z) = G(h)Gh(k)\alpha(Z) = G(hk)\alpha(Z) \\
= (hk)_{\xi'} \sigma_{G,hk} \alpha(Z) = (hk)_{\xi'} \eta_{k,h}(\xi') k^*\beta \sigma_{F,k} \\
= h_{\xi'}k_{h^*\xi'} k^*\beta \sigma_{F,k} = h_{\xi'} \beta k_\xi \sigma_{F,k}
= h_{\xi'}\beta F(k) = \tilde h F(k)
\end{gather*}$${{< /katex >}}

and

{{< katex >}}$$\begin{gather*}
G(h)Gh(\ell)\alpha(W)F(m) = G(h\ell)\alpha(W)F(m) = (h\ell)_{\xi'}\sigma_{G,h\ell}\alpha(W)F(m) \\
= (h\ell)_{\xi'} \eta_{\ell,h}(\xi') \ell^*\beta \sigma_{F,\ell} F(m)
= h_{\xi'}\ell_{h^*\xi'} \ell^*\beta \sigma_{F,\ell} F(m) \\
= h_{\xi'}\beta \ell_\xi \sigma_{F,\ell} F(m) = h_{\xi'} \beta F(\ell)F(m) = h_{\xi'}\beta F(k)
= \tilde h F(k).
\end{gather*}$${{< /katex >}}

The argument is summarized in the following interesting commutative diagram.

![The argument above in commutative diagram form](/img/2naturality2.jpeg)

Conversely it is clear that given such an {{< katex >}}$\alpha \colon F \Rightarrow Gh${{< /katex >}}, 
we get a map {{< katex >}}$\tilde h \colon \xi \to \xi'${{< /katex >}}
defined by {{< katex >}}$G(h)\alpha(Y)${{< /katex >}}.

## Pseudonaturality in {{< katex >}}$\mathsf{D}${{< /katex >}}

Now suppose we have a map of categories fibered in groupoids 
{{< katex >}}$f\colon \mathsf{C} \to \mathsf{D}${{< /katex >}}.
This is by definition a functor {{< katex >}}$f\colon \mathsf{C} \to \mathsf{D}${{< /katex >}}
such that {{< katex >}}$\pi f = \pi${{< /katex >}}.
For each {{< katex >}}$\xi \in \mathsf{C}(X)${{< /katex >}}, we get an object {{< katex >}}$f(\xi) \in \mathsf{D}(X)${{< /katex >}},
and for each arrow {{< katex >}}$\alpha \colon \xi \to \xi'${{< /katex >}} in the fiber, 
we get an arrow {{< katex >}}$f(\alpha)\colon f(\xi) \to f(\xi')${{< /katex >}} in the fiber.
In other words, we get a functor {{< katex >}}$f|_X \colon \mathsf{C}(X) \to \mathsf{D}(X)${{< /katex >}}.
Given a functor {{< katex >}}$F\colon \underline{X} \to \mathsf{C}${{< /katex >}}, postcomposition with {{< katex >}}$f${{< /katex >}}
yields a functor {{< katex >}}$f_*F = fF \colon \underline{X} \to \mathsf{D}${{< /katex >}}.
Similarly given a natural transformation {{< katex >}}$\alpha\colon F\Rightarrow G${{< /katex >}},
we get {{< katex >}}$f_*\alpha \colon f_*F\Rightarrow f_*G${{< /katex >}}.
Pseudonaturality in {{< katex >}}$\mathsf{D}${{< /katex >}} is the claim that the following diagram commutes

{{< katex >}}$$\begin{CD}
\operatorname{Hom}(\underline{X},\mathsf{C}) @>\operatorname{よ}_{\mathsf{C}}>> \mathsf{C}(X) \\
@VVf_*V @VVf|_XV \\
\operatorname{Hom}(\underline{X},\mathsf{D}) @>\operatorname{よ}_{\mathsf{D}}>> \mathsf{D}(X)
\end{CD}$${{< /katex >}}

up to a natural transformation.
And indeed, if we write {{< katex >}}$F(1_X) = \xi${{< /katex >}}, {{< katex >}}$G(1_X) = \xi'${{< /katex >}}
and {{< katex >}}$\alpha(1_X) = \alpha \colon \xi \to \xi'${{< /katex >}}, we actually have

{{< katex >}}$$f|_X\operatorname{よ}_{\mathsf{C}}(F) = f|_X(\xi) = f(\xi) = f_*F(1_X) 
= \operatorname{よ}_{\mathsf{D}}(f_*F)$${{< /katex >}}

and

{{< katex >}}$$f|_X\operatorname{よ}_{\mathsf{C}}(\alpha) = f|_X(\alpha) = f(\alpha) = f_*\alpha(1_X)
= \operatorname{よ}_{\mathsf{D}}(f_*\alpha),$${{< /katex >}}

so the diagram actually commutes on the nose.

[part three]: {{< ref "pursued-by-stacks-3:-we-need-a-lemma.md" >}}
[part six]: {{< ref "pursued-by-stacks-6:-stacks-and-groupoids.md" >}}
