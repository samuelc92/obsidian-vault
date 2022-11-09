# B-Tree

The B-Tree is a type of m-way tree that is commonly used for disc access. A B-Tree with order m can only have m-1 keys and m children. One of the primary reasons for using a B tree is its ability to store a large number os keys in a single node as well as large key values while keeping the three´s height relatively small.

A B-tree of order 4 is shown below in the image:

![[b-tree.jpg]]

- All of the leaves are at the same height;
- The term minimum degree 't' describes a B-tree. The value of 't' is determined by the size of the disc block;
- Except for root, every node must have at least t-1 keys. The root must contain at least one key;
- All nodes can have no more than 2\*t -1 keys;
- The number of children of a node is equal to its key count plus one;
- A node´s keys are sorted in ascending order. The child of two keys k1 and k2 contains all keys between k1 and k2;
- In contrast to Binary Search Tree, B-Tree grows and shrinks from the root;

## Use cases

- It is used to access data stored on discs in large databases;
- Using a B-Tree, you can search for data in a data set in significantly less time;

## Database context

Like [[sstable]], B-Tree keep key-value pairs sorted by key, which allow efficient key-value lookups and range queries. B-Tree breaks the database down into fixed-size blocks or pages, and read or write one page at a time, one page can have a reference to another. 

If you want to update the value for an existing key in a B-tree, you search for the leaf page containing that key, change the value in that page, and write the page back to disk. If you want to add a new key, you need to find the page whose range encompasses the new key and add it to that page. If there isn't enough free space in the page to accomodate the new key, it is split into two half-full pages and, the parent page is updated.