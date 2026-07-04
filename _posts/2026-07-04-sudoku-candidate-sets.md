# Candidate sets in Sudoku

## What is a candidate set?

In the [previous post]({% post_url 2026-07-03-sudoku-strategies-the-basics %}), we established the one basic rule of Sudoku:

> _Each digit must occur exactly once in every row, column, and box._

Candidate sets follow directly from this rule. For every empty cell, we can ask which digits can still be placed there without violating it.

The set of all digits that could still be placed in a cell is called its **candidate set**.

We can determine a cell's initial candidate set by starting with all digits from `1` to `9` and removing the digits that already appear in its row, column, or box:

```text
initial candidate set 
= all digits from 1 to 9
- digits already in the row
- digits already in the column
- digits already in the box
```

The image below shows an example candidate set for the highlighted cell.

<p align="center">
  <img
    src="{{ '/images/sudoku_candidate_set.png' | relative_url }}"
    alt="Sudoku row with one highlighted cell whose candidate set is 2, 5, and 8"
    width="650"
  >
</p>

For this example, only the row is highlighted. The digits `1`, `3`, `4`, `6`, `7`, and `9` already appear in the row, so they cannot be candidates for the highlighted cell. The remaining digits are `2`, `5`, and `8`.

This initial candidate set is only a starting point. As we apply Sudoku-solving strategies, we may be able to eliminate additional candidates.

## Why are candidate sets useful?

Candidate sets make the remaining possibilities explicit. Instead of considering every digit for every empty cell, we only need to consider digits that are still valid.

Most Sudoku-solving strategies work by reducing candidate sets. Sometimes this leaves a cell with only one candidate, which means its value is determined. In other cases, patterns across several candidate sets reveal where a digit must or cannot be placed.

Candidate sets are therefore a central tool in Sudoku solving and one of the main data structures used by a Sudoku solver.