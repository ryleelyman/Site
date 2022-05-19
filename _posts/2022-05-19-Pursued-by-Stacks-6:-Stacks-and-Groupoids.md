---
layout: post
math: true
---
In writing this post, I started to see what's kind of cool about stacks:
you can treat them almost as if they were spaces
in the sense that, as you'll see, objects of a stack $$\mathsf{D}$$ over a space $$Y$$
are the same thing as maps of stacks $$Y \to \mathsf{D}$$,
just like the situation of $$\underline{X}$$ for a space $$X$$.
The difference is that $$\mathsf{D}$$ may have many isomorphisms *stacked* over 
$$Y \to \mathsf{D}$$
while $$\underline{X}$$ has only the identity of $$Y$$.

In what might be the final post on stacks for a while,
I'd like to show that every topological stack is isomorphic to
$$\mathsf{B}\mathcal{G}$$ for some topological groupoid $$\mathcal{G}$$.
We could then say that, for instance, a graph of groups
is any stack isomorphic to $$\mathsf{B}\mathcal{G}$$,
where $$\mathcal{G}$$ is the étale groupoid we constructed [in a previous post].


Suppose $$\mathsf{D}$$ is a topological stack
with an atlas $$p\colon X \to \mathsf{D}$$.
We claim that $$X \times_{\mathsf{D}} X$$ 
(which is a space since $$X$$ is an atlas)
is a space of arrows for a groupoid $$\mathcal{G}$$ with space of objects $$X$$.
That finished,
we will construct an isomorphism $$\psi\colon \mathsf{D} \to \mathsf{B}\mathcal{G}$$.

Thus we are in search of structure maps for our groupoid.
By the 2-Yoneda lemma, 
if $$X$$ and $$Y$$ are spaces, any map of stacks $$X \to Y$$
is determined up to natural isomorphism by an object of $$\underline{Y}$$ over $$X$$;
in other words, a continuous map $$f\colon X \to Y$$.
But because the fiber of $$\underline{Y}$$ comprises only the identity arrow,
this map $$f$$ is in fact unique.
Therefore, it suffices to produce maps of stacks for our structure maps.

We take source and target maps of $$\mathcal{G}$$ to be the two projections
from $$X\times_{\mathsf{D}} X$$ to $$X$$.
In more words, $$(x,y,f) \mapsto X$$ and $$(x,y,f) \mapsto Y$$.
Note that the diagram

$$\require{AMScd}\begin{CD}
X @>1_X>> X \\
@VV1_XV @VVpV \\
X @>p>> \mathsf{D}
\end{CD}$$

commutes (on the nose),
so there is a map $$X \to X\times_{\mathsf{D}} X$$.
If you chase through the definition of maps to the 2-fiber product,
you see that on objects the map is $$Y \mapsto (Y,Y,1_Y)$$.

The multiplication map 

$$m\colon (X\times_{\mathsf{D}}X)\times_X(X\times_{\mathsf{D}}X) \to X \times_{\mathsf{D}} X$$

