# Asymptotic Notation

The efficiency of an algorithm depends on the amount of time, storage and other resources required to execute the algorithm. The efficiency is measured with the help of asymptotic notations.

An algorithm may not have the same performance for different types of inputs. With the increase in the input size, the performance will change.

## Big O Notation

It is used to describe **the worst case** scenario of an algorithm.

It is used to compare algorithms and to determine which algorithm is better.

It refers to the upper bound of a function.

## Big-Theta Notation

It refers to the exact bound of a function.

It is used to describe **the exact growth rate ( the average case )** of a function.

## Big-Omega Notation

It is used to describe **the best case** scenario of an algorithm and the lower bound of a function.

It is opposite of Big O notation.

## Common Runtimes

| O(1)       | Constant     |
|------------|--------------|
| O(log n)   | Logarithmic  |
| O(n)       | Linear       |
| O(n log n) | Linearithmic |
| O(n^2)     | Quadratic    |
| O(n^3)     | Cubic        |
| O(2^n)     | Exponential  |
| O(n!)      | Factorial    |
| O(n^n)     | Polynomial   |

### Constant

- The simplest and most efficient.
- Always take the **same** amount of time to run, regardless of the size of the input.
- For an algorithm, the base case scenario, and the goal of all algorithms.

### Logarithmic

- The **second-fastest** algorithm.
- Faster than linear algorithm, but slower than constant algorithm

### Linear

- Have a runtime that is directly **proportional** to the size of the input.

### Polynomial

- Have a runtime that is a polynomial function of the input size.

### Exponential

- Grow at a rate of 2^n.

### Factorial

- Have a runtime of $n!$.
- The worst case scenario for an algorithm.
- **Very inefficient and should be avoided**.