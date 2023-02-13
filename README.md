# Assignment5
## Sriya Reddy 

For this assignment, we were required to find the inverse and the determinant of two matrices A and B. 
The given matrices were loaded using the following code:
```
> A = matrix(1:100, nrow=10)
> B = matrix(1:1000, nrow=10)
```
Viewing the matrices, we get:
```
> View(A)
> View(B)
```

![Matrix A](https://github.com/venatisriya/assignment5/blob/main/mat_A.png)


![Part of Matrix B](https://github.com/venatisriya/assignment5/blob/main/mat_B.png)

The matrices are also uploaded as .csv files in my repository here : [Matrix A](https://github.com/venatisriya/assignment5/blob/main/MatA.csv), [Matrix B](https://github.com/venatisriya/assignment5/blob/main/MatB.csv).

Matrix A is of the shape (10x10) and matrix B is of the shape (10x100)
I used the following code to find the inverse for the two matrices. 

```
> inv_A = solve(A)
> inv_B = solve(B)
```
But this produced the following errors.
```
Error in solve.default(A) : 
  Lapack routine dgesv: system is exactly singular: U[6,6] = 0
```

```
Error in solve.default(B) : 'a' (10 x 100) must be square
```
This is because the matrix A is singular and the matrix B is non-square. 
To solve this issue, I used the generalized inverse function in R. The generalized inverse is develped using the pseudo inverse formulation.
To use this function, I installed the `MASS` library using the following code. 
```
> install.packages("MASS")
```
I used `> library(MASS)` to import the library, so that I can use the `ginv()` function. I used the following code:
```
inv_A = ginv(A)
inv_B = ginv(B)
```
This produced the following inverse matrices:

![Inverse of Matrix A](https://github.com/venatisriya/assignment5/blob/main/Inv_A_pic.png)


![Part of inverse of Matrix B](https://github.com/venatisriya/assignment5/blob/main/Inv_B_pic.png)

The .csv files for the inverse matrices are also uploaded to my repository: [Inverse of matrix A](https://github.com/venatisriya/assignment5/blob/main/Inv_A.csv), [Inverse of matrix B](https://github.com/venatisriya/assignment5/blob/main/Inv_B.csv).
I find that the generalized inverse provides an inverse matrix for each of the two given matrices. 

I used the following code to find the determinant of the matrices and obtained the results as shown. 
```
> det(A)
[1] 0
> det(B)
Error in determinant.matrix(x, logarithm = TRUE, ...) : 
  'x' must be a square matrix
```
The determinant of A is 0 as A is a singular matrix, while the determinant of B is not defined as B is a non-square matrix. 









