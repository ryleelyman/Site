---
title: "Category Theory Day One"
date: 2020-02-16T12:41:59-04:00
math: true
---
My office-mate asked me to give a "second lecture" in category theory
in [Eminar][eminar], the Tufts graduate student seminar. I gave a first lecture
last semester, but I thought it might be nice to have something to point people
who missed it to, in order to stick to my assignment
and begin at the Yoneda lemma. So, here is yet another rendition of the first
hour of a category theory class.

The treatment is brisk. To the interested reader,
I would highly recommend Emily Riehl's [*Category Theory in Context*][ctinc],
which is the main inspiration here and
has the advantage of being available on the author's website.
I also recommend Saunders Mac Lane's 
*Category Theory for the Working Mathematician*
and Francis Borceux's *Handbook of Categorical Algebra.*

## Categories
A *category* {{< katex >}}$C${{< /katex >}} is a collection of *objects,* say {{< katex >}}$c${{< /katex >}}, {{< katex >}}$d${{< /katex >}}, and 
*arrows* between them, say {{< katex >}}$f\colon c\to d${{< /katex >}}.
Given a pair of arrows as below

{{< katex >}}$$\begin{CD} a @>f>> b @>g>> c,\end{CD}$${{< /katex >}}

we require the existence of their *composition,* {{< katex >}}$gf\colon a\to c${{< /katex >}}.
Composition is associative, and for each object {{< katex >}}$c${{< /katex >}}, there is a
(unique) arrow {{< katex >}}$1_c\colon c\to c${{< /katex >}} which acts as an identity for composition
of arrows.

Many familiar mathematical objects assemble into categories.
To wit, there is the *category of sets,* where objects are sets
and arrows are functions of sets, and the *category of topological spaces,*
where objects are topological spaces and arrows are continuous maps.
However, the notion of a category is flexible: not all categories
have "sets with additional structure" as objects.
For instance, a *preorder* is the same data as a category
where there is at most one arrow between any two objects.
Here an arrow {{< katex >}}$c\to d${{< /katex >}} should be interpreted as saying {{< katex >}}$c\le d${{< /katex >}}$.

Note that I use the term *collection* advisedly: Russell's paradox
says that there can be no set of all sets, so the category of
sets has more than a set's worth of objects! However,
between any two sets, there is only a set's worth of distinct functions.
That is, if {{< katex >}}$a${{< /katex >}} and {{< katex >}}$b${{< /katex >}} are sets, there is a *set*

{{< katex >}}$$\operatorname{Set}(a,b) = \{f\colon a \to b\}.$${{< /katex >}}

