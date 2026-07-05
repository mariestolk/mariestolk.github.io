---
layout: post
title: "Eliminating candidates in Sudoku"
date: 2026-07-05 00:00:00 +0200
---

# Eliminating candidates in Sudoku

A [candidate set]({% post_url 2026-07-04-sudoku-candidate-sets %}) contains all digits that can currently be placed in a cell without violating the rules of Sudoku. As the puzzle is solved, these sets can be reduced by eliminating candidates that are no longer possible.

When starting a Sudoku, the initial candidate set for a cell can be determined by eliminating all digits that already occur in the same row, column, or box.

For example, consider cell $r_4c_2$ in the below image. Its initial candidate set contains all digits from `1` to `9` that do not already appear in row `r4`, column `c2`, or the box containing $r_4c_2$.

<p align="center">
  <img
    src="{{ '/images/sudoku_candidate_progression.png' | relative_url }}"
    alt="Sudoku where the initial candidate set of cell $r_4c_2$ is determined."
    width="650"
  >
</p>

Let's check out the different houses to understand how we got to this conclusion. We start out with candidate set $C = \{1, 2, 3, 4, 5, 6, 7, 8, 9\}$. Then:
1. _Box reduction_: Checking out the box containing cell $r_4c_2$, we see that both `1` and `9` are already present in this house. These can therefore be removed from $C$, leading to $C = \{2, 3, 4, 5, 6, 7, 8\}$.
2. _Row reduction_: Checking out row $r4$, we see that `1` (again), `2` and `7` are already present in this house. These can therefore be removed from $C$, leading to $C = \{3, 4, 5, 6, 8\}$.
3. _Column reduction_: Checking out column $c2$, we see that `4` (again), `5` and `8` are already present in this house. These can therefore be removed from $C$, leading to $C = \{3, 6\}$.

Thus, we are left with the candidate set presented on the right. This is our initial candidate set. 