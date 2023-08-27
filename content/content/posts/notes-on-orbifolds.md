---
title: "Notes on Orbifolds"
date: 2021-03-14T14:11:40-04:00
math: false
---
The purpose of this post is to share some [talk notes][notes] I made on orbifolds
and graphs of groups as étale groupoids.

The talk comes out of joint work in progress with [Tyrone Ghaswala][Ty].
It starts with us realizing that some representations of the braid group
into the automorphism group of a free group that each of us knew how to obtain by different methods
were really the same representation.
We thought that there ought to be some way to reconcile these two representations topologically
by working with the mapping class group of certain 2-dimensional orbifolds.

From there things got complicated: we discovered that there is a good amount of contention about what
a map of an orbifold even is.
The consensus, outside of low-dimensional topology, seems to be to work with étale groupoids,
rather than deal with orbifolds in terms of local charts.
This has the advantage of making ineffective orbifolds easier.
To wit, see the complications in the paper [Atlases for Ineffective Orbifolds][atlases] by Pronk, Scull and Tommasini.

Within low-dimensional topology, it's usually thought that the mapping class group
of a 2-dimensional orbifold whose underlying space is a finite-type surface 
and whose singular set is a finite collection of points
is the subgroup of the mapping class group of the surface where the singular set is marked
preserving the singular points of a given order.
One goal of our project is to reconcile these two points of view.

[notes]: /pdfs/orbifoldnotes.pdf
[Ty]: http://cirget.math.uqam.ca/~tyghaswala/
[atlases]: https://arxiv.org/pdf/1606.04439.pdf
