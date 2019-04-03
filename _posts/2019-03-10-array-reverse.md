---
title: "Reverse an array"
promo_title: "Reverse an array"
date: 2019-03-10
categories: [algorithms]
teaser: "Reverse an array in-place"
comments: true
---

**Problem:** Reverse a given array.

```
Input = [1, 2, 3, 4, 5, 6], Output = [6, 5, 4, 3, 2, 1]
```

**In Python:**

Use the slicing operation to get a copy of the reversed array.

```python
def reverse_array(arr):
  return arr[::-1]
```

Use the in-built `.reverse()` to reverse the array in-place.

```python
def reverse_array(arr):
  return arr.reverse()
```

Also, you can use the in-built `.reversed()` to get an iterator that iterates through the elements in the reverse order.

```python
def reverse_array(arr):
  return reversed(arr)
```

To write our own method, we're going to swap elements from one end to the other.

```python
def reverse_array_v1(arr):
    left = 0
    right = len(arr) - 1
    while left < right:
        arr[left], arr[right] = arr[right], arr[left]
        left += 1
        right -= 1
```

Let's try to solve this via recursion. We will reverse and return a copy of the array but the given array remains unchanged.

A recursion procedure consists of a base case or terminating case and recursive rules or reduction steps that converges to the base case.

The base case here is to return the given array if it contains just a single element. And a reduction step we can think of is swapping elements from one end to the other end. Instead of swapping all of the elements in one call, we do one swap per call and call the same function with a reduced/simplified input. In this case, it's the reduced size (n-2) of the array that gets passed in each recursive call. Each call performs a swapping until the base case. Once the base case is reached, we return the result.

```python
def reverse_array_v2(arr):
    if len(arr) < 2:
        return arr

    return [arr[len(arr) - 1]] + reverse_array_v2(arr[1:(len(arr) - 1)]) + [arr[0]]
```

Full source code is [here](https://github.com/pradheap/coding-problems/blob/master/array_reverse/source.py){:target="_blank"} and Unit tests are [here](https://github.com/pradheap/coding-problems/blob/master/array_reverse/test.py){:target="_blank"}.

**In Javascript:**

```javascript
function reverse(arr) {
  return arr.reverse();
}
```