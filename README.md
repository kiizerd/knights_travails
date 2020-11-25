# Knights Travails
### Solution for [this project](https://www.theodinproject.com/lessons/knights-travails) at [The Odin Project](https://www.theodinproject.com)

A knight in chess can travel from any square to any other square given enough moves.

The problem to solve is the shortest path between any two squares.

My solution is an algorithm involving a few different classes and methods.
I may have overdone the documentation for this but I was stuck on this one for awhile so maybe this could help somebody else in a similar position. :)

This can be broken down into a few simple steps and probably more simply than I have done here

1. Build a game board that has an array of every possible position, with a method to check if a move is possible
2. Build a knight that will give an array of possible moves from a given position
3. Build a Node class to represent a step in the path, with variables to hold its position in the board, in relation to the path, and possible moves from the node
4. Build a Path class that takes a starting node and a destination node
5. Starting at the root node
  5-A. Check every move from current node and make it a child of current
  5-B. Check every child for destination, add child to queue if not found
  5-C. Set current to first in queue
  5-D. Repeat A-C until queue is empty or destination is found
6. Trace path from end to finish using node parents
7. Return path

## **Classes**
### - Board
  Contains a grid class variable, an array of 64 other arrays, each containing coordinates in an 8x8 grid.
  
  [1,1], [1,2], [1,3], [1,4], [1,5], [1,6], [1,7], [1,8],
  [2,1], [2,2], [2,3], [2,4], [2,5], [2,6], [2,7], [2,8],
  [3,1], [3,2], [3,3], [3,4], [3,5], [3,6], [3,7], [3,8],
  [4,1], [4,2], [4,3], [4,4], [4,5], [4,6], [4,7], [4,8],
  [5,1], [5,2], [5,3], [5,4], [5,5], [5,6], [5,7], [5,8],
  [6,1], [6,2], [6,3], [6,4], [6,5], [6,6], [6,7], [6,8],
  [7,1], [7,2], [7,3], [7,4], [7,5], [7,6], [7,7], [7,8],
  [8,1], [8,2], [8,3], [8,4], [8,5], [8,6], [8,7], [8,8]
  
#### *Methods*
  - Board#allowed? (move)
    Takes a coordinate pair and returns false if it's outside the bounds of the board
    
---    
### - Knight
  Has a readable position value and a get_moves method

#### *Methods*
  - Knight#get_moves (pos=@pos)
    Returns an array of all possible moves from given position, defaults to @pos
    
--- 
### - Node
   Has a readable position and accessable parent and children instance variables
   
--- 
### - Path
  Tackles the meat of the problem
  Initializes with a start and finish position and the piece object that it will be making a path for.
  - @piece -Object that is being pathed
  - @start -Starting node
  - @finish -Destination node
  - @queue -Queue of nodes to check

#### *Methods*
  - Path#make_path (start, finish)
    1. Empty queue, found = false, reset piece position to start location
    2. Set current to start and pushes current to queue
    3. get_children of current
    4. check_children of current
    5. set current to the first element of queue
    6. repeat 3-5 until found

  - Path#get_children (node)
    1. Empty children array
    2. Gets all possible moves from position
    3. New node from each move with node as parent
    4. Set nodes children to children array 

  - Path#check_children (node)
    1. Checks every child of current node for destination
    2. Call found_finish if found
    3. Pushes child to @queue

  - Path#found_finish (node, parent)
    1. Called when the destination node is found 
    2. Sets @finish to found node, and found to true
    3. Calls get_steps

  - Path#get_steps
    Returns the path from start to finish as a string with arrows
--- 

