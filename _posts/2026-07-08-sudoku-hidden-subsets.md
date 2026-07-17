---
layout: post
title: "Sudoku strategies: from hidden singles to hidden subsets"
date: 2026-07-08 00:00:00 +0200
---

# Sudoku strategies: from hidden singles to hidden subsets

In the [previous post]({% post_url 2026-07-06-sudoku-naked-hidden-singles %}), we looked at hidden singles: a candidate that appears in only one cell within a house, making that cell its only possible location. Just as a naked single is the simplest form of a [naked subset]({% post_url 2026-07-07-sudoku-naked-subsets %}), a hidden single is the simplest form of a broader family of techniques called hidden subsets.

> A **hidden subset** occurs when a group of $n$ candidates within the same house appears only in the same $n$ cells. Those candidates must occupy those cells in some order, which means all other candidates can be removed from those cells.

Let's look at an example to get a feeling for it.

In the highlighted block below, the digits $2$, $4$, and $6$ appear only in the highlighted pink cells. Together, these digits must therefore occupy those three cells in some order, forming a hidden triple. The cells may also contain other candidates, but those candidates can be removed because the cells are reserved for $2$, $4$, and $6$.

<p align="center">
  <img
    src="{{ '/images/hidden_triple_example.png' | relative_url }}"
    alt="A Sudoku example showing a hidden triple in block $r_3c_0$ to $r_5c_2$."
    width="650"
  >
</p>
