---
layout: post
title: "Closure and interior of a set"
date: "2016-09-04 19:40:20 -0500"
categories:
  - class notes
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

Similarly, the **interior**, denoted $$A^o$$ or $$int(A)$$ is the biggest open set contained in A, or:
$$ \bigcup \{ F \subset X: F \text{ is open and } F \subset A \} $$

These definitions have some very useful equivalences, some of which are given as the definition in Analysis courses due to their geometric appeal.

Properties
===
For all $$A, B \subset X$$, it follows that:

1. \$$A\subset \overline{A}$$
2. \$$A \text{ closed } \Rightarrow \overline{A} = A$$
3. \$$\overline{\overline{A}} = \overline{A}$$
4. \$$A \subset B \Rightarrow \overline{A} \subset \overline{B}$$
5. Given a family $$(A_\alpha) \subset X$$, we get: $$\bigcup \overline{A}_\alpha \subset \overline{\bigcup A_\alpha} $$
6. \$$\overline{A \cap B} \subset \overline{A} \cap \overline{B}$$

Alternative closure definition
===
$$\overline{A} = \{ x\in X : x \in U \in \tau \Rightarrow U \cup A \neq \varnothing \}$$
