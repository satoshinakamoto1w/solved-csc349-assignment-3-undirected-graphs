Download Link: https://assignmentchef.com/product/solved-csc349-assignment-3-undirected-graphs
<br>
Graphs allow us to mathematically and computationally model and explore the relationships that occur in real world situations. One possible relationship that we might be interested in is some form of conflict between two entities. For example, vertices could represent university classes, where two vertices are connected by an edge if those classes’ times overlap.

<strong>Deliverables:</strong>

<strong>GitHub Classroom: </strong><a href="https://classroom.github.com/a/TbnVCgQo">https://classroom.github.com/a/TbnVCgQo</a>

<strong>Required Files:                    </strong>compile.sh, run.sh

<strong>Optional Files:                           </strong>*.py, *.java, *.clj, *.kt, *.js, *.sh

<h1>Part 1: Graph Colorings</h1>

A <em>vertex coloring </em>is an assignment of colors, one color to each vertex, such that no two adjacent vertices have the same color. If a graph can be colored using <em><sub>k </sub></em>colors, it is said to be <em><sub>k</sub>-colorable</em>. In the situation described above, where edges connect classes with conflicting times, a coloring could represent classroom assignments such that no two classes are in the same classroom at the same time. For example:

The above graph can be colored using two colors, and it is said to be <sub>2</sub>-colorable. For this special case of <em>k</em><sub>=2</sub>, the <sub>2</sub>-colorability of a graph can be computed in linear time (for <em><sub>k</sub></em><sub>≥3</sub>, finding valid colorings generally becomes very difficult).

In your programming language of choice per Assignment 1, implement an algorithm to determine whether or not a given graph is <sub>2</sub>-colorable. To help you get started, note the following observations:

<ul>

 <li>In order to establish the <sub>2</sub>-colorability of a graph, every vertex must be assigned exactly one color.</li>

 <li>Thus, every vertex should be explored exactly once by the coloring algorithm.</li>

 <li>The choice of cyan and magenta in the example above was entirely arbitrary; any two colors would do.</li>

 <li>Moreover, the choice of <em>which </em>group of vertices was colored cyan was also arbitrary: the assigned colors could be swapped, and the coloring would remain valid.</li>

 <li>The colors assigned within one component cannot affect the colors assigned within any other component. However, if any one component is not <sub>2</sub>-colorable, the entire graph is not <sub>2</sub>-colorable.</li>

</ul>

Each input graph will be provided as an <em>edge list</em>: each edge in the graph will be represented by a commaseparated pair of vertex identifiers, indicating an edge from the first vertex to the second.

You may assume that vertex identifiers are contiguous natural numbers — they begin at <sub>0</sub>, and there will be no “gaps” in the identifiers used. You may also assume that the graph will be simple and will not contain any isolated vertices.

1 of 2

CSC 349: Design and Analysis of Algorithms Fall 2019

For example, the above graph could be represented as:

0, 1 1, <a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>

2, 3 3, 0 4, 5




Your program must accept as a command line argument the name of a file containing an edge list as described above, then print to stdout the result of the attempted <sub>2</sub>-coloring according to the following format:

<ul>

 <li>Vertices assigned the same color within the same component appear on a single comma-separated line.</li>

 <li>Vertices assigned different colors appear on different lines. Vertices in different components appear on different lines, even if they are assigned the same color.</li>

 <li>Each line’s vertices must be sorted in ascending order. Note that vertex identifiers are integers, not strings. The lines themselves must be sorted in ascending order using their smallest vertex identifiers. For example:</li>

</ul>

&gt;$ ./compile.sh

&gt;$ ./run.sh in1.txt Is 2-colorable:

0, 2

1, 3

4 5

Your program will be tested using diff, so its printed output must match <em>exactly</em>.