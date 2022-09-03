## 00_Standards.md
#### William LaMorie
#### Github username: mrlamorie
---

### Assignment:
>Pick 2 specific [NY CS standards](http://www.nysed.gov/common/nysed/files/programs/curriculum-instruction/computer-science-digital-fluency-standards-k-12.pdf) and describe a lesson/task/assignment that addresses your selected standards, explain how.
>You can use the same lesson/task/assignment for both, or different ones.

---

### Standards addressed:
>**9-12.CT.1**: Create a simple digital model that makes predictions of outcomes.

>**9-12.CT.4**: Implement a program using a combination of student-defined and
third-party functions to organize the computation.

---

### Task Details:

#### Student Audience: 
High school students in 11th & 12th grades who have self selected into a computer science program with the possibility of college credit. This activity will take place fairly early in the school year, while students are still working on mastery of core programming motifs.

#### Activity: 
Conway's Game of life.

Students will complete an implementation of Conway's game of life, as an activity to build on their use of complex conditionals and nested looping. Students will be provided with code for some parts of the program, and will have either comment skeletons or docstrings provided to help students organize their code and build desired deliverables.

Students should be comfortable with simple looping, and using conditionals, but the level of complexity may be new to them. Students should also be familiar with 2d array like data structures, and coordinate maps.

#### Flow:
Students will look at an example of a game of life, and be allowed some time with the [program](https://playgameoflife.com/), and directed in their experimentation if need be. Once they have a basic understanding of what is happening, move on to the research and discussion.

Students will then be directed to look up emergence in pairs, and come up with a working definition of what emergence is, and at least 2 examples per group of fields in which emergence is a key topic. Groups will then share out and create a list of disciplines in which emergence matters, discussion will be wrapped up by students discussing why this might be an important topic to link to the game of life.

The programming activity will then be introduced, along with the provided code and the code scaffold. Students will work in pairs on the assignment, and should use the provided code to test their code. 

Example code scaffold & provided code (python) (testing code not provided to sake of space):
```python
import os
import time

""" 
The Rules of Life:

Survivals:
* A living cell with 2 or 3 living neighbours will survive for the next generation.

Deaths:
* Each cell with >3 neighbours will die from overpopulation.
* Every cell with <2 neighbours will die from isolation.

Births:
* Each dead cell adjacent to exactly 3 living neighbours is a birth cell. It will come alive next generation.

"""

## --------------- PROVIDED CODE --------------------- ##
def newBoard(rows, cols, sym='.'):#tested & works
  """a function to make a new board filled with symbol sym of row x col size """
  # need to use the more verbose method below because of shallow list in python
  board = [[sym for i in range(cols)] for j in range(rows)]
  return board

def setCell(board, cord, sym):
  """A function that takes in 2d array "board" and sets the string value of a
  cell at board[coordinates] to symbol sym. """

  board[cord[0]][cord[1]] = sym

def ageCell(board, cord, sym="X", alt= "."):
  """A function that checks what the cel value will update to based on the
  rules outlined for cgol, returns sym if alive, alt if not"""
    
  friends = countNeighbors(board, cord, sym) ## how many buddies
  living = board[cord[0]][cord[1]] == sym
  
  if living and friends == 2:
    return sym
  elif friends == 3:
    return sym
  else:
    return alt
    
def ageBoard(board, sym="X", alt="."):
  """A function that creates a new board based on the rules of gol and the 
  positions of the previous board"""
  nextGen =  newBoard(len(board), len(board[0]))

  for i in range(len(board)):
    for j in range(len(board[0])):
      nextGen[i][j] = ageCell(board, (i, j), sym, alt)

  return nextGen
    
  

## --------------- YOUR CODE --------------------- ##

def printBoard(board):
  """A function to print a 2d array (board) as a grid"""
  #DO -
  # Make a nested loop to go though the board and print each item.
  # Use the print statements below, make sure to indent them correctly.
  # This should be working before you move on.
  print(c, end=' ')  # NOTE - the end=' ' keeps it from adding a new line!
  print()


def validNeighbors(board, cord):
  """A function that takes a location of cord on a board, uses the board's
  size at row 0 (assumes a non jagged board) to return a list of touples of 
  neighbors that are valdily within the correct area of the board."""
  
  # Task:
  # check all the squares around the coordinate (cord) to see which ones are on
  # the board. Return a list of these items.

  #DO -
  # Make sure you know the board boundries
  # Make an empty list to return
  
  # make a for loop ranging from -1 to 1 (i)
    # make a second for loop ranging from -1 to 1 (j)
  
      # make a test coordinate which is the starting coordinate[0] + i
      # and the starting coordinate[1] + j

      # check if the test coordinate is within bounds
        # check to make sure the test coordinate is not the original coordinate
          # add it to the list if all conditions are met
  

  # DO -Return a list or a tuple of tuples or list of coordinates
  return [(0,0),(1,1)]

def countNeighbors(board, cord, sym="X"):
  """A function to count the number of living neighbors with the valid neighbors
  of a given coord, a living neigbor as defined by symol sym"""

  # DO  - use your validNeighbors here to make a list of test coordinates
  # DO  - set a living counter to 0

  # DO -
  # for each coordinate from your validNeighbors, check to see if it matches the
  # symbol pased to this function in the param sym, if it does, add 1 to your
  # living counter.

  # DO - return your living counter.
  return 0


```
---

### How this meets the standards:

1. **9-12.CT.1**: Create a simple digital model that makes predictions of outcomes.

Emergence is a common phenomena across many disciplines, and explains a great amount of our universe. The game of life is a simple model of how basic rules can cause complex and diverse behavior. By Constructing an implementation of GoL students have made a model that can be used to make predictions of outcome patterns based on an initial starting state that is far less complex. 

2. **9-12.CT.4**: Implement a program using a combination of student-defined and
third-party functions to organize the computation.

The structure of the activity and the provided code allow students to work on their own functions while working within a structure defined for them. I don't want to under explain this, but the reality is that this standard is pretty implicitly met by the lesson.