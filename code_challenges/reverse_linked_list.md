# Reverse Linked LIst

## Problem Domain

Given the `head` of a singly linked list, reverse the list, and return the reversed list.

### **input**

Head = [1, 2, 3, 4, 5]

### **output**

[5, 4, 3, 2, 1]

### **visual**

null -> 1 -> 2 -> 3 -> 4 -> 5
  ^     ^
prev   curr

null <- 1  <- 2   3 -> 4 -> 5
        ^     ^
       prev   curr

null <- 1  <- 2 <-  3  4 -> 5
              ^     ^
            prev   curr

null <- 1  <- 2 <-  3  <- 4  <- 5     null
                                ^     ^
                               prev   curr

### **algorithm**

assign previous to none
assign current to head

while current is not null
  next is assigned to next of current.
  next of current assign to prev
  prev assign to current
  current is assign to next

### **code**

```python
def reverseList(head):
  prev = None
  current = head

  while current:
    temp_next = current.next
    current.next = prev
    prev = current
    current = temp_next
  return prev
```

### **testing**

test for integers
test for strings
test for array

### **BigO**

O(n), for both **time** and **space**, because this code will take however long the length of the array is, so 1 to 100. And there isn't any storage here.

### **Design Choice and Why**

Went with the iterative approach, as it is explicit to read and easy to decipher.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/reverse-linked-list)

-----

### 👈 [Back to Table of Contents](../toc.md)
