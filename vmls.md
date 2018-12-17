# Introduction to Applied Linear Algebra: Vectors, Matrices, and Least Squares

Stephen Boyd, Lieven Vandenberghe

## Vectors

### Basic

- A vector is an ordered list of numbers
- numbers in the list are the elements (entries, coefficients, components) 
- numbers are called scalars 
- the stacked vector or concatenation (of b, c, and d) is also called a block vector
- a unit vector has one entry 1 and all others 0 
- 2-vector (x1,x2) can represent a location or a displacement in 2-D
- inner prodcuct is a scalar, other notation used: ⟨a, b⟩, ⟨a|b⟩, (a, b), a · b 

### Flops

- computers store (real) numbers in floating-point format 
- basic arithmetic operations (addition, multiplication, . . . ) are called floating point operations or flops 
- x + y needs n additions, so: n flops 
- xT y (inner product)needs n multiplications, n − 1 additions so: 2n − 1 flops, we simplify this to 2n (or even n) flops for xT y and much less when x or y is sparse

### Linear functions

- f satisfies the superposition property if f (αx + βy) = αf (x) + βf (y) holds for all numbers α, β, and all n-vectors x, y

- a function that satisfies superposition is called linear 

- with a an n-vector, the function f (x) = aT x = a1x1 + a2x2 + · · · + anxn 

  is the inner product function, the inner product function is linear

- all linear functions are inner products, it can be expressed as f(x) = aT x

  f(x) = f(x1e1 +x2e2 +···+xnen) = x1f(e1)+x2f(e2)+···+xnf(en)

### Affine functions

- a function that is linear plus a constant is called affine, the general form is f(x) = aT x + b, similar with linear functions, f (αx + βy) = αf (x) + βf (y) for all numbers α, β, **but α + β = 1**, it can be interpret in 2D, the linear functions must pass through (0, 0), the affine functions can not.

### First-order Taylor approximation

- fˆ ( x ) = f ( z ) + ∇ f ( z ) T ( x − z ), fˆ is an affine function of  x, and fˆ ( x )  is very close to f(x) when xi are all near zi

### Regression model

- regression model is (the affine function of x) yˆ = x T β + v 

### Norm and distance

- Euclidean norm (or just norm) of an n-vector x is ||x|| = sqrt(xT x)
- it used to measure the size of a vector
- it have some propreties, such as homogeneity, triangle inequality, nonnegativity, definiteness

### RMS value

- root-mean-square value (RMS value) is sqrt((x1^2 + .. + xn^2)/n), used to compare sizes of vectors of different lengths
- 







