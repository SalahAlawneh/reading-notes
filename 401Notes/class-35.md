# Graphs
## Basics
- the graphs is non linear datastructure
- there is four terminology i have to be familiar with in order to understand the graph:
   - vertex which the same of node and this node have a connection with more than one as i said it's non linear 
   - edge=> the link between the vertices
   - neighbor=> relative to a node it's it linked node
   - degree=> number of nodes connected to one node

## Directed vs Undirected
- the undirected one is the graph her vertices edges don't point on each other
- the directed graph is the graph have vertices edges point to each other
## Completed vs Connected vs Disconnected
- those three types are about the edges in every node:
   - completed=> every node have edges on every another node
   - connected=> every node have at least one edge
   - unconnected=> a graph that has nodes don't have any edge
## Acyclic vs Cyclic
- cyclic grapch=> are the graph have at least one node traverse and at least can back to itself.
- Acyclic grapch=> are the graph don't have any node traverse and back to itself.
## Graph Representaion
- there is two ways to represent a graph:
   - 2d matrix:
   you will writer every single node on top of columns and rows, and inside the matrix you will put 1 if there is edge between the two nodes and zero if it's not
   - linked list beside each other=> we will righ every sing node in bottom of each other and after beside every one of them i will draw an arrow point to every node have a common edge with it
- most used representation is adjacent linked list, for me i prefer the matrix=> maybe after knowing things better i will change my mind
## Weighted Graphs
- if the edge between two nodes have number on it then we call it weighted graph
- in matrix we can represent that with putting the weighted number instead of 1.
- in adjacent list we can write like this `a->b,7`
- what's realy that mean to have number above the edge?    
i don't know, i will search about it after finshing some tasks i'm late on submiting them    
## Traversals
- there is two types of traverse:
   - breadth first
   - depth first    
- in cyclic graph we can end up with infinite loop, so we have to make states for the nodes, to change the one we transverse in with `visisted` to not trasverse in it again
- if there is unconnected node we will not visit it 
- about the psedocode and java implementation i will leave it to the lecture and code challenge time
## Real Applications
- the graph is a big thing, and there is a lot of things i can learn about it, but in gerneral it's used for things related to locations and communcation apps like=> maps, street locations, social network, suggest product and airplane services.