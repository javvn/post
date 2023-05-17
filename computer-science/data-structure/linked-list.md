# Singly-Linked List

## Keywords

- Linear Collection of Elements
- Not consecutive in memory
- Point to next element
- Dynamic size
- Not same type

Linked lists are less rigid in their storage stucture and elements are usually not stored in contiguous locations, hence they need to be stored with additional tags giving a reference to the next element. So Random access is not possible. Only linear searching !

A linked list has the same name as a link in a chain. so linked list got a head pointer that points to a node that then has some data and points to another node, points to another node and eventually points to one that doesn’t point any farther.

## Times for some operations

| Singly-Linked List | No tail | With tail |
| --- | --- | --- |
| PushFront ( Key ) | O(1) |  |
| TopFront ( ) | O(1) |  |
| PopFront ( ) | O(1) |  |
| PushBack ( Key ) | O(n) | O(1) |
| TopBack ( ) | O(n) | O(1) |
| PopBack ( ) | O(n) |  |
| Find ( Key ) | O(n) |  |
| Erase ( Key ) | O(n) |  |
| Empty ( ) | O(1) |  |
| AddBefore ( Node, Key ) | O(n) |  |
| AddAfter ( Node, Key ) | O(1) |  |

## vs Array

|  | Array | Linked List |
| --- | --- | --- |
| Search | Fast | Slow |
| Insertion | Slow | Fast |
| Deletion | Slow | Fast |
| Write | Fast | Slow |

# Doubly-Linked List

## Keywords

- No way to get back
- So bidirectional arrow two pointers.

Our problem was that although we had a way to get from a previous element to the next element, we had no way to get back. And what a doubly-linked list say is let’s go ahead and add a way to get back. So we’ll have two pointers, forward and back pointers. That’s the bidirectional arrow. And the way we would actually implement this is, with node that adds an extra pointer. So at any node we can either go forward or we can go backwards.

## Times for some operations

| Doubly-Linked List | No tail | With tail |
| --- | --- | --- |
| PushFront ( Key ) | O(1) |  |
| TopFront ( ) | O(1) |  |
| PopFront ( ) | O(1) |  |
| PushBack ( Key ) | O(n) | O(1) |
| TopBack ( ) | O(n) | O(1) |
| PopBack ( ) | O(n) O(1) |  |
| Find ( Key ) | O(n) |  |
| Erase ( Key ) | O(n) |  |
| Empty ( ) | O(1) |  |
| AddBefore ( Node, Key ) | O(n) |  |
| AddAfter ( Node, Key ) | O(1) |  |

# References

[singly-linked-list.txt](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/996601b2-6f48-4a1f-9166-0c320c79f43c/singly-linked-list.txt)

[Singly-Linked Lists - Basic Data Structures | Coursera](https://www.coursera.org/learn/data-structures/lecture/kHhgK/singly-linked-lists)