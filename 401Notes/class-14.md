# Trees
- trees is a abstract data type represent a heirarcle tree structure. and it is represent with root value and subtree values that have parents, all of that represent in connected nodes.
- we dicuss three types of trees in our course:
   - binary tree
   - binary search tree
   - k-ary tree
- traversal between nodes it's a core idea in dealing and manipulating data in trees, and there two types of traversaling:
    - depth first
    - breadth first
- there is eight terminology we have to understand in order to understand the trees:
1. root=> the beggining node of the tree
1. left=> refrence of child to node
1. right=> refrencde to another child for same node
1. edge=> the link between the parent and child node
1. k=> its the maximam number of child that node have.
1. height=> maximum number of edges in the tree beween the root node and the last node
1. leaf=> the last node in the tree, or we can say the node that don't have a children in the tree
1. node=> it's element in the tree have two thing:
   - value
   - refrence to another node
![](img/14a.PNG)
- in depth first traverse we will start traverse from the in height direction from root to the leaf, and there is three way in depth first traverse:

    Pre-order: root >> left >> right
    In-order: left >> root >> right
    Post-order: left >> right >> root
- in breadth first traverse we use queue to implement it and recursion, and will be from top nodes to bottom nodes.   

depth first | breadth first
------------ | -------------
use recursion  |  use recursion
use stack  |  use queue
go vertically in the tree | go horezontaly on the tree

![](img/14b.jpeg)
- the binary search tree it's a tree every node in have just two children except the leaf node, and the difference between it and between the regular binary tree is that the search one is organised in a way that make the values of the left nodes smaller than the value of root, and the right nodes larger than the root wich made the searching easier.