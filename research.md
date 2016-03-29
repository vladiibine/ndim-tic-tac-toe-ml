# Number of edges of higher-dimensional cubes
this document demonstrates the formula for the number of edges to be `Nedges = ndim * 2^(ndim -1)`

http://www.math.brown.edu/~banchoff/Beyond3d/chapter4/section05.html


# Total number of lines between any 2 points in a hypercube is
`Nlines = 2^(ndim-1) * (2^ndim - 1)`

This solution is based on the solution to the problem "in a group of N people, if they all wanted to shake hands to each other, how many handshakes would there be? -> (N* (N-1))/2"


# Number of diagonals
Since diagonals are those lines that are not the edges, this one is simple

`Ndiagonals = Nedges - Nlines`
