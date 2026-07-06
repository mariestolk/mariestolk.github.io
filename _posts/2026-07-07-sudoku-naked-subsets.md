---
layout: post
title: "Sudoku strategies: from naked singles to naked subsets"
date: 2026-07-07 00:00:00 +0200
---

# Sudoku strategies: from naked singles to naked subsets

In the [previous post]({% post_url 2026-07-06-sudoku-naked-hidden-singles %}), we looked at naked singles: cells for which only one candidate remains. A naked single is actually the simplest example of a broader family of techniques called **naked subsets**.

> A **naked subset** occurs when a group of $n$ cells within the same house collectively contains exactly $n$ distinct candidates. Those candidates must occupy those cells in some order, which means they can be removed from every other cell in that house.

Let's look at an example to get a feeling for it.

In the row below, the three highlighted cells contain the candidate sets $\{1,2\}$, $\{2,3\}$, and $\{1,3\}$. Together, these cells contain only the digits $1$, $2$, and $3$, so they form a naked triple. Note that the individual cells do not need to contain the same candidates; only their combined set of candidates matters. Those digits must occupy the three cells in some order, which means no other cell in row $r_4$ can contain $1$, $2$, or $3$.

<p align="center">
  <img
    src="{{ '/images/naked_triple_example.png' | relative_url }}"
    alt="A Sudoku example showing a naked triple in row r4."
    width="650"
  >
</p>

## Why we stop at naked quads

Larger naked subsets are valid, but they are usually described as smaller hidden subsets instead. The example below gives an intuition for why.

The first five cells contain the candidate sets $\{1,2\}$, $\{2,3\}$, $\{3,4\}$, $\{4,5\}$, and $\{1,5\}$. Together, they contain only the digits $1$, $2$, $3$, $4$, and $5$, so they form a **naked quint**.

<p align="center">
  <img
    src="{{ '/images/naked_quint_hidden_quad_example.png' | relative_url }}"
    alt="A Sudoku row containing a naked quint and its complementary hidden quad."
    width="650"
  >
</p>

Those five digits must occupy the first five cells in some order, so they can be removed from the remaining four cells. The digits $6$, $7$, $8$, and $9$ are restricted to those four cells and therefore form a hidden quad. If those cells already contain no other candidates, they also form a naked quad. Otherwise, removing the extra candidates reveals the complementary naked quad.

This relationship can be generalized. 

Suppose a house contains $m$ unsolved cells, of which $n$ form a naked subset. Those $n$ cells collectively contain exactly $n$ candidates, so those digits must occupy those cells. They can therefore be removed from the remaining $m-n$ cells.

The remaining digits are then restricted to those remaining $m-n$ cells, forming a hidden subset of size $m-n$.

In a house with nine unsolved cells:

- a naked quint corresponds to a hidden quad;
- a naked sextuple corresponds to a hidden triple;
- a naked septuple corresponds to a hidden pair;
- a naked octuple corresponds to a hidden single.

Larger naked subsets therefore introduce no new type of deduction. They can always be described as smaller hidden subsets, which is why naked subsets are usually discussed only up to quads.