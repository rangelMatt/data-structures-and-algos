# Find Closest Value in BST

## Problem Domain

Write a function that takes in a Binary Search Tree (BST) and a target integer value and returns the closet value to that target value contained in the BST.

You can assume that there will only be one closest value.

Each `BST` node has an integer `value`, a `left` child node, and a `right` child node. A node is said to be a valid `BST` node if and only if it satisfies the BST property: its `value` is strictly greater than the values of every node to its left; its `value` is less than or equal to the values of every node to its right; and its children nodes are either valid `BST` nodes themselves or `None` / `null`.

### **input**

```python
tree = 10
      /  \
     5    15
    / \  /  \ 
   2   5 13  22
  /        \
 1          14
 target = 12   
```

### **output**

```python
13
```

### **visual**

```python

closet = (infinity)

       10         12 -> 13
      /  \
     5    15
    / \  /  \ 
   2   5 13  22
  /        \
 1          14

|10 - 12| = 2

|(infinity) - 12| = (infinity)

closest = 10

|15 - 12| = 3 # don't update closest value
|10 - 12| = 2
|13 - 12| = 1 compare to |10 - 12| = 2

update closest = 13

```

### **algorithm**

if there is no tree
return closest

if the absolute value of target minus closest is greater than the absolute value of target minus the value at the tree
then reassign closest to the tree value
if target is less than tree value
go to the left of the tree
if the target is greater than tree value
go to the right of the tree.
else, return closest.

### **code**

```python
def findClosestValueInBst(tree, target):
  return findClosestValueInBstHelper(tree, target, float("inf"))

def findClosestValueInBstHelper(tree, target, closest):
  if tree is None:
    return closest
  
  if abs(target - closest) > abs(target - tree.value):
    closest = tree.value
  
  if target < tree.value:
    return findClosestValueInBstHelper(tree.left, target, closest)
  elif target > tree.value:
    return findClosestValueInBstHelper(tree.right, target, closest)
  else: 
    return closest

```

### **testing**

test for strings
test for tree

### **BigO**

Average: Time = O(log(N)), because we are limiting on average half the tree everytime we explore a node.

Worst: Time = O(N), When a tree only has one branch.

Space = O(1), calling it on each node by adding frames on the call stack, which means we are using extra memory.

Worst: Space = O(1), because if we solve this iteratively we are storing the node that we are exploring.

### **Design Choice and Why**

Went with a recursive binary search as it is excellent practice and finding and holding a solution. Unfortunately, this approach uses `O(log(N))` that will then take in as much as the tree depth lets it.

-----

-----

### 👈 [Back to Table of Contents](../toc.md)
