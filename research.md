# Number of edges of higher-dimensional cubes
this document demonstrates the formula for the number of edges to be **N<sub>edges</sub> = n<sub>dim</sub> * 2^(n<sub>dim</sub> -1)**

http://www.math.brown.edu/~banchoff/Beyond3d/chapter4/section05.html


# Total number of lines between any 2 points in a hypercube is
**N<sub>lines</sub> = 2<sup>n<sub>dim</sub>-1</sup> * (2<sup>n<sub>dim</sub></sup> - 1)**

This solution is based on the solution to the problem "in a group of N people, if they all wanted to shake hands to each other, how many handshakes would there be? -> (N* (N-1))/2"


# Number of diagonals
Since diagonals are those lines that are not the edges, this one is simple

**N<sub>diagonals</sub> = N<sub>edges</sub> - N<sub>lines</sub>**

# Iterating over the elements in n dimensional hypercube-like matrix
We have a 4 dymensional matrix, with a numpy-like shape (4,4,4,4)
We start from a point on this hypercube, say at coordinates (0,0,0,0).
A diagonal must consist of 4 points in this case, [(x1,y1,z1,t1), (x2,y2,z2,t2)...]. These points represent the coordinates on the corresponding axes.

A diagonal is a sequence of 4 points where each consecutive point after the first one is determined by applying the same rule to the previous point. The rule will consist of **n<sub>dim</sub>** transformations of this form, **w<sub>n</sub> = w<sub>n-1</sub> + k** where **k** is either +1, 0 or -1, and **w** refers to any of the dimensions. Additionally, on a diagonal, at least 2 of the coordinates x, y, z, .... must change. If only one of the coordinates changes, that transformation represents an edge, and not a diagonal.

Example: 
1. in 3 dimensions, these are a few rules that generate diagonals
(+1, +1, 0), (+1, 0, +1), (+1, +1, +1). Applying these transformations will generate the coordinates of the next point of the diagonal.

2. in 2 dimensions, the main diagonal follows the rules (+1, +1) or (-1, -1), and the antidiagonal can be described by both (+1, -1) or (-1, +1), depending on the point of departure.
In more detail, if the 2d matrix is made up of these points: (1,1), (1,2), (2,1), (2,2), and we start from the point (1,1), we can apply the rule (+1, +1) which will result in the coordinates (2,2). The points (1, 1) and (2,2) form define the diagonal.
