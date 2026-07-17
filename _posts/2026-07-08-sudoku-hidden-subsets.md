---
layout: post
title: "Sudoku strategies: from hidden singles to hidden subsets"
date: 2026-07-08 00:00:00 +0200
---

# Sudoku strategies: from hidden singles to hidden subsets

In the [previous post]({% post_url 2026-07-06-sudoku-naked-hidden-singles %}), we looked at hidden singles: a candidate that appears in only one cell within a house, making that cell its only possible location. Just as a naked single is the simplest form of a [naked subset]({% post_url 2026-07-07-sudoku-naked-subsets %}), a hidden single is the simplest form of a broader family of techniques called hidden subsets.

> A **hidden subset** occurs when a group of $n$ candidates within the same house appears only in the same $n$ cells. Those candidates must occupy those cells in some order, which means all other candidates can be removed from those cells.

Let's look at an example to get a feeling for it.

In the highlighted block below, the three highlighted pink cells contain the candidate sets $\{2,4\}$, $\{2,6\}$, and $\{4,6\}$. Together, these cells contain only the digits $2$, $4$, and $6$, so they form a hidden triple. The cells do not each need to contain the same candidates; what matters is that, taken together, they contain exactly these three digits. Since $2$, $4$, and $6$ must occupy those three cells in some order, any other candidates in those cells can be eliminated.

<p align="center">
  <img
    src="{{ '/images/hidden_triple_example.png' | relative_url }}"
    alt="A Sudoku example showing a hidden triple in block $r_3c_0$ to $r_5c_2$."
    width="650"
  >
</p>