is defined on objects as $$((x,y,f),(y,z,g) = (x,z,gf)$$.
This multiplication is associative because composition of arrows in $$\mathsf{D}$$ is associative.
The inversion map $$(\cdot)^{-1}$$ is given on objects as

$$(x,y,f)^{-1} = (y,x,f^{-1}).$$

So far we have not used any of the stack properties, 
merely that the category is fibered in groupoids.
(I cannot help myself: if the category were merely fibered in categories, 
whatever that might mean, we would end up with a category which is not a groupoid.)

Now we define $$\psi\colon \mathsf{D} \to \mathsf{B}\mathcal{G}$$.
This means that to each object of $$\mathsf{D}$$ over a space $$Y$$,
we need to produce a principal $$\mathcal{G}$$-bundle over $$Y$$.

Recall that by the 2-Yoneda lemma an object of $$\mathsf{D}$$ over $$Y$$
is the same thing as a map of stacks $$f\colon Y \to \mathsf{D}$$.
Since $$X$$ is an atlas, the fiber product $$Y \times_{\mathsf{D}} X$$ is a space
and the map $$Y\times_{\mathsf{D}} X \to Y$$ is an open surjection which admits local sections.
We let the projection $$Y\times_{\mathsf{D}} X \to X$$ be the anchor map
for the right action of $$\mathcal{G}$$ defined on objects as

$$\begin{gather*}
(Y\times_{\mathsf{D}} X)\times_X(X\times_{\mathsf{D}}X) \to Y \times_{\mathsf{D}} X \\
((y,x_2,f),(x_1,x_2,g)) \mapsto (y,x_1,g^{-1}f).
\end{gather*}$$

(This disagrees with [Lerman] but is the correct definition for a *right* action.)

The map

$$(Y\times_{\mathsf{D}}X)\times_X\mathcal{G}_1 
\to (Y\times_{\mathsf{D}}X)\times_Y(Y\times_{\mathsf{D}}X)$$

defined by

$$((y,x_2,f),(x_1,x_2,g)) \mapsto ((y,x_2,f),(y,x_1,g^{-1}f))$$

is clearly (the action on objects of) an isomorphism of stacks,
so the action of $$\mathcal{G}$$ on $$(Y\times_{\mathsf{D}}X)$$ is free and transitive.
Thus we define $$\psi(f\colon M \to \mathsf{D})$$ to be the principal $$\mathcal{G}$$-bundle
$$Y \times_{\mathsf{D}}X \to Y$$.

Now, if an object of $$\mathsf{D}$$ over a space $$Y$$ is a map $$f\colon Y \to \mathsf{D}$$
and an object of $$\mathsf{D}$$ over a space $$Z$$ is a map $$g \colon Z \to \mathsf{D}$$,
then an arrow of $$\mathsf{D}$$ over the map $$h \colon Y \to Z$$
should in fact be the map $$h \colon Y \to Z$$ making the diagram

$$\begin{CD}
Y @>f>> \mathsf{D} \\
@VVhV @| \\
Z @>g>> \mathsf{D}
\end{CD}$$

commute—at least, up to a specified natural isomorphism $$\eta\colon f \Rightarrow gh$$.
I think this is a missing naturality statement in the 2-Yoneda lemma,
so expect an appendix.
If we believe that for now, let's continue.

Now notice that we get a commutative diagram

$$\begin{CD}
Y \times_{\mathsf{D}} X @>>> X \\
@VVh\pi V @VVpV \\
Z @>g>> \mathsf{D}
\end{CD}$$

up to the composite natural transformation $$\epsilon\eta$$
(where $$\epsilon$$ is the defining natural transformation for the fiber product
$$Y\times_{\mathsf{D}} X$$).
Therefore by the universal property of the 2-fiber product,
we get a map $$\tilde h\colon Y\times_{\mathsf{D}}X \to Z\times_{\mathsf{D}}X$$
such that the following diagram commutes

$$\begin{CD}
Y\times_{\mathsf{D}}X @>\tilde h>> Z\times_{\mathsf{D}}X \\
@VV\pi V @VV\pi V \\
Y @>h>> Z
\end{CD}$$

up to a natural isomorphism, which must be the identity,
because every object in the diagram is a space.
Specifically, chasing through the map as described when we considered 2-fiber products,
on objects we have
$$\tilde h(y,x,f) = (h(y),x,f)$$.
It is clear from this definition that $$\tilde h$$ is $$\mathcal{G}$$-equivariant,
and that $$\psi$$ is functorial and fully faithful.
We still haven't used that $$\mathsf{D}$$ is a stack!

To complete the proof, we need to show that $$\psi$$ is essentially surjective.
First, we show it for $$\mathcal{G}$$-bundles with a global section.
By an argument I think I failed to give—if so, sorry—such a bundle
is (canonically isomorphic to) 
the pullback bundle $$f^*\mathcal{G}_1$$ by a map $$f\colon Y \to X$$.
Now, given such a map $$f\colon Y \to X$$,
notice that the silly diagram

$$\begin{CD}
Y @>pf>> \mathsf{D} \\
@VVfV @| \\
X @>p>> \mathsf{D}
\end{CD}$$

commutes on the nose, so certainly up to natural transformation.
The bundle $$\psi(pf)$$ is $$Y\times_{\mathsf{D}}X$$ over $$Y$$,
which has an equivariant map $$\psi(f)$$ to $$\mathcal{G}_1$$
and hence an isomorphism $$Y\times_{\mathsf{D}}X \cong f^*\mathcal{G}_1$$.
Therefore $$Y\times_{\mathsf{D}}X$$ has a global section $$\sigma$$
with the property, if you chase it through,
that $$\pi_2\sigma \colon Y\times_{\mathsf{D}}X \to X$$ is $$k$$.

Similarly, if we have a commuting diagram of spaces

$$\begin{CD}
Y @>f>> X \\
@VVhV @| \\
Z @>g>> X
\end{CD}$$

then composing with $$p\colon X \to \mathsf{D}$$ yields a commuting map of stacks,
i.e. a map between the bundles $$\psi(f)$$ and $$\psi(g)$$.
This map is (isomorphic to) $$\tilde h\colon f^*\mathcal{G}_1 \to g^*\mathcal{G}_1$$.
Therefore the full subcategory of $$\mathsf{B}\mathcal{G}$$
spanned by the bundles which have global sections is in the image of $$\psi$$.

Now suppose $$E$$ is a principal $$\mathcal{G}$$-bundle over a space $$Y$$.
Then $$Y$$ has an open cover $$\mathcal{U} = \{U_i\}_{i\in I}$$
with the property that each $$\iota_i^*E$$ has a global section.
The pullbacks of intersections define a descent datum for this open cover,
which lives in the image of $$\psi$$.
Thus since $$\mathsf{D}$$ is a stack, the descent datum is effective,
giving us an element $$\xi$$ of $$\mathsf{D}$$.
By functoriality of $$\mathsf{D}$$ and since isomorphisms form a sheaf,
we conclude that $$\psi(\xi)$$ is isomorphic to $$E$$,
showing that $$\psi$$ is essentially surjective.

Let us remark that atlases are super not unique,
but that if we have two atlases $$p\colon X \to \mathsf{D}$$ and $$q\colon Y \to \mathsf{D}$$
we can construct a bibundle $$P = X\times_{\mathsf{D}} Y$$
which is principal for both resulting groupoids.
Therefore the bibundle is invertible.
Put another way, the groupoids are equivalent.

[Lerman]: https://ems.press/content/serial-article-files/6839
[in a previous post]: {% link _posts/2022-05-14-Graphs-of-groups-as-étale-groupoids.md %}