Categories where this is the case for all objects are called *locally small.*
If additionally there is only a set's worth of arrows in the entire category
(and thus only a set's worth of objects!), the category is called *small.*

## Functors
If {{< katex >}}$C${{< /katex >}} and {{< katex >}}$D${{< /katex >}} are categories, a *functor* {{< katex >}}$F\colon C \to D${{< /katex >}}
is an assignment 

{{< katex >}}$$\begin{CD}
a @.{\mapsto} @.Fa \\ 
@VfVV @. @VVFfV \\ 
b @.{\mapsto} @.Fb.
\end{CD}$${{< /katex >}}

I.e. for each object {{< katex >}}$a${{< /katex >}} of {{< katex >}}$C${{< /katex >}}, there is an object {{< katex >}}$Fa${{< /katex >}} in {{< katex >}}$D${{< /katex >}},
and for each arrow {{< katex >}}$f\colon a\to b${{< /katex >}} in {{< katex >}}$C${{< /katex >}}, there is an arrow
{{< katex >}}$Ff\colon Fa\to Fb${{< /katex >}}. Additionally, {{< katex >}}$F${{< /katex >}} is required to satisfy

{{< katex >}}$$F1_{a} = 1_{Fa}$${{< /katex >}}

for all {{< katex >}}$a${{< /katex >}} in {{< katex >}}$C${{< /katex >}}, and {{< katex >}}$F${{< /katex >}} must
respect composition in the sense that 

{{< katex >}}$$F(gf) = FgFf.$${{< /katex >}}

Such functors are sometimes called *covariant.*

Every category {{< katex >}}$C${{< /katex >}} has an *opposite category* 
{{< katex >}}$C^{\mathrm{op}}${{< /katex >}}, which is obtained from
formally reversing the direction of all the arrows.
Thus if {{< katex >}}$C${{< /katex >}} has arrows

{{< katex >}}$$\begin{CD} a @>f>> b @>g>> c,\end{CD}$${{< /katex >}}

then {{< katex >}}$C^{\mathrm{op}}${{< /katex >}} has arrows

{{< katex >}}$$\begin{CD} a @<f^{\mathrm{op}}<< b @<g^{\mathrm{op}}<< c.\end{CD}$${{< /katex >}}

Any statement about objects and arrows in {{< katex >}}$C${{< /katex >}} has a *dual*
statement about objects and arrows in {{< katex >}}$C^{\mathrm{op}}${{< /katex >}}, which is obtained
by reversing the direction of all the arrows.
If the proof of the original statement is categorical,
dualizing the proof yields a proof of the dual statement for {{< katex >}}$C^{\mathrm{op}}${{< /katex >}}.

The definition of a functor admits dualization in {{< katex >}}$C${{< /katex >}} or in {{< katex >}}$D${{< /katex >}}.
The import is essentially the same as long as only one dualization is
performed: the result is a *contravariant functor* {{< katex >}}$G\colon C^{\mathrm{op}} \to D${{< /katex >}}:

{{< katex >}}$$\begin{CD} a @.\mapsto  @.Ga \\ @VfVV @. @AAGfA \\ b @.\mapsto @.Gb.
\end{CD}$${{< /katex >}}


Functors abound in mathematics. Many are so simple that we hardly think about
them: for instance the "forgetful" 
functor from the category of groups and homomorphisms
to sets that sends a group {{< katex >}}$G${{< /katex >}} to its set of elements,
and a group homomorphism to its action on underlying sets.

If {{< katex >}}$C${{< /katex >}} is a locally small category and {{< katex >}}$c${{< /katex >}} is an object,
there are two particularly important functors {{< katex >}}$C \to{\operatorname{Set}}${{< /katex >}}.
Write {{< katex >}}$C(c,b)${{< /katex >}} and {{< katex >}}$C(b,c)${{< /katex >}} for the set of arrows in {{< katex >}}$C${{< /katex >}}
with domain and codomain {{< katex >}}$c${{< /katex >}}, respectively.
If {{< katex >}}$f\colon b\to d${{< /katex >}} is an arrow in {{< katex >}}$C${{< /katex >}}, there are
functions 

{{< katex >}}$$f_*\colon C(c,b) \to C(c,d) \text{ and }f^*\colon C(d,c) \to C(b,c)$${{< /katex >}}

defined as {{< katex >}}$f_*(g) = fg${{< /katex >}} and {{< katex >}}$f^*(h) = hf${{< /katex >}}, respectively.
The assignments

  {{< katex >}}$$\begin{CD} b @.\mapsto  @.C(c,b) @.\qquad\qquad @.b @.\mapsto @.C(b,c) \\
    @VfVV @.\mapsto @VVf_*V @.\qquad\qquad @VfVV @.\mapsto @AAf*A \\
    d @.\mapsto  @.(c,d)  @.\qquad\qquad @.d @.\mapsto @. C(d,c)
  \end{CD}$${{< /katex >}}

define covariant and contravariant functors 
{{< katex >}}$C(c,-)\colon C \to {\operatorname{Set}}${{< /katex >}} and  
{{< katex >}}$C(-,c)\colon C^{\mathrm{op}}\to{\operatorname{Set}}${{< /katex >}}, respectively.

### Natural Transformations
Just as we have defined functors between categories,
it is  useful to consider *functor categories,*
whose elements are functors {{< katex >}}$C\to D${{< /katex >}}. To do this, we need 
a  notion of a morphism between functors. It turns out
that the right notion is a *natural transformation.*
If {{< katex >}}$F,G\colon C \to D${{< /katex >}} are functors, a natural transformation
{{< katex >}}$\eta\colon F\Rightarrow G${{< /katex >}} is a collection of maps
{{< katex >}}$\eta_c\colon Fc \to Gc${{< /katex >}}, one for each object {{< katex >}}$c${{< /katex >}} of {{< katex >}}$C${{< /katex >}}
such that for every arrow {{< katex >}}$f\colon c \to d${{< /katex >}}, the following
diagram commutes

{{< katex >}}$$\begin{CD}
  Fc @>\eta_c>> Gc \\
  @VFfVV @VVGfV \\
  Fd @>\eta_d>> Gd.
\end{CD}$${{< /katex >}}

Any directed path in a diagram of objects and arrows within
a category like the above yields an arrow from the initial 
"vertex" of the path to the terminal one by reading off the
labelled arrows. A diagram *commutes* if any two directed
paths with the same endpoints yield equal arrows.
Thus, to say that the above diagram commutes asserts the
equality 

{{< katex >}}$$Gf\eta_c = \eta_d Ff.$${{< /katex >}}

The standard example of a natural transformation is the following.
Let {{< katex >}}$k${{< /katex >}} be a field, and consider the category of {{< katex >}}$k${{< /katex >}}-vector spaces
and linear transformations. There is a contravariant functor
that sends a vector space {{< katex >}}$V${{< /katex >}} to its *dual* {{< katex >}}$V^*${{< /katex >}}, namely the vector
space of linear transformations {{< katex >}}$V\to k${{< /katex >}}.
A linear map {{< katex >}}$f\colon V \to W${{< /katex >}} is sent to a map {{< katex >}}$f^*\colon W^*\to V^*${{< /katex >}}
which is defined as follows.
If {{< katex >}}$\lambda\colon W \to k${{< /katex >}} is an element of {{< katex >}}$W^*${{< /katex >}},
{{< katex >}}$f^*(\lambda)${{< /katex >}} is the linear  map 

{{< katex >}}$$\lambda f\colon V\to k.$${{< /katex >}}

Thus there is a *covariant* functor sending a vector space {{< katex >}}$V${{< /katex >}}
to its "double dual" {{< katex >}}$V^{**}=(V^*)^*${{< /katex >}}.
There is a natural transformation {{< katex >}}$ev${{< /katex >}} from the identity functor
to the double dual functor.
At a given vector space {{< katex >}}$V${{< /katex >}}, the map {{< katex >}}$ev_V${{< /katex >}} sends a vector {{< katex >}}$v${{< /katex >}}
to the linear map {{< katex >}}$V^*\to k${{< /katex >}} defined by "evaluation at {{< katex >}}$v${{< /katex >}},"
namely

{{< katex >}}$$\lambda \mapsto \lambda(v),\quad  \lambda \in V^*.$${{< /katex >}}

Naturality of {{< katex >}}$ev${{< /katex >}} asserts that for {{< katex >}}$f\colon V \to W${{< /katex >}}
a linear map, the following diagram commutes

{{< katex >}}$$\begin{CD}
  V @>ev_V>> V^{**} \\
  @VfVV @VVf^{**}V \\
  W @>ev_W>> W^{**}.
\end{CD}$${{< /katex >}}

To show this, consider a vector {{< katex >}}$v \in V${{< /katex >}}.
The element {{< katex >}}$f^{**}(ev_V(v)) \in W^{**}${{< /katex >}} is
the linear map 

{{< katex >}}$$ev_V(v)\circ f^*\colon W^*\to k,${{< /katex >}}

so its action on {{< katex >}}$\lambda \in W*${{< /katex >}} is 

{{< katex >}}$$ev_V(v)(f^*(\lambda)) = ev_V(v)(\lambda f) = 
\lambda (f(v)) = ev_W(f(v))(\lambda),$${{< /katex >}}

demonstrating naturality.

The map {{< katex >}}$ev_V${{< /katex >}} is an isomorphism when {{< katex >}}$V${{< /katex >}} is finite dimensional.
Thus we say that when restricted to the *subcategory*
of finite dimensional vector spaces, {{< katex >}}$ev${{< /katex >}} is a *natural isomorphism.*

### The Yoneda Lemma
Perhaps the fundamental result in category theory
is the following:

> **Theorem.** (The Yoneda Lemma)      
>  Let {{< katex >}}$C${{< /katex >}} be a locally small category and
>  {{< katex >}}$F\colon C \to {\operatorname{Set}}${{< /katex >}} a functor.
>  For each object {{< katex >}}$c${{< /katex >}} of {{< katex >}}$C${{< /katex >}}, there is a bijection

{{< katex >}}$$\{\alpha\colon C(c,-)\Rightarrow F\} \longleftrightarrow \{x \in Fc\}$${{< /katex >}}

>  implemented by sending a natural transformation
>  {{< katex >}}$\alpha${{< /katex >}} to the element {{< katex >}}$\alpha_c(1_c)${{< /katex >}}.
>  This bijection is natural in {{< katex >}}$F${{< /katex >}} and {{< katex >}}$c${{< /katex >}}.

The proof is straightforward, once one figures out what needs proving.
The utility of the Yoneda lemma is likely 
far from obvious when one first meets it,
but it turns out to be a major tool in category theory.

[eminar]: http://www.danielkeliher.com/EminarCurrent.html
[ctinc]: http://www.math.jhu.edu/~eriehl/context.pdf


