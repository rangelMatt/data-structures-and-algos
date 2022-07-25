# Two Sum

## Problem Domain

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

-

### **input**

#### 2 args

- nums: array of integers
- target: an integer

### **output**

- Array of indices

### **visual**

nums = [2,7,11,15], target = 9

i = 2
j = 7

if j == target - i

return [i, j]

output = [2, 7]

### **algorithm**

iterate over the nums array with a "slow" search
iterate over the nums array + 1 from the previous slow search, this will search "faster"
  check if nums index is equals to the target minus the first nums index
    return indices for first and second index iterations once the if statement is true.

### **code**

```Python
def twoSum(nums, target):
  for i in range(len(nums)):
    for j in range(i + 1, len(nums)):
      if nums[j] == target - nums[i]:
        return [i, j]
```

### **testing**

test if there is an array
test if there are strings
test for length of array

### **BigO**

Time: O(n^2), because we are looping through the array twice. Looping through the array once is O(n) which n represents the length of the array, be it 1 to 100. Since we are doing this twice, this is squared.

Space: O(1), because we are not holding any information. We are just inputting an array, and this doesn't depend on the size of the input array.

### **Design Choice and Why**

I went with the brute force here because this is where I am comfortable with at the moment. I have completed this earlier in my development life, but it's been so long that I forgot how to code it out.

I would choose a hash table or a dictionary to search through the array for a more dynamic search through the array. This is important because in real life situations we have no idea what size the array could be and if it's 1000 indexes long (likely not going to happen, but could), this will pick the key quickly.

When using the brute force, this will take more time to search through the hypothetical 1000 index long array. That time is a major difference between getting the user what they want then, or moving on to something else.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/two-sum)

-----

### 👈 [Back to Table of Contents](../toc.md)
