---
layout: post
title: "Closure and interior of a set"
date: "2016-09-04 19:40:20 -0500"
categories:
  - classnotes
  - topology
tags:
  - topology
lang: en
---
Topology is one area of mathematics many people find mystic-sounding. Of course, I thought the same when I first heard about it. But after taking Real Analysis, it's just a nice and natural generalization of what you've seen before. Let's start with some definitions.

A **topology** $$\tau$$ on $$X$$ is a collection of sets in $$2^X$$ that satisfies the following properties:

1. \$$\varnothing, X \in \tau$$
2. \$$(A_\alpha)_{\alpha\in L} \in \tau \Rightarrow \bigcup_{\alpha\in L} A_\alpha \in \tau$$
3. \$$ A, B \in \tau \Rightarrow A \cap B \in \tau$$

 We say that a set is **open** if it's an element of the topology, or **closed** if it's the complement of an open set. Note these terms are [not mutually exclusive](https://en.wikipedia.org/wiki/Clopen_set).

A **topological space** is a tuple $$(X, \tau)$$, where $$\tau$$ is a topology on $$X$$. It's common to say that $$X$$ is the topological space without referencing $$\tau$$ explicitly.

The **closure** of a set $$A \subset X $$, denoted $$\bar{A}$$ or $$cl(A)$$, is the smallest closed set that contains $$A$$, that is:
$$ \bigcap \{ F \subset X : F \text{ is closed and } A \subset F \} $$

Similarly, the **interior**, denoted $$\mathring{A}$$ or $$int(A)$$ is the biggest open set contained in A, or:
$$ \bigcup \{ F \subset X: F \text{ is open and } F \subset A \} $$

These definitions have some very useful equivalences, some of which are given as the definition in Analysis courses due to their geometric appeal. We'll talk about them later. First, here are some properties.

Properties
===
For all $$A, B \subset X$$, it follows that:

1. \$$A\subset \overline{A}$$
2. \$$A \text{ closed } \Rightarrow \overline{A} = A$$
3. \$$\overline{\overline{A}} = \overline{A}$$
4. \$$A \subset B \Rightarrow \overline{A} \subset \overline{B}$$
5. Given a family $$(A_\alpha) \subset X$$, we get: $$\bigcup \overline{A}_\alpha \subset \overline{\bigcup A_\alpha} $$
6. \$$\overline{A \cap B} \subset \overline{A} \cap \overline{B}$$

Let's now define special points that will characterize sets and give more geometric intuition. Let $$A \subset X$$ and take a point $$x \in X$$. We'll categorize it according to the behavior of $$A$$ or its complement with the neighborhoods of $$x$$.

It is an **accumulation or adherence point** if $$x \in U \in \tau \Rightarrow U \cap A \neq \varnothing$$.

It is a **limit point** if $$x \in U \in \tau \Rightarrow U \cap (A \setminus \{x\}) \neq \varnothing$$.

It is a **boundary point** if $$x \in U \in \tau \Rightarrow U \cap A \neq \varnothing \text{ and } U \cap (X \setminus A) \neq \varnothing$$.

It is an **interior point** if $$\exists U \subset X$$ neighborhood of $$x$$ such that $$U \subset A$$.

To define a topology, we usually just specify some special elements that will generate the rest of it. It's analogous to generating a vector space from a basis.

A **basis** of a topology is a subset $$\mathbb{B} \subset \tau$$ such that $$\forall A \in \tau \exists B_1, B_2 : A = B_1 \cup B_2$$. That is, every element of the topology can be expressed as the union of elements of the basis.

It can be checked that being the basis of a topology is equivalent to having the following properties:

1. \$$\forall x \in X, \exists B \in \mathbb{B}: x\in B$$
2. \$$\forall x\in X, x \in B_1 \cap B_2 \Rightarrow \exists B_3 \subset B_1 \cap B_2 : x \in B_3$$

**Theorem:** Let $$\mathbb{A}, \mathbb{B}$$ be two bases for topologies $$\tau_1, \tau_2$$, respectively. Then $$\tau_1 = \tau_2$$ if and only if:

1. \$$x \in A \in \mathbb{A} \Rightarrow \exists B \in \mathbb{B} : x \in B \subset A$$
2. \$$x \in B \in \mathbb{B} \Rightarrow \exists A \in \mathbb{A} : x \in A \subset B$$

The basis can be reduced even more through the use of a subbasis. A **subbasis** $$\mathcal{S}$$ for a topology $$\tau$$ is a collection of sets such that $$\mathbb{B}(\mathcal{S}) = \{ \bigcap_{i=1}^{n} S_n : S_n \in \mathcal{S} \}$$, that is, the set of all the finite intersections of sets in $$\mathcal{S}$$, is a basis for the topology $$\tau$$.

**Theorem:** $$\mathcal{S}$$ is a subbasis for a topology on $$X$$ if and only if $$\bigcup_{S\in\mathcal{S}} S = X$$.

One nice consequence of this theorem is that, for an arbitrary collection $$\mathcal{C} \subset 2^X$$, we can form the smallest topology that contains it, using the fact that $$\mathcal{C} \cup X$$ will always be a subbasis:

$$\tau(\mathcal{C}) = \tau(\mathbb{B}(\mathcal{C} \cup \{X\}))$$

Where in the last $$\tau$$ operator you're just taking all the unions.

For a point $$p \in X$$, we define a **local basis** $$\mathbb{B}_p$$ to be a collection of neighborhoods of $$p$$ such that:

$$\forall V \text{ open neighborhood of } p, \exists B \in \mathbb{B}_p : p\in B \subset V$$

In the next post we'll see some results and definitions related to continuity and limits.
