# Keywords

- A linear collection of items
- FIFO

# Content

Queue is a linear collection of items where items are inserted and removed in a particular order. The queue is also called a FIFO abstract data structure because it follows the “First In, First Out” principle i.e, the item that is inserted in the first is the one that is taken out first.

Queue has some similarities this a stack. But in a fundamental way is different. This distinguishes them from stacks which are LIFO. Last In, first out.

How can you implement a queue? One way is with a linked list, where you have a head and a tail pointer.

## Implementation with  Linked List

Enqueue ⇒ use List. PushBack

Dequeue ⇒ use List. TopFront and List. PopFront

# Summary

- Queues can be implemented with either a linked list ( with tail pointer ) or an array
- Each queue operation is O(1) : Enqueue, Dequeue, Empty

# References

[queue.txt](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/340951c7-4fa9-45f5-87ae-8f9a2b1776bd/queue.txt)

[Queues - Basic Data Structures | Coursera](https://www.coursera.org/learn/data-structures/lecture/EShpq/queues)