---
title: "Pursued by Stacks 6: Stacks and Groupoids"
date: 2022-05-19T15:57:47-04:00
math: true
---
In writing this post, I started to see what's kind of cool about stacks:
you can treat them almost as if they were spaces
in the sense that, as you'll see, objects of a stack {{< katex >}}$\mathsf{D}${{< /katex >}} over a space {{< katex >}}$Y${{< /katex >}}
are the same thing as maps of stacks {{< katex >}}$Y \to \mathsf{D}${{< /katex >}},
just like the situation of {{< katex >}}$\underline{X}${{< /katex >}} for a space {{< katex >}}$X${{< /katex >}}.
The difference is that {{< katex >}}$\mathsf{D}${{< /katex >}} may have many isomorphisms *stacked* over 
{{< katex >}}$Y \to \mathsf{D}${{< /katex >}}
while {{< katex >}}$\underline{X}${{< /katex >}} has only the identity of {{< katex >}}$Y${{< /katex >}}.

In what might be the final post on stacks for a while,
I'd like to show that every topological stack is isomorphic to
{{< katex >}}$\mathsf{B}\mathcal{G}${{< /katex >}} for some topological groupoid {{< katex >}}$\mathcal{G}${{< /katex >}}.
We could then say that, for instance, a graph of groups
is any stack isomorphic to {{< katex >}}$\mathsf{B}\mathcal{G}${{< /katex >}},
where {{< katex >}}$\mathcal{G}${{< /katex >}} is the étale groupoid we constructed [in a previous post].


Suppose {{< katex >}}$\mathsf{D}${{< /katex >}} is a topological stack
with an atlas {{< katex >}}$p\colon X \to \mathsf{D}${{< /katex >}}.
We claim that {{< katex >}}$X \times_{\mathsf{D}} X${{< /katex >}} 
(which is a space since {{< katex >}}$X${{< /katex >}} is an atlas)
is a space of arrows for a groupoid {{< katex >}}$\mathcal{G}${{< /katex >}} with space of objects {{< katex >}}$X${{< /katex >}}.
That finished,
we will construct an isomorphism {{< katex >}}$\psi\colon \mathsf{D} \to \mathsf{B}\mathcal{G}${{< /katex >}}.

Thus we are in search of structure maps for our groupoid.
By the 2-Yoneda lemma, 
if {{< katex >}}$X${{< /katex >}} and {{< katex >}}$Y${{< /katex >}} are spaces, any map of stacks {{< katex >}}$X \to Y${{< /katex >}}
is determined up to natural isomorphism by an object of {{< katex >}}$\underline{Y}${{< /katex >}} over {{< katex >}}$X${{< /katex >}};
in other words, a continuous map {{< katex >}}$f\colon X \to Y${{< /katex >}}.
But because the fiber of {{< katex >}}$\underline{Y}${{< /katex >}} comprises only the identity arrow,
this map {{< katex >}}$f${{< /katex >}} is in fact unique.
Therefore, it suffices to produce maps of stacks for our structure maps.

We take source and target maps of {{< katex >}}$\mathcal{G}${{< /katex >}} to be the two projections
from {{< katex >}}$X\times_{\mathsf{D}} X${{< /katex >}} to {{< katex >}}$X${{< /katex >}}.
In more words, {{< katex >}}$(x,y,f) \mapsto X${{< /katex >}} and {{< katex >}}$(x,y,f) \mapsto Y${{< /katex >}}.
Note that the diagram

{{< katex >}}$$\begin{CD}
X @>1_X>> X \\
@VV1_XV @VVpV \\
X @>p>> \mathsf{D}
\end{CD}$${{< /katex >}}

commutes (on the nose),
so there is a map {{< katex >}}$X \to X\times_{\mathsf{D}} X${{< /katex >}}.
If you chase through the definition of maps to the 2-fiber product,
you see that on objects the map is {{< katex >}}$Y \mapsto (Y,Y,1_Y)${{< /katex >}}.

The multiplication map 

{{< katex >}}$m\colon (X\times_{\mathsf{D}}X)\times_X(X\times_{\mathsf{D}}X) \to X \times_{\mathsf{D}} X${{< /katex >}}

