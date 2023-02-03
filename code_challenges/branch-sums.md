# Branch Sums

## Problem Domain

Write a function that takes in a Binary Tree and returns a list of its branch sums ordered from leftmost branch sum to rightmost branch sum.

A branch sum is the sum of all values ina Binary Tree branch. A binary Tree branch is a path of nodes ina tree that starts at the root node and ends at any leaf node.

Each `BinaryTree` node as an integer `value`, a `left` child node, and a `right` child node. Children nodes can either be a `BinaryTree` nodes themselves or `None`/`null`.

### **input**

```python
tree =   1
      /     \
     2       3
   /   \    /  \
   4    5  6    7
 /   \ /   
8    9 10    
```

### **output**

```python
[15, 16, 18, 10, 11]
# 15 == 1 + 2 + 4 + 8
# 16 == 1 + 2 + 4 + 9
# 18 == 1 + 2 + 5 + 10
# 10 == 1 + 3 + 6
# 11 == 1 + 3 + 7
```

### **visual**

```python
tree =   1
      /     \
     2       3
   /   \    /  \
   4    5  6    7
 /   \ /   
8    9 10  

At the left most tree
sum = 0 + 1
sum = 1 + 2
sum = 3 + 4
sum = 7 + 8
sum = 15 stops at leaf, at this to `list of sums` which is passed to each call

sums = [15]

```

### **algorithm**

Start at root and add current sum and current node then go left and right.
keep adding until we reach the leafs.
Add up each branch sum and return sums.

### **code**

```python
class BinaryTree:
  def __init__(self, value):
    self.value = value
    self.left = None
    self.right = None

def branchSums(root):
  sums = []
  calculateBranchSums(root, 0, sums)
  return sums

def calculateBranchSums(node, runningSum, sums):
  if node is None:
    return

  newRunningSum = runningSum + node.value
  if node.left is None and node.right is None:
    sums.append(newRunningSum)
    return

  calculateBranchSums(node.left, newRunningSum, sums)
  calculateBranchSums(node.right, newRunningSum, sums)

```

### **testing**

### **BigO**

Time: `O(n)`, have to traverse through all of the node to account for each of their values. Adding that value to the sum. Constant time operations at n times.

Space: `O(log(n))`,Whenever you are making a recursive call, you are suddenly eliminating half of the nodes, by starting to the left of the tree, and moving to the right. Which you will never have more than that many calls in the call stack.

We know that we are going to be bounded by O(n), we are not going to exceed N branch sums.

### **Design Choice and Why**

Recursive calls work best for Binary Search trees.

-----

-----

### 👈 [Back to Table of Contents](../toc.md)
