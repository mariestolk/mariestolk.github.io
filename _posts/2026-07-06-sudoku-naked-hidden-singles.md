---
layout: post
title: "Sudoku strategies: Naked singles and hidden singles in Sudoku"
date: 2026-07-06 00:00:00 +0200
---

# Naked singles and hidden singles in Sudoku

Before we get started: yes, I also wonder why the term _naked_ was chosen instead of _exposed_. I do not know who coined it, but you are not alone if it makes you picture a digit dropping its towel after stepping out of the shower.

Now, onto what naked and hidden singles actually are.

## Naked singles 

A naked single occurs when a cell has only one candidate left. Since every other digit has already been ruled out, that remaining candidate must be the value of the cell.

A simple example is the highlighted cell $r_4c_4$ below. To determine its value, we look at the three houses it belongs to: its row, its column, and its box.

- In row $r_4$, the digits $1$, $2$, and $3$ are already present.
- In column $c_4$, the digits $4$, $5$, and $6$ are already present.
- In its box, the digits $7$ and $8$ are already present.

That rules out every digit except $9$, so the candidate set for $r_4c_4$ is simply $\{9\}$. Since only one candidate remains, $r_4c_4 = 9$. That is a naked single.

<p align="center">
  <img
    src="{{ '/images/naked_single_example.png' | relative_url }}"
    alt="A Sudoku example in which the highlighted cell $r_4c_4$ becomes a naked single."
    width="650"
  >
</p>

## Hidden singles

A hidden single occurs when a digit can only go in one cell within a row, column, or box. The cell itself may still have several candidates, but only one of those candidates is unique within that house.

The highlighted cell $r_4c_4$ below shows a hidden single. In this case, the cell is not forced because it has only one candidate left. Its candidate set is $\{4, 7, 9\}$, so it is not a naked single.

However, if we look across the whole row $r_4$, the digit $7$ can only go in one place: $r_4c_4$. Every other cell in that row is blocked from containing $7$ by the surrounding columns and boxes.

So even though the cell still has multiple candidates, the digit $7$ is unique within the row. That means $r_4c_4 = 7$. That is a hidden single.

<p align="center">
  <img
    src="{{ '/images/hidden_single_example.png' | relative_url }}"
    alt="A Sudoku example in which the highlighted cell r_4c_4 contains a hidden single 7."
    width="650"
  >
</p>

## Cell-centred versus house-centred

The cell value is forced in both cases, but the difference lies in where the information needed to determine it is found.

- A naked single is **cell-centred**: the cell itself has only one candidate remaining.
A hidden single is **house-centred**: the cell may still have several candidates, but one of them appears nowhere else in the relevant row, column, or box.

In other words, naked singles are found by inspecting one cell, while hidden singles are found by comparing multiple cells within a house.