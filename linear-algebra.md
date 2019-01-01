# Linear algebra

### MIT Lesson 1

The key of linear algebra is to solve the equation Ax=b. We can view the equation from three perspectives.

- Matrix. Ax = b, it's a systemic way to tackle the problem.
- Row picture. just like 2x + y = 1, -x + 3y = 2, it seems to find a point solving the above equations both, but it is hard to find a solution and also difficult to visualize when the dimension is large.
- Col picture. it's a good idea to regard Ax=b as a combination with the cols of matrix A. So when a matrix left-times a vector x, it means to combine the cols of A using the elements of x. As a result, the cols and rows of a matrix seem to be unequal, have different meaning at less.

When A is inverted, non-singular, it means the cols of A can fill the whole space, in other words, each col contributes something new, independent with the other cols.

So the key idea is to find out the properties of the matrix A, when the space can be filled, when can not, shall we find a normal solution or a metric to tackle the problem.

### MIT Lesson 2

To solve the equation Ax = b, Gauss came up with a method named elimination and back-subsitution. It's a very simple idea.

The goal is to transform A to an upper triangle matrix U. The method is to operate rows and use pivot to elimine the elements below pivot. And the pivots will always locate in the diagonal, so the final matrix will be an upper triangle matrix. Finally, when we get the matrix U, we can also do the same operations on the right-hand b to form c. Actually, we can operate A and b meanwhile, it's known with augmented matrix. We can do back subsitution with U and c. To solve the last equation and the second last, and recursively untill the first equation.

All the operations above are on rows. We want to know how to operate with matrix to get U from A. The previous lesson has shown if you want to do some operations on cols, you must right-times a vector in col. The same with cols, if you want to do some operations on rows, you must left-times a vector in raw. In other words, a row times a matrix make a row, a matrix times a col make a col. So if we define the operation that elimine the element on (1, 2) a matrix E\_(12), then E\_(12)A will elimine the element. As a result, the elimination process actually is some matrixs left-times A to elemine the elements. We want to find a matrix which can do the same thing with the product of the all E matrixs. And this idea is the key of the inverse matrix.