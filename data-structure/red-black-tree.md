# Red-Black Tree

Red Black Tree are a type of self-balancing binary search tree. Rudolf Bayer invented it in 1972 and dubbed it "symmetric binary B-trees."
A red-black tree is a Binary tree in which each node has a colour attribute, either red or black. By comparing the node colours on any simple path from the root to a leaf, red-black trees ensure that no path is more than twice as long as any other, ensuring that the tree is generally balanced.
Red-black trees are similar to binary trees in that they both store their data in two's complementary binary formats. However, red-black trees have one important advantage over binary tree: they are faster to access.

![[red-black-tree.jpg]]

## Rules

- Every node is either red or black;
- The tree's root is always black;
- There are no two red nodes that are adjacent;
- There is the same number of black nodes on every path from a node to any of its descendant's NULL nodes;
- All of the leaf nodes are black;

## Use cases

- The majority of self-balancing BST library functions in C++ or Java use Red-Black Trees;
- It is used to implement Linux CPU Scheduling;
- It is also used to reduce time complexity in the K-mean clustering algorithm in machine learning;
- MySQL also employs the Red-Black tree for table indexes in order to reduce searching and insertion time;