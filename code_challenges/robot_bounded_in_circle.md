# Robot Bounded in Circle

## Problem Domain

On an infinite plane, a robot initially stands at (0,0) and faces north. The robot can receive on of three instructions:

- "G": go straight 1 unit;
- "L": turn 90 degrees to the left;
- "R": turn 90 degrees to the right.

The robot performs the instructions given in order, and repeats them forever.

Return true if and only if there exists a circle in the plane such that the robot never leaves the circle.

### **input**

instructions = "GGLLGG"

### **output**

True

Explanation: The robot moves from (0,0) to (0,2), turns 180 degrees, and then returns to (0,0).
When repeating these instructions, the robot remains in the circle of radius 2 centered at the origin.

### **visual**

instructions = "GGLLGG"

 i = 0,0

  "GG" = i -> ->; "LL" = i ^, <- ; "GG" = i <-, <-
  
### **algorithm**

iterate over the instructions
check if instruction equals "G", "L", or "R"
If "G", update x and y axis by adding direction x to x and direction y to y.
If "L", update direction x to go back one direction y, and set direction y to direction x.
otherwise, it's "R", which we would update direction y to go back one direction x, and set direction x to direction y.

finally, return boolean if x and y are at 0, 0, or dirX and dirY are not at 0,1.

### **code**

```Python
def isRobotBounded(instructions):
  dirX, dirY = 0, 1
  x, y = 0, 0

  for direction in instructions:
    if direction == "G":
      x, y = x + dirX, y + dirY
    elif direction = "L":
      dirX, dirY = -1*dirY, dirX

    else: 
      dirX, dirY = dirY, -1*dirX

  return (x, y) == (0,0) or (dirX, dirY) != (0,1)
```

### **testing**

Test for integers
Test for letters other than "GLR"
Test for strings

### **BigO**

Time and Space are at `O(n)` because we loop over the string, and it depends on how many indexes there are in the string. We are not holding anything in the space, just reading it, so this will be `O(n)` as well.

### **Design Choice and Why**

This is a fairly simple code to read, and for someone to jump in to look at they can pick up and know what is happening fairly quickly.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/robot-bounded-in-circle/)

-----

### 👈 [Back to Table of Contents](../toc.md)
