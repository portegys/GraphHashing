# GraphHashing
Graph isomorphism testing boosted by path coloring

Graph hashing and isomorphism.

A means of identifying a graph with an MD5 hash is given.
This technique is also used in a graph isomorphism algorithm.
Graphs are isomorphic if they are topologically identical.

References:

T. E. Portegys. "Graph isomorphism testing boosted by path coloring", May 2016. http://arxiv.org/abs/1606.00001<br>
T. E. Portegys. "General Graph Identification By Hashing", Feb. 2008. http://arxiv.org/abs/1512.07263<br>
L. P. Cordella, P. Foggia, C. Sansone, M. Vento. "Performance Evaluation
of the VF Graph Matching Algorithm", Proc. of the 10th ICIAP,
IEEE Computer Society Press, vol. 2, pp. 1038-1041, 1999.<br>
J. R. Ullmann. "An Algorithm for Subgraph Isomorphism", 
Journal of the Assoc. for Computing Machinery, 23, pp. 31-42, 1976.<br>
C. Sayers and A.H. Karp, "RDF Graph Digest Techniques and Potential
Applications", Mobile and Media Systems Laboratory,
HP Laboratories Palo Alto, HPL-2004-95, May 28, 2004<br>
V. Arvind, J. Köbler, G. Rattan, O. Verbitsky. "Graph Isomorphism, Color Refinement, and Compactness", 2015

Required packages:

The UNIX version requires the gcc compiler, make command, and
the bash shell. The Windows version requires the Microsoft Visual
C++ 2013 (or later) IDE.

To build:

UNIX: type 'make'
Windows: use VC++ solution and project files.
Note: Define the THREADS compilation symbol to use parallel hashing
with pthreads.

Commands:

1. graph_hash - create graph and hash.

<pre>
Usage:
    Create graph and hash:
        -numVertices &lt;number of vertices&gt;
        -numEdges &lt;number of edges&gt;
        [-labelVertices &lt;none (default) | unique | random&gt;]
        [-labelEdges &lt;none (default) | unique | random&gt;]
        [-directed (directed graph)]
        [-structureRandomSeed &lt;graph structure random seed&gt;]
        [-labelRandomSeed &lt;label random seed&gt;]
        [-save &lt;graph save file&gt;]
        [-verbose]
        [-numThreads &lt;number of threads (default=1)&gt;]
    Load graph and create hash:
        [-load &lt;graph load file&gt;]
        [-verbose]
        [-numThreads &lt;number of threads (default=1)&gt;]
</pre>

Notes: 

See graphHashDriver.cpp as example of how to create a graph.

2. graph_isomorph_tester - graph isomorphism tests.

<pre>
Usage:
    Generate graphs:
            -tests &lt;number of graph tests&gt;
            -numVertices &lt;number of vertices&gt;
            -numEdges &lt;number of edges&gt;
            [-directed (directed graph)]
            [-structureRandomSeed &lt;graph structure random seed&gt;]
            [-isomorphic (generate isomorphic graphs)]
            [-numThreads &lt;number of threads (default=1)&gt;]
    Load graphs:
            -load1 &lt;graph1 load file&gt; -load2 &lt;graph2 load file&gt;
            [-numThreads &lt;number of threads (default=1)&gt;]
</pre>

3. graph_hash_special_tester - special test cases.

<pre>
Usage:
        graphHashBug1Tester "graph1" | "graph2"
|       graphHashBug2Tester "graph1" | "graph2"
|       graphHashRegularGraphTester
|       graphHashCaseTester
|       graph_ge &lt;random seed&gt; &lt;number of vertices&gt; &lt;vertex degree&gt;
</pre>