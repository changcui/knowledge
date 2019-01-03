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

### MIT Lesson 3

Firstly, we introduce how to do matrixe multiply. 

- If we conduct AB = C, we can view in the elements picture, it's easy. The element (3, 4) in C will be the product of the 3 row of A and the 4 col of B.
- If we view the product in the col picture, then each col of C is the combination of the cols of A, the coeffcient of the combination is the col of B.
- If we view the product in the row picture, then each row of C is the combination of the rows of B, the coeffcient of the combination is the row of A.
- If we view the product with the multiply with the cols of A and the rows of B, then each col of A multiply the corresponding row of B produce a matrix the same of C. And add up the all matrix will get C, too. So it's an wonderful perspective in which we can factor the product with the cols of A and the rows of B. However, if the row of A product the col of B will just produce an element which is the first way.
- If we view the product in the block way, we can factor the matrix A and B with A(1, 1) A(1,2).. B(1, 1) B(1, 2) then the C(1, 1) will be the sum of the product of A(1, 1) B(1,1) and the product of A(1, 2) B(2, 1), it's familiar with the first way.

Then, we can talk about the inverse matrix. The most important questions about inverse are when the matrix is invertible and how to find the inverst matrix when invertible.

- As to the former, a simple idea is when you can find a vector x not 0 which Ax = 0, A is not invertible. Because, if the inverse matrix exists, then A-1 A x = 0, x must be 0.
- As to the latter, Gauss-Jordan came up with a systemic solution. We can concat A and I to make a longer matrix namely augment matrix which may look like [A I]. Then we conduct some row operations to make A be I, finally A will be A-1. The insight is that when we conduct row operations, actually equal a matrix left-times the augment matrix. So the procedure may be E1 E2 En [A I] = [I X], we have shown the product of matrix can be divided to block, so the product can be done to A and I meanwhile. We regard all the E matrix as one matrix E, then E [A I] = [I X],  EA = I, X = E, so E = A-1 = X. The most important point to understand this procedure is row operations equal matrixs left-times A. 

### MIT Lesson 4

Matrix factorization is very important to find the inherent property of matrix. And the basic factorization is LU factorization. The L refers to a lower triangle matrix and the U refers to an upper triangle matrix. LU factorization can be viewed as the matrix form of Gauss-Jordon methon.

- Firstly, we conduct the eliminations to get the upper triangle matrix U as usual. As we process, we get one elimination matrix E each move. So it may look like E1 E2 E3 ... En A = U, and each elimination matrix will be a lower triangle matrix because we always do elimination with the lower rows and current row.
- Secondly, we left-times the inverse matrix of every elimination matrix E, it will look like A = En-1... E2-1 E1-1U. And the inverse of elimination matrix will be lower triangle matrix, too. The diffenrence betwenn them is just the sign of the element which not 1 or 0. So it's easy to get the inverse.
- Finally, we multiply all of the inverse matrix to get L. The final view will be A = LU.

Some notation: 

- The reason to get L not using the original elimination matrix is that the product of all elimination matrix has a worse form than its inverse. It will make some new elements which we don't want to see. However, its inverse matrix just make up with the elemens of the inverse of elimination matrix in the same position.
- The above method is based on no row exchange. That means every pivot lies on the right row. If not, we should add a permutation matrix namely P, then the final form will be A = PLU.
- The operation counts will be about one third n cubed. In the left-hand of the equation Ax=b, the factorization of A will cost  n^2 + (n-1)^2 + ...+ 1^2, in which every element in the expression is the elemination cost. In the right-hand, it will be n + (n-1) + ... + 1. The final result will be roughly 1/3 n^3.
- The lesson hasn't introduced why we should do factorization of matrix. Just follow the matrix inverse lesson, it may look like ending the elemination of matrix with LU factorization which is the matrix form of Gauss-Jordan methon.