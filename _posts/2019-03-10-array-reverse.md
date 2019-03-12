---
title: "Reverse an array"
promo_title: "Reverse an array"
date: 2019-03-10
categories: [algorithms]
teaser: "Reverse an array in-place"
comments: true
---

Problem: Reverse a given array in-place.

```
Input = [1, 2, 3, 4, 5, 6], Output = [6, 5, 4, 3, 2, 1]
```

**In Python:**

You can use slicing operation to get a copy of the reversed array.

```python
def reverse_array(arr):
  return arr[::-1]
```
But you can use the in-built `.reverse()` to reverse the array in-place.

```python
def reverse_array(arr):
  return arr.reverse()
```

To write our own method, we're going to swap elements from one end with the other end.

```python
def reverse_array(arr):
    left = 0
    right = len(arr) - 1
    while left < right:
        arr[left], arr[right] = arr[right], arr[left]
        left += 1
        right -= 1
```

Full source code is [here](https://github.com/pradheap/coding-problems/blob/master/array_reverse/source.py) and Unit tests are [here](https://github.com/pradheap/coding-problems/blob/master/array_reverse/test.py).

**In Javascript:**

```javascript
function reverse(arr) {
  return arr.reverse();
}
```