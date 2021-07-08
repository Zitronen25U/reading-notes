# Class 35 Reading Notes

## Graphs

### What is it?

- non-linear data structure that can be looked at as a collection of **vertices** for **nodes**

### Common Terms

1. vertex
2. edge
3. neighbor
4. degree

### Directed vs Undirected

- and undirected graph is a graph where the edge is undirected or bi directional

- no specific order of connection it seems

- directed is a diagraph.

- every edge is directed

### Complete vs Disconnected

- You can have nodes disconnected from the linked graph nodes

## Traversals

### Breadth First

- travels like a tree
    -Enqueue into queue
    -Dequeue 1st node
    -if dequeue node has unvisisted child nodes, add the unvisited children to visited set and queue them

### Depth First

- push root node into stack
- while loop (stack is not empty)
- PEEK at the top node in stack
- if top has unvisited children, mark top node as visited then **push** any unvisited children back into the stack
- if top has no children, **pop** node off stack
- Repeat until empty

## Real World Usage

- GPS
- Driving Directions
- Social Networks
- Airline Traffic
- Netflix suggestions