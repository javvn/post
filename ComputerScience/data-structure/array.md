# Keywords

- **Collection of Items**
- **Consecutively**
- **Same Type**
- **Fixed in size**

---

Array store elements in contiguous memory locations, resulting in easily calculable addresses for the elements stored and this allows faster access to an element at a specific index.

*“Contiguous area of memory consisting of equal-size elements.”*

The key point about an array is we have **random access**. That is, we have constant time access to any particular element in an array. Constant time access to read, constant time access to write.

How does that actually work ? Well basically what means is we can just do arithmetic to figure out the address of a particular element.

## One-Dimensional Array

```
ArrayAddr + ElementSize * (i - firstIndex)
```

## Multi-Dimensional Array

### Row Major Ordering

Changing column index.

```
ArrayAddress + (ElementSize*(x - firstIndex)+y)*ElementSize
```

### Column Major Ordering

Changing row index

```
ArrayAddress + (ElementSize*(y - firstIndex)+x)*ElementSize
```

## Times for Common Operations

|  | Add | Remove |
| --- | --- | --- |
| Beginning | O(n) | O(n) |
| End | O(1) | O(1) |
| Middle | O(n) | O(n) |

## Finally

A huge advantage for arrays is that we have thos constant time access to elements, either read or wirte.

An array consists of a contiguous area of memory. because if it were non-contiguous then we couldn’t just do this simple arithmetic to get where we’re going.

We have constant time access to any element, constant time to add or remove at the end and linear time to add and remove at any arbitrary location.

# Reference

[array.txt](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2dd4a653-57b1-40f4-93e2-813226cbb808/array.txt)

[Arrays - Basic Data Structures | Coursera](https://www.coursera.org/learn/data-structures/lecture/OsBSF/arrays)