# The basics of sudoku

## Why am I describing sudoku-solving strategies?
I am building a Sudoku solver to get a better grasp of one of my favorite types of puzzles. Alongside this [solver](https://github.com/mariestolk/sudoku-solver/tree/main), I want to document the different ways to think about Sudokus and the different strategies used to reduce candidate sets—a term I will explain shortly.

## What is a sudoku?
Perhaps I am wrong, but I am going to assume that you are at least somewhat familiar with Sudoku. Even so, I will use this post to take a closer look at how the puzzle works.

A Sudoku is a number-placement puzzle. It consists of a 9 × 9 grid divided into nine 3 × 3 boxes. To complete a classic Sudoku, you must assign a digit from `1` to `9` to every cell.

There is one basic rule:

> _Each digit must occur exactly once in every row, column, and box._

That's all you need to get started.

## The houses of sudoku
Now that we have the basics set up, let's move on to a first observation about the structure. There are three distinct groups upon which our one rule applies. 

<p align="center">
  <img
    src="{{ '/images/sudoku_houses.png' | relative_url }}"
    alt="Sudoku grid showing a row, column, and box"
    width="650"
  >
</p>

A row, column, or box is collectively referred to as a **house**. Important to note is that we can thus generalize from row/column/box, a specific instance, to a 'house'.