is defined on objects as {{< katex >}}$((x,y,f),(y,z,g) = (x,z,gf)${{< /katex >}}.
This multiplication is associative because composition of arrows in {{< katex >}}$\mathsf{D}${{< /katex >}} is associative.
The inversion map {{< katex >}}$(\cdot)^{-1}${{< /katex >}} is given on objects as

{{< katex >}}$(x,y,f)^{-1} = (y,x,f^{-1}).${{< /katex >}}

So far we have not used any of the stack properties, 
merely that the category is fibered in groupoids.
(I cannot help myself: if the category were merely fibered in categories, 
whatever that might mean, we would end up with a category which is not a groupoid.)

Now we define {{< katex >}}$\psi\colon \mathsf{D} \to \mathsf{B}\mathcal{G}${{< /katex >}}.
This means that to each object of {{< katex >}}$\mathsf{D}${{< /katex >}} over a space {{< katex >}}$Y${{< /katex >}},
we need to produce a principal {{< katex >}}$\mathcal{G}${{< /katex >}}-bundle over {{< katex >}}$Y${{< /katex >}}.

Recall that by the 2-Yoneda lemma an object of {{< katex >}}$\mathsf{D}${{< /katex >}} over {{< katex >}}$Y${{< /katex >}}
is the same thing as a map of stacks {{< katex >}}$f\colon Y \to \mathsf{D}${{< /katex >}}.
Since {{< katex >}}$X${{< /katex >}} is an atlas, the fiber product {{< katex >}}$Y \times_{\mathsf{D}} X${{< /katex >}} is a space
and the map {{< katex >}}$Y\times_{\mathsf{D}} X \to Y${{< /katex >}} is an open surjection which admits local sections.
We let the projection {{< katex >}}$Y\times_{\mathsf{D}} X \to X${{< /katex >}} be the anchor map
for the right action of {{< katex >}}$\mathcal{G}${{< /katex >}} defined on objects as

{{< katex >}}$$\begin{gather*}
(Y\times_{\mathsf{D}} X)\times_X(X\times_{\mathsf{D}}X) \to Y \times_{\mathsf{D}} X \\
((y,x_2,f),(x_1,x_2,g)) \mapsto (y,x_1,g^{-1}f).
\end{gather*}$${{< /katex >}}

(This disagrees with [Lerman] but is the correct definition for a *right* action.)

The map

{{< katex >}}$$(Y\times_{\mathsf{D}}X)\times_X\mathcal{G}_1 
\to (Y\times_{\mathsf{D}}X)\times_Y(Y\times_{\mathsf{D}}X)$${{< /katex >}}

defined by

{{< katex >}}$((y,x_2,f),(x_1,x_2,g)) \mapsto ((y,x_2,f),(y,x_1,g^{-1}f))${{< /katex >}}

is clearly (the action on objects of) an isomorphism of stacks,
so the action of {{< katex >}}$\mathcal{G}${{< /katex >}} on {{< katex >}}$(Y\times_{\mathsf{D}}X)${{< /katex >}} is free and transitive.
Thus we define {{< katex >}}$\psi(f\colon M \to \mathsf{D})${{< /katex >}} to be the principal {{< katex >}}$\mathcal{G}${{< /katex >}}-bundle
{{< katex >}}$Y \times_{\mathsf{D}}X \to Y${{< /katex >}}.

Now, if an object of {{< katex >}}$\mathsf{D}${{< /katex >}} over a space {{< katex >}}$Y${{< /katex >}} is a map {{< katex >}}$f\colon Y \to \mathsf{D}${{< /katex >}}
and an object of {{< katex >}}$\mathsf{D}${{< /katex >}} over a space {{< katex >}}$Z${{< /katex >}} is a map {{< katex >}}$g \colon Z \to \mathsf{D}${{< /katex >}},
then an arrow of {{< katex >}}$\mathsf{D}${{< /katex >}} over the map {{< katex >}}$h \colon Y \to Z${{< /katex >}}
should in fact be the map {{< katex >}}$h \colon Y \to Z${{< /katex >}} making the diagram

{{< katex >}}$$\begin{CD}
Y @>f>> \mathsf{D} \\
@VVhV @| \\
Z @>g>> \mathsf{D}
\end{CD}$${{< /katex >}}

commute—at least, up to a specified natural isomorphism {{< katex >}}$\eta\colon f \Rightarrow gh${{< /katex >}}.
I think this is a missing naturality statement in the 2-Yoneda lemma,
so expect an appendix.
If we believe that for now, let's continue.

Now notice that we get a commutative diagram

{{< katex >}}$$\begin{CD}
Y \times_{\mathsf{D}} X @>>> X \\
@VVh\pi V @VVpV \\
Z @>g>> \mathsf{D}
\end{CD}$${{< /katex >}}

up to the composite natural transformation {{< katex >}}$\epsilon\eta${{< /katex >}}
(where {{< katex >}}$\epsilon${{< /katex >}} is the defining natural transformation for the fiber product
{{< katex >}}$Y\times_{\mathsf{D}} X${{< /katex >}}).
Therefore by the universal property of the 2-fiber product,
we get a map {{< katex >}}$\tilde h\colon Y\times_{\mathsf{D}}X \to Z\times_{\mathsf{D}}X${{< /katex >}}
such that the following diagram commutes

{{< katex >}}$$\begin{CD}
Y\times_{\mathsf{D}}X @>\tilde h>> Z\times_{\mathsf{D}}X \\
@VV\pi V @VV\pi V \\
Y @>h>> Z
\end{CD}$${{< /katex >}}

up to a natural isomorphism, which must be the identity,
because every object in the diagram is a space.
Specifically, chasing through the map as described when we considered 2-fiber products,
on objects we have
{{< katex >}}$\tilde h(y,x,f) = (h(y),x,f)${{< /katex >}}.
It is clear from this definition that {{< katex >}}$\tilde h${{< /katex >}} is {{< katex >}}$\mathcal{G}${{< /katex >}}-equivariant,
and that {{< katex >}}$\psi${{< /katex >}} is functorial and fully faithful.
We still haven't used that {{< katex >}}$\mathsf{D}${{< /katex >}} is a stack!

To complete the proof, we need to show that {{< katex >}}$\psi${{< /katex >}} is essentially surjective.
First, we show it for {{< katex >}}$\mathcal{G}${{< /katex >}}-bundles with a global section.
By an argument I think I failed to give—if so, sorry—such a bundle
is (canonically isomorphic to) 
the pullback bundle {{< katex >}}$f^*\mathcal{G}_1${{< /katex >}} by a map {{< katex >}}$f\colon Y \to X${{< /katex >}}.
Now, given such a map {{< katex >}}$f\colon Y \to X${{< /katex >}},
notice that the silly diagram

{{< katex >}}$$\begin{CD}
Y @>pf>> \mathsf{D} \\
@VVfV @| \\
X @>p>> \mathsf{D}
\end{CD}$${{< /katex >}}

commutes on the nose, so certainly up to natural transformation.
The bundle {{< katex >}}$\psi(pf)${{< /katex >}} is {{< katex >}}$Y\times_{\mathsf{D}}X${{< /katex >}} over {{< katex >}}$Y${{< /katex >}},
which has an equivariant map {{< katex >}}$\psi(f)${{< /katex >}} to {{< katex >}}$\mathcal{G}_1${{< /katex >}}
and hence an isomorphism {{< katex >}}$Y\times_{\mathsf{D}}X \cong f^*\mathcal{G}_1${{< /katex >}}.
Therefore {{< katex >}}$Y\times_{\mathsf{D}}X${{< /katex >}} has a global section {{< katex >}}$\sigma${{< /katex >}}
with the property, if you chase it through,
that {{< katex >}}$\pi_2\sigma \colon Y\times_{\mathsf{D}}X \to X${{< /katex >}} is {{< katex >}}$k${{< /katex >}}.

Similarly, if we have a commuting diagram of spaces

{{< katex >}}$$\begin{CD}
Y @>f>> X \\
@VVhV @| \\
Z @>g>> X
\end{CD}$${{< /katex >}}

then composing with {{< katex >}}$p\colon X \to \mathsf{D}${{< /katex >}} yields a commuting map of stacks,
i.e. a map between the bundles {{< katex >}}$\psi(f)${{< /katex >}} and {{< katex >}}$\psi(g)${{< /katex >}}.
This map is (isomorphic to) {{< katex >}}$\tilde h\colon f^*\mathcal{G}_1 \to g^*\mathcal{G}_1${{< /katex >}}.
Therefore the full subcategory of {{< katex >}}$\mathsf{B}\mathcal{G}${{< /katex >}}
spanned by the bundles which have global sections is in the image of {{< katex >}}$\psi${{< /katex >}}.

Now suppose {{< katex >}}$E${{< /katex >}} is a principal {{< katex >}}$\mathcal{G}${{< /katex >}}-bundle over a space {{< katex >}}$Y${{< /katex >}}.
Then {{< katex >}}$Y${{< /katex >}} has an open cover {{< katex >}}$\mathcal{U} = \{U_i\}_{i\in I}${{< /katex >}}
with the property that each {{< katex >}}$\iota_i^*E${{< /katex >}} has a global section.
The pullbacks of intersections define a descent datum for this open cover,
which lives in the image of {{< katex >}}$\psi${{< /katex >}}.
Thus since {{< katex >}}$\mathsf{D}${{< /katex >}} is a stack, the descent datum is effective,
giving us an element {{< katex >}}$\xi${{< /katex >}} of {{< katex >}}$\mathsf{D}${{< /katex >}}.
By functoriality of {{< katex >}}$\mathsf{D}${{< /katex >}} and since isomorphisms form a sheaf,
we conclude that {{< katex >}}$\psi(\xi)${{< /katex >}} is isomorphic to {{< katex >}}$E${{< /katex >}},
showing that {{< katex >}}$\psi${{< /katex >}} is essentially surjective.

Let us remark that atlases are super not unique,
but that if we have two atlases {{< katex >}}$p\colon X \to \mathsf{D}${{< /katex >}} and {{< katex >}}$q\colon Y \to \mathsf{D}${{< /katex >}}
we can construct a bibundle {{< katex >}}$P = X\times_{\mathsf{D}} Y${{< /katex >}}
which is principal for both resulting groupoids.
Therefore the bibundle is invertible.
Put another way, the groupoids are equivalent.

[Lerman]: https://ems.press/content/serial-article-files/6839
[in a previous post]: {{< ref "graphs-of-groups-as-etale-groupoids.md" >}}
