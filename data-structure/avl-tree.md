# AVL Tree

AVL trees are height balancing binary search trees which use the BalanceFactor formula to balance it.

BalanceFactor compares the heights of the left and right subtrees and ensures that the difference is less than one.

**BalanceFactor = height(left-subtree) - height(right-subtree)**

![[avl-tree.jpg]]


## Operations

- **Insertion**: Insertion in an AVL tree is done in the same way that it is done in a binary search tree. However, it may cause a violation in the AVL tree property, requiring the tree to be balanced. Rotations can be used to balance the tree;
- **Deletion**: Deletion can also be performed in the same manner as binary search tree. It can also unbalance the AVL tree, so rotations ca be used to balance;

## Rotations

- **Left rotation:** When a node is inserted into the right subtree of the right subtree and the tree become unbalanced, we perform a single left rotation;
- **Right rotation:** If a node is inserted in the left subtree of the left subtree, the AVL tree may become unbalaced. The tree the requires right rotation;
- **Left-Right rotation:** The RR rotation is performed first on the subtree, followed by the LL rotation on the entire tree;
- **Right-Left rotation:** The LL rotation is performed first on the subtree, followed by the RR rotation on the entire tree;

## Use cases

- Used for in-memory sets and dictionaries;
- Used in database applications where there are fewer insertions and deletions but frequent data lookups are required;
- Used in applications that require improved searching;