# Hash Table

## Keywords

- Without using any iterations
- Key-Value lookup
- Advantage: Does not depend on the size of data

Hash Table, Map, HashMap, Dictionary or Associative are all the names of the same data structure.

Insert / Delete / Search operation constant complexity : O (1)

The Hash table data structure stores elements in key-value pairs. In a hash table, a new index is processed using the keys. And, the element corresponding to that key is stored in the index. This process is called **hashing.**

## Hashing ( Hash Function )

**Takes the input and gives back the hash code / index in array.**


A technique of mapping a large set of arbitrary data to tabular indexes using a hash function. It allows lookups, updating and retrieval operation to occur in a constant time i.e. `O(1)`

We need to perform various operation for a large amount of data. Linear search and binary search perform lookups/search with time complexity of `O(n)` and `O(log n)` respectively.

Need a technique that does not depend on the size of data. Hashing allows lookups to occur in contant time i.e `O(1)`.

## [Hash Collision](https://www.programiz.com/dsa/hash-table)

When the hash function generates the same index for multiple keys, there will be a conflict. This is called a hash collision.

Resolve the hash collision using one of the following techniques.

- Collision resolution by chaining
- Open Addressing: Linear / Quadratic Probing and Double Hashing

# Keep in mind

When creating a hash table,

First,  for the same input the hashing function should always give the same output.

Second, You should make sure to handle the hash table collisions. Hash table collision is return same output feeding different input.

# Applications of Hash Table

- Constant time lookup and insertion is required
- Cryptographic application
- Indexing data is required

# References
[ hash table data structure ] https://www.youtube.com/watch?v=jalSiaIi8j4

[ hashing ] https://www.programiz.com/dsa/hashing