---
title: "The Axiom of Choice Is False for Manifolds"
date: 2020-08-02T13:55:19-04:00
math: true
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

To see that this is really equivalent, notice that if {{< katex >}}$p\colon S \to T${{< /katex >}} is a surjective function of sets,
then we may identify {{< katex >}}$S${{< /katex >}} with the disjoint union

{{< katex >}}$ \coprod_{t \in T} p^{-1}(t). ${{< /katex >}}

A *right inverse* for the function {{< katex >}}$p${{< /katex >}} is a function {{< katex >}}$i \colon T \to S${{< /katex >}}
such that {{< katex >}}$p(i(t)) = t${{< /katex >}} for all {{< katex >}}$t${{< /katex >}} in {{< katex >}}$T${{< /katex >}}.
Notice that this means that {{< katex >}}$i\colon T \to S${{< /katex >}} picks out one element of {{< katex >}}$p^{-1}(t)${{< /katex >}} as {{< katex >}}$t${{< /katex >}}
varies over the elements of {{< katex >}}$T${{< /katex >}},
so the existence of such a function is equivalent to being able to perform choice in the sense that we said above!

This axiom can be reformulated in any category:
the correct generalization of a surjective function is called an *epimorphism;*
for categories of "sets with additional structure" (e.g. groups, rings, manifolds) the surjective maps 
are epimorphisms, but the converse is not always true.

A right inverse for an arrow {{< katex >}}$f\colon c \to d${{< /katex >}} makes sense in any category:
it's an arrow {{< katex >}}$r \colon d \to c${{< /katex >}} such that {{< katex >}}$fr${{< /katex >}} is the identity arrow of {{< katex >}}$c${{< /katex >}}.
It's a general fact that admitting a right inverse implies that the arrow is an epimorphism,
even though we haven't defined what that is.
In fact, for categories of "sets with additional structure" if {{< katex >}}$f${{< /katex >}} admits a right inverse,
then it is surjective.
We say {{< katex >}}$f${{< /katex >}} is a *split epimorphism* (the name comes from "split exact sequences" of e.g. groups).

This allows us to cheekily reformulate the axiom of choice in any category as the following statement

> **The Axiom of Choice for a Category:** every epimorphism is split.

This axiom fails for smooth manifolds:
a surjective map from the real line to the unit circle in {{< katex >}}$\mathbb R^2${{< /katex >}} given by sending {{< katex >}}$x${{< /katex >}}
to {{< katex >}}$(\cos x,\sin x)${{< /katex >}} for instance, fails to have a right inverse.

## An Equivalent Definition of Equivalence of Categories

Another use of the axiom of choice in category theory is the following theorem:

> **Theorem:** A functor {{< katex >}}$F\colon C \to D${{< /katex >}} between categories {{< katex >}}$C${{< /katex >}} and {{< katex >}}$D${{< /katex >}} is an *equivalence of categories*
> if and only if it is *fully faithful* and *essentially surjective.*

Here the functor {{< katex >}}$F${{< /katex >}} is *full* if for all objects {{< katex >}}$c${{< /katex >}} and {{< katex >}}$c'${{< /katex >}} in {{< katex >}}$C${{< /katex >}}, the function
{{< katex >}}$F\colon C(c,c') \to D(Fc,Fc')${{< /katex >}} is surjective, and *faithful* if it is injective.
So {{< katex >}}$F${{< /katex >}} is *fully faithful* if it induces a bijection from the set of arrows betwwen any two objects in {{< katex >}}$C${{< /katex >}}
to their images in {{< katex >}}$D${{< /katex >}}.

The functor {{< katex >}}$F${{< /katex >}} is *essentially surjective* if every object {{< katex >}}$d \in D${{< /katex >}} is isomorphic to {{< katex >}}$Fc${{< /katex >}} for some
{{< katex >}}$c \in C${{< /katex >}}.

Finally an *equivalence of categories* is a functor {{< katex >}}$F\colon C \to D${{< /katex >}} such that there exists an "inverse"
functor {{< katex >}}$G \colon D \to C${{< /katex >}} and natural isomorphisms between the two double compositions and the
identity functors of {{< katex >}}$C${{< /katex >}} and {{< katex >}}$D${{< /katex >}}, respectively.

The proof that an equivalence of categories has the above properties is fairly simple: in an alternate universe,
this blog post would give it, and show that the converse requires the axiom of choice.
Let me just content myself with pointing out that the use of the axiom of choice is to pick
a {{< katex >}}$c${{< /katex >}} such that {{< katex >}}$Fc${{< /katex >}} is isomorphic to {{< katex >}}$d${{< /katex >}} for all {{< katex >}}$d \in D${{< /katex >}}.
In fact, it turns out that the theorem is *equivalent* to the axiom of choice,
if you make the appropriate definitions of the categories involved.
(e.g. {{< katex >}}$D${{< /katex >}} should be an index set, and {{< katex >}}$C${{< /katex >}} a clever category based on a collection
of sets indexed by {{< katex >}}$D${{< /katex >}}.)

One can define (small) categories *internal* to a category and 
do category theory in this way. Thus one way to phrase the axiom of choice for a category is:

> **The Axiom of Choice for a Category:** A functor between categories internal to {{< katex >}}$C${{< /katex >}}
> is an equivalence if and only if it is fully faithful and essentially surjective.

It turns out that the category of smooth manifolds *also* fails this axiom,
essentially because it fails the previous one!
