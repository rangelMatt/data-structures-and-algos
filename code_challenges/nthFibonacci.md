# Nth Fibonacci

## Problem Domain

The Fibonacci sequence is defined as followsL the first number of the sequence is `0`, the second number is `1`, the nth number is the sum of the (n-1)th and (n - 2)th numbers. Write a function that takes in an integer `n` and returns the nth Fibonacci number.

Important note: the Fibonacci sequence is often defined with its first two numbers as `F0 - 0` and `F1 = 1`. For the purpose of this question, the first Fibonacci number is `F0`; therefore, `getNthFib(1)` is equal to `F0`, `getNthFib(2)` is equal to `F1`, etc..

### **input**

```python
n = 2
```

### **output**

```python
1 # 0, 1
```

### **visual**

```python
0,1,1,2,3,5,8,13,21,34

fib(n) = fib(n-1) + fib(n-2) for n > 2

if n == 2:
  return 1
elif n == 1:
  return 0
else:
  return fib(n - 1) + fib(n-2)

        fib(6)
      /         \
    fib(5)        fib(4)
    /   \          /     \
fib(4) fib(3)   fib(3) fib(2)
  /   \
fib(3) fib(2)

```

#### Memoization Recursive Solution

```python
if n is memoize
  return memoize[n]
else:
  memoize[n] = fib(n - 1) + fib(n-2)
  return memoize[n]

calculating: fib6 -> fib5 -> 4 -> 3 -> 2
                \      \      \     \  
                 5      3      2       1
            (4th run) (3rd run)(2nd run)(1st run)
```

### **algorithm**

if the number is in memoize
   then return that number

otherwise, call that number to the function and calculate that number subtracting 1 and adding the other call to the function by subtracting 2 while carrying memoize.
finally returning that number

### **code**

```python
def getNthFib(n, memoize = {1: 0, 2: 1}):
  if n in memoize:
    return memoize[n]
  else: 
    memoize[n] = getNthFib(n - 1, memoize) + getNthFib(n - 2, memoize)
    return memoize[n]
```

### **testing**

### **BigO**

Time: `O(2^n)`, because out of each fib, we are splitting the fib into 2, as long as we don't hit the base case.
Space: `O(n)`, we are using the function call stack which will be using a lot of memory. Each fib is waiting in memory until we hit the base case. So they are being stored in the mean time.

#### Memoize

Time `O(n)`, because we are still hitting each number once and for n times.

Space: `O(n)`, because we are using the function call stack which will be using a lot of memory. Each fib is waiting in memory until we hit the base case. So they are being stored in the mean time.

#### Iterative

Time = `O(n)`, because ultimately we have to calculate n fibonacci numbers
Space = `O(1)`, because we are not using space, not storing anything in the call stack.

### **Design Choice and Why**

Put in a few which my favorite take away is the Memoize function as it acts like a dictionary which I am getting more accustomed to using.

-----

### 👈 [Back to Table of Contents](../toc.md)
