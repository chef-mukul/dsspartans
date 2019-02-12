# Binary Tree
A tree which has at most 2 children
Unlike Arrays, Linked Lists, Stack and queues, which are linear data structures, trees are hierarchical data structures.
A binary tree is an ordered tree having either root or node
which have right subtree and left tree or leaves
e.g. sometimes order makes sense, like expression 
and sometimes it doesn't e.g. like file system
## Some common glosary in  Binary Tree
root
ancestor
descendant
parent
child
sibling
leaves
depth(leve) -> roots level is zero/one

Height of node – The height of a node is the number of edges on the longest downward path between that node and a leaf.
height of leaf = zero

degree -> number of child subtree for a node 
## Different type of  binary trees
* Full Binary Tree
A Binary Tree is full if every node has 0 or 2 children. Following are examples of a full binary tree
![fullbinarytree.PNG](:storage\f4299f86-d831-4ea9-9b42-680a7a4b37bb\325165f3.PNG)
* Complete Binary Tree
A Binary Tree is complete Binary Tree if all levels are completely filled except possibly the last level and the last level has all keys as left as possible
![completebinarytree.PNG](:storage\f4299f86-d831-4ea9-9b42-680a7a4b37bb\717df7c3.PNG)
![unboundedtree.PNG](:storage\f4299f86-d831-4ea9-9b42-680a7a4b37bb\f96e81be.PNG)
* Perfect Binary Tree
A Binary tree is Perfect Binary Tree in which all internal nodes have two children and all leaves are at the same level.

A Perfect Binary Tree of height h (where height is the number of nodes on the path from the root to leaf) has 2h – 1 node.

* A degenerate (or pathological) tree
A Tree where every internal node has one child. Such trees are performance-wise same as linked list.

* Skew Tree
a tree only have child in its left sub tree or right sub tree

* Balanced Binary Tree
A binary tree is balanced if the height of the tree is O(Log n) where n is the number of nodes. For Example, AVL tree maintains O(Log n) height by making sure that the difference between heights of left and right subtrees is 1. Red-Black trees maintain O(Log n) height by making sure that the number of Black nodes on every root to leaf paths are same and there are no adjacent red nodes. Balanced Binary Search trees are performance wise good as they provide O(log n) time for search, insert and delete.

## why choose tree and some common application
1. One reason to use trees might be because you want to store information that naturally forms a hierarchy. For example, the file system on a computer:
2. Trees (with some ordering e.g., BST) provide moderate access/search (quicker than Linked List and slower than arrays).
3. Trees provide moderate insertion/deletion (quicker than Arrays and slower than Unordered Linked Lists).
4. Like Linked Lists and unlike Arrays, Trees don’t have an upper limit on number of nodes as nodes are linked using pointers.

1. Manipulate hierarchical data.
2. Make information easy to search (see tree traversal).
3. Manipulate sorted lists of data.
4. As a workflow for compositing digital images for visual effects.
5. Router algorithms
6. Form of a multi-stage decision-making (see business chess).
7. Heap is a tree data structure which is implemented using arrays and used to implement priority queues.
8. B-Tree and B+ Tree : They are used to implement indexing in databases.
9. Syntax Tree: Used in Compilers.
10. K-D Tree: A space partitioning tree used to organize points in K dimensional space.
11. Trie : Used to implement dictionaries with prefix lookup.
12. Suffix Tree : For quick pattern searching in a fixed text.
## Basic Tree structure
```java
/* Class containing left and right child of current 
node and key value*/
class Node 
{ 
	int key; 
	Node left, right; 

	public Node(int item) 
	{ 
		key = item; 
		left = right = null; 
	} 
} 
class BinaryTree 
{ 
    // Root of Binary Tree 
    Node root; 
  
    // Constructors 
    BinaryTree(int key) 
    { 
        root = new Node(key); 
    } 
  
    BinaryTree() 
    { 
        root = null; 
    } 
  
    public static void main(String[] args) 
    { 
        BinaryTree tree = new BinaryTree(); 
  
        /*create root*/
        tree.root = new Node(1); 
  
        /* following is the tree after above statement 
  
              1 
            /   \ 
          null  null     */
  
        tree.root.left = new Node(2); 
        tree.root.right = new Node(3); 
  
        /* 2 and 3 become left and right children of 1 
               1 
             /   \ 
            2      3 
          /    \    /  \ 
        null null null null  */
  
  
        tree.root.left.left = new Node(4); 
        /* 4 becomes left child of 2 
                    1 
                /       \ 
               2          3 
             /   \       /  \ 
            4    null  null  null 
           /   \ 
          null null 
         */
    } 
}
```

