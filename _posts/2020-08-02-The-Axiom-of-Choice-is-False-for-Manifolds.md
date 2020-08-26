---
layout: post
math: true
published: true
---
This is a post about one of those things that is really a case of category theory
cheekily playing with unhooking a signifier from what it typically signifies.
Namely, one of the (many) tricky foundational things about working with orbifolds
goes by the name "the axiom of choice is false for the category of smooth manifolds."

One way to misinterpret the statement is to take it literally:
as undergraduate math majors learn, the axiom of choice says that given an infinite collection of sets,
you can always choose exactly one element of each set, even if the collection is infinite.
Therefore the statement "the axiom of choice is false for the category of smooth manifolds"
could reasonably be thought to mean "given a collection of smooth manifolds,
which are in particular sets with additional structure,
it is *not* the case that you can always choose a point in each manifold if the collection is sufficiently large."
Of course, if we accept the axiom of choice 
(I do, since I like the 
[Nielsen–Schreier theorem](https://en.wikipedia.org/wiki/Nielsen–Schreier_theorem#Axiomatic_foundations)
which says that subgroups of free groups are free), 
then this statement is nonsense: it doesn't matter if the collection of sets is really a collection of manifolds
or a collection of the contents of various grocery stores, we can always choose one element from each.
What, then, does this statement mean?

As it turns out, there are two statements equivalent to the axiom of choice that have category-theoretic import.
This post is primarily concerned with the latter, but the former is too cute to pass up.

## Every Epimorphism Splits

Set theory is kind of in an odd position within mathematics.
I read some complaint that most mathematicians see sets every day
and yet have never seen sets be *interesting,* 
and so discount the possibility that set theory could be a worthwhile pursuit.
The standard formulation of set theory as a foundation for mathematics is somewhat unfortunate, too:
if we take the axioms of Zermelo–Frankel set theory too literally, then we notice that everything is a set,
even the elements of sets.
Thus nonsensical questions like "what are the elements of 6" are allowable on a technicality.

I learned this complaint, and everything in this section, from a beautiful 8-page article by Tom Leinster called
["Rethinking Set Theory"](https://arxiv.org/pdf/1212.6543.pdf) from which I'd like to quote most of the abstract:

> Mathematicians manipulate sets with confidence almost every day, rarely making mistakes. 
> Few of us, however, could accurately quote what are often referred to as "the" axioms of set theory. 
> This suggests that we all carry around with us, perhaps subconsciously, 
> a reliable body of operating principles for manipulating sets. 
> What if we were to take some of those principles and adopt them as our axioms instead? 
> The message of this article is that this can be done, in a simple, practical way (due to Lawvere). 
> The resulting axioms are ten thoroughly mundane statements about sets. 

Of these axioms, the formulation of the axiom of choice is perhaps the most devastatingly simple:

> **10.** Every [surjective function of sets] has a right inverse.

To see that this is really equivalent, notice that if $$p\colon S \to T$$ is a surjective function of sets,
then we may identify $$S$$ with the disjoint union

$$ \coprod_{t \in T} p^{-1}(t). $$

A *right inverse* for the function $$p$$ is a function $$i \colon T \to S$$
such that $$p(i(t)) = t$$ for all $$t$$ in $$T$$.
Notice that this means that $$i\colon T \to S$$ picks out one element of $$p^{-1}(t)$$ as $$t$$
varies over the elements of $$T$$,
so the existence of such a function is equivalent to being able to perform choice in the sense that we said above!

This axiom can be reformulated in any category:
the correct generalization of a surjective function is called an *epimorphism;*
for categories of "sets with additional structure" (e.g. groups, rings, manifolds) the surjective maps 
are epimorphisms, but the converse is not always true.

A right inverse for an arrow $$f\colon c \to d$$ makes sense in any category:
it's an arrow $$r \colon d \to c$$ such that $$fr$$ is the identity arrow of $$c$$.
It's a general fact that admitting a right inverse implies that the arrow is an epimorphism,
even though we haven't defined what that is.
In fact, for categories of "sets with additional structure" if $$f$$ admits a right inverse,
then it is surjective.
We say $$f$$ is a *split epimorphism* (the name comes from "split exact sequences" of e.g. groups).

This allows us to cheekily reformulate the axiom of choice in any category as the following statement

> **The Axiom of Choice for a Category:** every epimorphism is split.

This axiom fails for smooth manifolds:
a surjective map from the real line to the unit circle in $$\mathbb R^2$$ given by sending $$x$$
to $$(\cos x,\sin x)$$ for instance, fails to have a right inverse.

## An Equivalent Definition of Equivalence of Categories

Another use of the axiom of choice in category theory is the following theorem:

> **Theorem:** A functor $$F\colon C \to D$$ between categories $$C$$ and $$D$ is an *equivalence of categories*
> if and only if it is *fully faithful* and *essentially surjective.*

Here the functor $$F$$ is *full* if for all objects $$c$$ and $$c'$$ in $$C$$, the function
$$F\colon C(c,c') \to D(Fc,Fc')$$ is surjective, and *faithful* if it is injective.
So $$F$$ is *fully faithful* if it induces a bijection from the set of arrows betwwen any two objects in $$C$$
to their images in $$D$$.

The functor $$F$$ is *essentially surjective* if every object $$d \in D$$ is isomorphic to $$Fc$$ for some
$$c \in C$$.

Finally an *equivalence of categories* is a functor $$F\colon C \to D$$ such that there exists an "inverse"
functor $$G \colon D \to C$$ and natural isomorphisms between the two double compositions and the
identity functors of $$C$$ and $$D$$, respectively.

The proof that an equivalence of categories has the above properties is fairly simple: in an alternate universe,
this blog post would give it, and show that the converse requires the axiom of choice.
Let me just content myself with pointing out that the use of the axiom of choice is to pick
a $$c$$ such that $$Fc$$ is isomorphic to $$d$$ for all $$d \in D$$.
In fact, it turns out that the theorem is *equivalent* to the axiom of choice,
if you make the appropriate definitions of the categories involved.
(e.g. $$D$$ should be an index set, and $$C$$ a clever category based on a collection
of sets indexed by $$D$$.)

One can define (small) categories *internal* to a category and 
do category theory in this way. Thus one way to phrase the axiom of choice for a category is:

> **The Axiom of Choice for a Category:** A functor between categories internal to $$C$$
> is an equivalence if and only if it is fully faithful and essentially surjective.

It turns out that the category of smooth manifolds *also* fails this axiom,
essentially because it fails the previous one!
