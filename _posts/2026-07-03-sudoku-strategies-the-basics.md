# The basics of Sudoku

## Why am I describing Sudoku-solving strategies?

I am building a [Sudoku solver](https://github.com/mariestolk/sudoku-solver/tree/main) to get a better grasp of one of my favorite types of puzzles. Alongside this solver, I want to document the different ways to think about Sudoku and the strategies used to reduce candidate sets—a term I will explain shortly.

## What is a Sudoku?

I am going to assume that you are at least somewhat familiar with Sudoku. Even so, I will use this post to take a closer look at how the puzzle works.

A Sudoku is a number-placement puzzle. It consists of a 9 × 9 grid divided into nine 3 × 3 boxes. To complete a classic Sudoku, you must assign a digit from `1` to `9` to every cell.

There is one basic rule:

> _Each digit must occur exactly once in every row, column, and box._

That's all you need to get started. 

## Cells, givens, and candidates

Each position in the Sudoku grid is called a **cell**. Some cells already contain a digit when the puzzle begins. These starting digits are called **givens** or **clues** and cannot be changed.

For every empty cell, we can determine which digits from `1` to `9` are still possible without breaking the basic rule. These possible digits form the cell's **candidate set**.

For example, if a cell's row already contains `1`, `4`, and `7`, those digits cannot be candidates for that cell. We can apply the same reasoning to its column and box. Solving strategies work by reducing these candidate sets until only one valid digit remains, or until the remaining candidates reveal a broader pattern.

## The houses of Sudoku

Now that we have established the basic rule, we can look more closely at the structure of a Sudoku. There are three types of units to which this rule applies: rows, columns, and boxes.

<p align="center">
  <img
    src="{{ '/images/sudoku_houses.png' | relative_url }}"
    alt="Sudoku grid showing a row, column, and box"
    width="650"
  >
</p>

Rows, columns, and boxes are collectively referred to as **houses**. Each individual row, column, or box is one house. This allows us to generalize across the three types: instead of describing the same reasoning separately for rows, columns, and boxes, we can describe it once for houses.

With these concepts in place, we can begin exploring the strategies used to eliminate candidates and solve a Sudoku. More posts will follow soon.