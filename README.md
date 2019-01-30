# Computer Science Conceptual Questions

## Difference between big endian v/s little endian? 
Big-Endian (BE) / Little-Endian (LE) are two ways to organize multi-byte words. For example, when using two bytes to represent a character in UTF-16, there are two ways to represent the character 0x1234 as a string of bytes (0x00-0xFF):
```
Byte Index:      0  1
---------------------
Big-Endian:     12 34
Little-Endian:  34 12
```

In order to decide if a text uses UTF-16BE or UTF-16LE, the specification recommends to prepend a Byte Order Mark (BOM) to the string, representing the character U+FEFF. So, if the first two bytes of a UTF-16 encoded text file are FE, FF, the encoding is UTF-16BE. For FF, FE, it is UTF-16LE.

A visual example: The word "Example" in different encodings (UTF-16 with BOM):
```
Byte Index:   0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15
------------------------------------------------------------
ASCII:       45 78 61 6d 70 6c 65
UTF-16BE:    FE FF 00 45 00 78 00 61 00 6d 00 70 00 6c 00 65
UTF-16LE:    FF FE 45 00 78 00 61 00 6d 00 70 00 6c 00 65 00
```
[Reference](https://stackoverflow.com/questions/701624/difference-between-big-endian-and-little-endian-byte-order)

## What is tree in datastructure ?
- Tree is a non linear datastructure which depicts a hierarchical structure. 
- There is a root node in tree. 
- Each node is refered by a parent and can have any no. of childs. 
- There won't be any cycle in the tree. 

## What is binary tree ?
- A tree whose elements have at most 2 children is called a binary tree. Since each element in a binary tree can have only 2 children, we typically name them the left and right child.
- The topmost node in the tree is known as root. 

## Tree terminologies
- Depth of node: Number of edge between root and node. 
- Height of node: Number of edge between depest leaf and node.
- Height of tree: Height of the root. 
- Full Binary tree: Each node have exactly 0 or 2 children.
- Complete Binary tree : Binary tree which is completely filled, with an exception at bottom level, which is filled from left to right. 

## Traversal in binary tree
- Pre-order 
- In-order
- Post-order

## What is binary search tree?
A BST is a binary tree where nodes are ordered in the following way:
- Each node contains one key (also known as data)
- The keys in the left subtree are less then the key in its parent node, in short L < P;
- The keys in the right subtree are greater the key in its parent node, in short P < R;
- Duplicate keys are not allowed.

## Binary Search Tree (BST) Complexities
#### Average
- Insert : O(log n)
- Delete : O(log n)
- Search : O(log n)

#### Worst
- Insert : O(n)
- Delete : O(n)
- Search : O(n)

Reference - [BigOCheetSheet](http://bigocheatsheet.com/)

## What is Trie datastructure ?
A trie is a tree-like data structure whose nodes store the letters of an alphabet. By structuring the nodes in a particular way, words and strings can be retrieved from the structure by traversing down a branch path of the tree.

```
struct TrieNode
{
     struct TrieNode *children[ALPHABET_SIZE];

     // isEndOfWord is true if the node
     // represents end of a word
     bool isEndOfWord;
};
```

- Insert a word - O(M)
- Search a word - O(M)

where M is length of the string. 

##  What is AVL tree ?
An AVL tree is a self-balancing binary search tree. In an AVL tree, the heights of the two child subtrees of any node differ by at most one; if at any time they differ by more than one, rebalancing is done to restore this property.

All time complexities - O(log n)

## What is Red Black tree?
A red–black tree is a kind of self-balancing binary search tree. Each node of the binary tree has an extra bit, and that bit is often interpreted as the color of the node. These color bits are used to ensure the tree remains approximately balanced during insertions and deletions.

Properties of Red black tree
1. Every node has a color either red or black.
2. Root of tree is always black.
3. There are no two adjacent red nodes (A red node cannot have a red parent or red child).
4. Every path from a node (including root) to any of its descendant NULL node has the same number of black nodes.

All operations are O(log n)
