# Augmenting Paths

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

I watched two videos to understand the ford fulkerson algorithm better. This is the one that really helped:
https://www.youtube.com/watch?v=Tl90tNtKvxs
I then realized we only needed the augmenting paths function which can be implimented using depth first search. I had the help of AI to figure out how to concatenate the start with the return of the recursive call for the rest of the path.

When we talked about the Ford-Fulkerson algorithm to find the maximum flow
through a graph, I mentioned the "find an augmenting path" function. You're
going to implement this function. Start with the template I provided in
`code.js`. Use an adjacency list data structure to represent the graph and node
names, not indices, to indicate start and end node. The function returns a list
of node names, starting with the start node and finishing with the end node. If
start and end node are the same, it should return a list containing only this
node. If there is no path, you must return an empty list.

Test your new function; I've provided some basic testing code in `code.test.js`.

To illustrate, here's an example graph:
![example graph](graph.png)

Here's the call for this graph:

```javascript
var graph = {'foo': {'boo': 7},
             'boo': {'foo': 3, 'bar': 2},
             'bar': {'boo': 4}};
augmentingPath(graph, 'foo', 'bar');
```

The call would return `['foo', 'boo', 'bar']`.

Feel free to use other data structures, but you'll have to change the test code
accordingly.

## Runtime Analysis

What is the worst-case big $\Theta$ complexity of your implementation? Add your
answer, including your reasoning, to this markdown file.

I believe the $\Theta$ complexity of this algorithm is $\Theta(v * e)$. This is because
we search through all nodes in the worst case via the recursive call. Then in each call,
we have a for loop that goes through each adjacent node but only if there is an edge because
we used an adjacency list. This means we would itterate through all of the edges which gives us
a final complexity of $\Theta(v * e)$.
