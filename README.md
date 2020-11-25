# Knights Travails
## Solution for [this project](https://www.theodinproject.com/lessons/knights-travails)
## at [The Odin Project](https://www.theodinproject.com)

A knight in chess can travel from any square to any other square given enough moves.

The problem to solve is the shortest path between any two squares.

My solution is an algorithm involving a few different classes and methods.

### **Classes**
-Board
  Contains a grid class variable, an array of 64 other arrays, each containing coordinates in an 8x8 grid.
  [1, 1], [1, 2], [1, 3], [1, 4], [1, 5], [1, 6], [1, 7], [1, 8],

  [2, 1], [2, 2], [2, 3], [2, 4], [2, 5], [2, 6], [2, 7], [2, 8],

  [3, 1], [3, 2], [3, 3], [3, 4], [3, 5], [3, 6], [3, 7], [3, 8],

  [4, 1], [4, 2], [4, 3], [4, 4], [4, 5], [4, 6], [4, 7], [4, 8],

  [5, 1], [5, 2], [5, 3], [5, 4], [5, 5], [5, 6], [5, 7], [5, 8],

  [6, 1], [6, 2], [6, 3], [6, 4], [6, 5], [6, 6], [6, 7], [6, 8],

  [7, 1], [7, 2], [7, 3], [7, 4], [7, 5], [7, 6], [7, 7], [7, 8],

  [8, 1], [8, 2], [8, 3], [8, 4], [8, 5], [8, 6], [8, 7], [8, 8]
#### *Methods*
  -Board#allowed?(move)
    Takes a coordinate pair and returns false if it's outside the bounds of the board
-Knight
#### *Methods*
-Node
#### *Methods*
-Path
#### *Methods*


