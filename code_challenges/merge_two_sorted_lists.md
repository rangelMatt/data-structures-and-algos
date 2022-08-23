# Merge Two Sorted Lists

## Problem Domain

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists in a one **sorted** list. The list should be made by splicing together the nodes of the first two lists.

return the head of the merged linked list.

### **input**

```Python
list1 = [1,2,4], list2 = [1,3,4]
```

### **output**

```Python
[1,1,2,3,4,4]
```

### **visual**

```Python
list1 = [1,2,3,4]
list2 = [1,3,4]

dummy = output = ListNode(0)

list1.val = 1 
list2.val = 3 

list1.val < list2.val

output = list1

```

### **algorithm**

dummy is set to output and output set to ListNode
while list1 and list2 are there
check if the value of list 1 is less than the value of list 2.
if it is, then we set the next output to list1.
then we move to the next list1
else, we set the next output to list 2.
then move to the next list2 value.
then we move the current pointer, output, to the next output.

Once we break out of the loop,
we bring the remainder of list1 to the next output.
And repeat for the list2 as well.

Finally, return dummy.next, which is the head.

### **code**

```Python
    def mergeTwoLists(list1, list2)
        if not list1: return list2
        if not list2: return list1
        
        dummy = output = ListNode(0)
        while list1 and list2:
            if list1.val < list2.val:
                output.next = list1
                list1 = list1.next
            else:
                output.next = list2
                list2 = list2.next
            output = output.next
        
        if list1: output.next = list1
        if list2: output.next = list2
        
        return dummy.next
```

### **testing**

Test if there are strings
Test if there are integers

### **BigO**

Space and Time: O(n), as we are only holding and traversing through how long the lists currently are.

### **Design Choice and Why**

I chose this design choice as it is straightforward and easiest to understand.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/merge-two-sorted-lists/)

-----

### 👈 [Back to Table of Contents](../toc.md)
