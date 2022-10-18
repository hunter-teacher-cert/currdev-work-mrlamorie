## 05_assignments.md
#### William LaMorie
#### Github username: mrlamorie

---
### Assigment #1 - <br>
#### Type: Group Work <br>
_Purpose:_ Students develop their understanding of data types, itteration, and arrays.<br>
_Sequence:_ First step of project following student discussion and project launch <br>
_Name:_ Basic Map Construction

_Student instructions:_<br>
The first step of the assigment is to develop a map. Our map will be a 30 x 30 grid printed out to the console. The specifications are as follow:
- The map should be made with a function called `makeMap()`
- The map should be a 2d list, with the first level of array being the y coordinates and the second level being the x coordinates - 
From our last activity can you identify why we are dooing the coordinates like this rather than as an X and then Y method?
Each item in the 2d list should be a dictionary. That dicationary should at this time have the following information right now:
`{name: "."}`
The final input should have the general format of below:<br>
```
. . . . .
. . . . .
. . . . .
. . . . .
. . . . .
````
Next, generalize the function to be able to be used with any size grid. This should have x as the first param and y as the second. Include default values of 30 for each.

For an extension activity you can add a border, this boarder will require you to use some math, but you can style it any way you want. An example border might be:<br>
```
+-------+
| . . . |
+-------+
```

---
### Assigment #2 - <br>
#### Type: Homework/Indpendent work <br>
_Purpose:_ Students reinforce their understanding of random number generation, also, students must figure out a system of tracking what cooridnates have already been used by the RNG gods.<br>
_Sequence:_ Follows students making a map as a group project. Students may do this in many ways, but will exampled by generating a 2d list of each of the coordinates and pulling off a random location from there to a new list
_Name:_ Coordinate picker

_Student instructions:_ <br>
This function should return a list of coordinates on a map of the size specs given to it. 
The function should have the name `coordPicker(n, x, y)` where n is the number of coordinates to be returned, x is the width of the map and y is the height .
The function should return a list of coordinates in the form of dictionaries with x and y keys as such: `({x: 5, y: 12}, {x: 15, y: 42} ......` 

You can do this any way you want, but it should generate unique with no replacements. There are a number of ways you could do this, but one suggestion is as follows:<br>
Make a list of all the possable items, generate a random number from the length of the list. Remove that numbered item, draw a random number from the new length of the list.