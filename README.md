Download Link: https://assignmentchef.com/product/solved-csc3102-homework2-basic-graph-algorithms
<br>
<h1></h1>

<ul>

 <li>Augmenting a Weighted Digraph ADT</li>

 <li>Using Graph Traversal Algorithms</li>

 <li>Implementing a Shortest Path Algorithm</li>

 <li>Creating the Complement of a Graph</li>

 <li>Generating a {−1<em>,</em>0<em>,</em>1} Incidence Matrix</li>

</ul>

There are many problems in computer science that can be modeled using graphs. This project involves the augmentation of an adjacency list implementation of a weighted digraph ADT and the completion of a menu-driven application that uses the ADT. The project involves writing both ADT and client functions (methods) to perform various tasks. Some of the functions (methods) have already been written for you; so you will simply have to properly call them. You will implement other functions (methods). After this project, menu options 1-4 should work. A simplifying assumption is that the weights on the edges are non-negative real numbers.

The program will have the following text-based user interface:

<h2>BASIC WEIGHTED GRAPH APPLICATION =============================================</h2>

<ul>

 <li>Incidence Matrix of G</li>

 <li>Floyd’s Shortest Round Trip in G</li>

 <li>Postorder DFS Traversal of G Complement</li>

 <li>BFS Traversal of G Complement</li>

 <li>Check whether G is Bipartite [6] Topological Ordering of V(G)</li>

</ul>

[7] Prim’s Minimum Spanning Tree in G

<h2>[0] Quit =============================================</h2>

<strong>Definition 1. </strong>The <strong>complement </strong>or <strong>inverse </strong>of a digraph <em>D</em>, denoted <em>D</em>¯, is a digraph on the same set of vertices such that if (<em>u,v</em>) ∈<em>/ E</em>(<em>D</em>) then (<em>u,v</em>) ∈ <em>E</em>(<em>D</em>), vice versa.

<strong>Definition 2. </strong>The <strong>incidence </strong>of a digraph is a {−1<em>,</em>0<em>,</em>1}-matrix which has a row for each vertex and column for each edge, and (<em>u,e</em>) = 1 if <em>e </em>is an out-directed edge from <em>u </em>and (<em>v,e</em>) = −1 if <em>e </em>is an in-directed edge that is incident with <em>v </em>and all other entries in the column label <em>e </em>is 0,

When option 1 is selected, your application should generate the incidence {−1<em>,</em>0<em>,</em>1}-matrix of the input digraph and display the number of edges in both the digraph and its complement. This option will require your completion of the <em>isEdge </em>and countEdges member functions (methods) and nonmember <em>complement </em>functions (methods). Once you implement <em>isPath </em>member function (method) and <em>floyd </em>non-member function (method), you will be able to execute the second menu option. Both traversal functions (methods) have already been implemented for you. To get options 3 and 4 of the user interface to work properly, you will need to invoke them correctly in your application using the complement of the the input digraph and appropriate lambda functions. The executable file is <strong>GraphDemo</strong>. The input weighted digraph file will be a variation on the DIMACS network flow format described below. DIMACS is the Center for Discrete Mathematics and Theoretical Computer Science based at Rutgers University.

<ul>

 <li>Comment lines give human-readable information about the file and are ignored by programs. Comment lines can appear anywhere in the file. Each comment line begins with a lower-case character <strong>c</strong>.</li>

</ul>

c This is an example of a comment line.

<ul>

 <li><strong>Problem line. </strong>There is one problem line per input file. The problem line must appear before any node or edge descriptor lines.</li>

</ul>

<h2>p NODES EDGES</h2>

The lower-case character p signifies that this is the problem line. The NODES field contains an integer value specifying |<em>V </em>|, the number of vertices in the graph. The EDGES field contains an integer value specifying |<em>E</em>|, the number of edges in the graph.

<ul>

 <li><strong>Node Descriptors. </strong>All node descriptor lines must appear before all edge descriptor lines.</li>

</ul>

<h2>n ID LABEL</h2>

The lower-case character n signifies that this is a node descriptor line. The field gives a node identification number, an integer between 1 and |. The LABEL field gives a string which serves as an alternate label for the vertex.

<ul>

 <li><strong>EDGE Descriptors. </strong>There is one edge descriptor line for each edge in the graph. The edge descriptor line will be formatted as:</li>

</ul>

<h2>e SRC DST WEIGHT</h2>

The lower-case character <strong>e </strong>signifies that this is an edge descriptor line. For a directed edge (<em>v,w</em>), the SRC field gives the identification number for the source vertex <em>v</em>, and the DST field gives the destination vertex <em>w</em>. For an undirected edge, (<em>v,w</em>) and (<em>w,v</em>) refer to the same edge so only one edge descriptor line appears and on that line the end points of the edge are written in lexicographical order. Identification numbers are integers between 1 and |<em>V </em>|. The WEIGHT field contains <em>cost</em>(<em>v,w</em>).

The input file name is entered as a command line argument. For example, to run your application on a graph file called cities1.wdg, enter <em>cities1.wdg </em>as a command line argument. The assumption is that file is in DIMACS format so no validation is done on the input file. The <em>readGraph </em>function (method) has already been implemented for you and it reads the input file and creates a <em>Graph </em>instance. The files <em>cities1.wdg </em>and <em>cities2.wdg </em>are weighted digraphs.

Any digraph file may be used to test menu optio