# Slowest Key

## Problem Domain

A newly designed kepad was tested, where a tester pressed a sequence of `n` keys, one at a time.

You are given a string `keysPressed` of length `n`, where `keysPressed[i]` was the `i^th` key pressed din the testing sequence, and a sorted list `releaseTimes`, where `releaseTime[i]` was the time the `i^th` key was released. Both arrays are **0-indexed**. The `0th` key was pressed at the time `0`, and every subsequent key was pressed at the **exact** time the previous key was released.

The tester wants to know the key of the keypress that had the **longest duration**. The `i^th` keypress had a duration of `releaseTimes[i] - releaseTime[i - 1]`, and the `0^th` keypress had a duration of `releaseTimes[0]`.

Note that the same key could have been pressed multiple times during the test, and these multiple presses of the same key **may not** have had the same **duration**.

*Return the key of the keypress that had the **longest duration**. If there are multiple such keypresses, return the lexicographically largest key of the keypresses.*

### **input**

releaseTimes = [9,29,49,50]
keysPressed = "cbcd"

### **output**

"c"

### **visual**

```Python
releaseTimes = [9,29,49,50], keysPressed = "cbcd"

paired: 9 = c, 29 = b, 49 = c, 50 = d

9 - 0 = 9 , 29 - 9 = 20 , 49 - 29 = 20, 50 - 49 = 1

c = 9, b = 20, c = 20, d = 1

return lexicographically largest key: c
```

### **algorithm**

iterate over the keys pressed
assign current time to release times index minus the previous release times index
check if the current time is greater than the current index.
update result to the current keyspressed index
update time to the current time.
otherwise if current time is equal to time,
then update the result of the maximum value of the current result and the new value of keyspressed index.
return the lexicographically largest key

### **code**

```Python
def slowestKey(releaseTimes, keysPressed):
        time = releaseTimes[0]
        result = keysPressed[0]
        for index in range(1, len(keysPressed)):
            current_time = releaseTimes[index] - releaseTimes[index - 1]
            if current_time > time:
                result = keysPressed[index]
                time = current_time
            elif current_time == time:
                result = max(result, keysPressed[index])
        return result
```

### **testing**

test for array
test for strings
test for integers

### **BigO**

Time and Space is O(n), as we iterate through the array for however many integers and indexes there are.

### **Design Choice and Why**

This was a good function that anyone could jump in and read, and it is fairly quick when it runs.

-----

#### [**Leet Code Example**](https://leetcode.com/problems/two-sum)

-----

### 👈 [Back to Table of Contents](../toc.md)
