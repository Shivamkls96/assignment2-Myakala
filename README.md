# assignment2-Myakala
# Shiva Krishna Myakala
###### Coorg
I like coorg because of the **climatic** conditions.
Coorg is called as **Scotland of India**.
*** 
### Travel Directions 
1. Take flight
    1. to Chicago,
    2. to delhi,
    3. to bangalore <br/>
3. Take Cabs
    1. From maryville to kansas airport,
    2. From bangalore take a cab to Coorg. 
- Items to be brought for maximum enjoyment
    - jacket
    - shoes
    - dresses
    - food

[Shiva](AboutMe.md)

***Food Reco***

**Food Recommendations** that I would recommend others
|food/drink item| Location| money to pay |
| --- | --- | ---:|
|Punugulu | Hyderabad | 20 |
|Tea | Charminar | 10 |
|Mirchi Bajji | Hyderabad | 25 |
|Mutton Biryani | Bawarchi | 120 |

***Favorite Quotations***

# Inspiring Quotations
>The best and most **beautiful things** in the world cannot be seen or even touched - **they must be felt with the heart.** <br>
>The best **preparation** for tomorrow is doing your **best today**.
*H. Jackson Brown, Jr.*

***Graph flows/Matchings/Misc***

# Algorithm to perform breadth first search in an unweighted graph

>Breadth-first search (BFS) is an algorithm for searching a tree data structure for a node that satisfies a given property. It starts at the tree root and explores all nodes at the present depth prior to moving on to the nodes at the next depth level. <br>
[Link to the source](https://en.wikipedia.org/wiki/Breadth-first_search)


import java.io.*;
import java.util.*;
 
// This class represents a directed graph using adjacency list
// representation
class Graph
{
    private int V;   // No. of vertices
    private LinkedList<Integer> adj[]; //Adjacency Lists
 
    // Constructor
    Graph(int v)
    {
        V = v;
        adj = new LinkedList[v];
        for (int i=0; i<v; ++i)
            adj[i] = new LinkedList();
    }
 
    // Function to add an edge into the graph
    void addEdge(int v,int w)
    {
        adj[v].add(w);
    }
 
    // prints BFS traversal from a given source s
    void BFS(int s)
    {
        // Mark all the vertices as not visited(By default
        // set as false)
        boolean visited[] = new boolean[V];
 
        // Create a queue for BFS
        LinkedList<Integer> queue = new LinkedList<Integer>();
 
        // Mark the current node as visited and enqueue it
        visited[s]=true;
        queue.add(s);
 
        while (queue.size() != 0)
        {
            // Dequeue a vertex from queue and print it
            s = queue.poll();
            System.out.print(s+" ");
 
            // Get all adjacent vertices of the dequeued vertex s
            // If a adjacent has not been visited, then mark it
            // visited and enqueue it
            Iterator<Integer> i = adj[s].listIterator();
            while (i.hasNext())
            {
                int n = i.next();
                if (!visited[n])
                {
                    visited[n] = true;
                    queue.add(n);
                }
            }
        }
    }
 
    // Driver method to
    public static void main(String args[])
    {
        Graph g = new Graph(4);
 
        g.addEdge(0, 1);
        g.addEdge(0, 2);
        g.addEdge(1, 2);
        g.addEdge(2, 0);
        g.addEdge(2, 3);
        g.addEdge(3, 3);
 
        System.out.println("Following is Breadth First Traversal "+
                           "(starting from vertex 2)");
 
        g.BFS(2);
    }
}

[Code Source](https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/)