## Some properties of binary tree
1) The maximum number of nodes at level ‘l’ of a binary tree is 2l-1.
2) Maximum number of nodes in a binary tree of height ‘h’ is 2h – 1
if height of a node with single node = 1
otherwise its 2(h+1) -1 
3) In a Binary Tree with N nodes, minimum possible height or minimum number of levels is  ⌈ Log2(N+1) ⌉   
4) A Binary Tree with L leaves has at least   ⌈ Log2L ⌉ + 1   levels
5) In Binary tree where every node has 0 or 2 children, number of leaf nodes is always one more than nodes with two children.
 L = T + 1
Where L = Number of leaf nodes
      T = Number of internal nodes with two children
      
## Handshaking lemma and interesting tree properties
Handshaking lemma is about undirected graph. In every finite undirected graph number of vertices with odd degree is always even. The handshaking lemma is a consequence of the degree sum formula (also sometimes called the handshaking lemma)
$$ \sum_{u \epsilon v} deg(v) = 2\left  | E \right | $$
 
 
 1) In a k-ary tree where every node has either 0 or k children, following property is always true.

  L = (k - 1)*I + 1
Where L = Number of leaf nodes
      I = Number of internal nodes  

􀂅level i has 2i nodes
􀂅In a tree of height h
􀂅leaves are at level h
􀂅No. of leaves is 2h
􀂅No. of internal nodes = 1+2+22+…+2h-1 = 2h-1
􀂅No of internal nodes = no of leaves -1
􀂅Total no. of nodes is 2h+1-1 = n
􀂅In a tree of n nodes
􀂅No of leaves is (n+1)/2
􀂅Height = log2 (no of leaves)

## ADT's of tree
ADTs for Trees
􀂄 generic container methods: size(), isEmpty(),
elements()
􀂄 positional container methods: positions(),
swapElements(p,q), replaceElement(p,e)
􀂄 query methods: isRoot(p), isInternal(p),
isExternal(p)
􀂄 accessor methods: root(), parent(p),
children(p)
􀂄 update methods: application specific

ADTs for Binary Trees
􀂄 accessor methods: leftChild(p),
rightChild(p), sibling(p)
􀂄 update methods:
􀂅expandExternal(p), removeAboveExternal(p)
􀂅other application specific methods

## The node structure
 ![nodestructureofbinarytree.PNG](:storage\f4299f86-d831-4ea9-9b42-680a7a4b37bb\305cb671.PNG)
 ![rootedtree.PNG](:storage\f4299f86-d831-4ea9-9b42-680a7a4b37bb\75ded66b.PNG)
 ![unboundedtree.PNG](:storage\f4299f86-d831-4ea9-9b42-680a7a4b37bb\369add27.PNG)
now in unbounded tree we create a linkedlist of nodes for childs
otherwise for every child we keep have to modify the nodes
in our tree class

## References
[Binary Tree \| Set 1 (Introduction) - GeeksforGeeks](https://www.geeksforgeeks.org/binary-tree-set-1-introduction/)


[Handshaking Lemma and Interesting Tree Properties - GeeksforGeeks](https://www.geeksforgeeks.org/handshaking-lemma-and-interesting-tree-properties/)
