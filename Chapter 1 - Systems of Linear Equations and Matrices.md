## 1.1 - Introduction to Systems of Linear Equations
#### Examples of linear equations
- $ax + by = c$ is the equation for a line (assuming $a,\ b$ not both $0$)
- $ax + by + cz = d$ is the equation for a plane (assuming $a,\ b,\ c$ not all $0$)

#### General form of a linear equation
- $a_1x_1 + a_2x_2 + \dots + a_nx_n = b$ is the general form of a linear equation (assuming $a_1,\ a_2,\ \dots,\ a_n$ not all $0$)
- When $b = 0$ the equation is called a ***homogeneous linear equation***
#### Systems of linear equations
- A finite set of linear equations is called a ***system of linear equations*** or just a ***linear system***

- A general linear system of $m$ equations in the $n$ unknowns $x_1,\ \dots,\ x_n$ can be written as
	$$
	\begin{matrix}
	a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n = b_1 \\
	a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n = b_2 \\
	\vdots \\
	a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n = b_m \\
	\end{matrix}
	$$
- A ***solution*** to a linear system in $n$ unknowns is a sequence of $n$ numbers $s_1,\ \dots,\ s_n$ for which the substitution
	$$
	x_1 = s_1,\ \dots,\ x_n = s_n
	$$
	Makes each equation a true statement.

	Solutions can be written as an ordered $n$-tuple, $(s_1,\ \dots,\ s_n)$ which allows them to be interpreted geometrically as points in $n$-dimensional space

- A linear system is ***consistent*** if it has at least one solution and ***inconsistent*** otherwise.
- Every linear system has either $0$, $1$ or infinitely many solutions. For example, a system in $2$ unknowns represents two lines and that system's solutions represent all the points in 2D space which lie on both of those lines. The only three possibilities are
	1. The lines intersect at a single point $(x, y)$.
	2. All the points on a line are points of intersection with the other as the two lines are equal.
	3. The lines do not intersect at any point.

	The possible numbers of solutions correspond to the above possibilities by 1 meaning there is only a single solution. 2 meaning there are infinitely many solutions and 3 meaning there are no solutions.

- The solutions to systems with a single solution are simply expressed as their tuples or via listing the values of each unknown.
- Systems with no solutions have none to list.

- The infinitely many solutions to some systems can be expressed via parametric equations, as shown below.

	Taking the linear system
$$
\begin{matrix}
4x - 2y = 1 \\
16x - 8y = 4
\end{matrix}
$$
	as an example, it is solved via multiplying the first equation by $-4$ and adding that to the second equation. The result is as follows.
	$$
	\begin{matrix}
	4x - 2y = 1 \\
	0 = 0
	\end{matrix}
	$$
	Recall that the solution to a system of linear equations is the set of values for each unknown which make the equations in the system true statements. The statement $0 = 0$ is a true statement for all values of $x$ and $y$ so it can be omitted, the result is just $4x - 2y = 1$. There is not enough information to obtain a definite value for $x$ or $y$; from both $x = \frac{1 + 2y}4$ and $y = \frac{1 - 4x}{-2}$ it's clear that there are solutions for $x$ for every possible value of $y$. The same is true for solutions to $y$ and possible values of $x$. Either of these equations describe the solution set, the fact that the set is described via two dependent variables with one having an arbitrary value is emphasised through a parametric equation:
\
	The form $x = \frac{1 + 2y}{4}$ is chosen arbitrarily over $y = \frac{1 - 4x}{-2}$ and the solution set is described as the parametric equation below.
$$
\begin{matrix}x = \frac14 + \frac12t, & y = t\end{matrix}
$$
	As an example, if $t$ is chosen to equal $0$ then the solution is $(\frac14,\ 0)$. This set of parametric equations is called the ***general solution*** to the system.

#### Augmented Matrices and Elementary Row Operations

- A linear system can be expressed more succinctly as a grid of numbers, called a ***matrix***. For example, the linear system
	$$
	\begin{matrix}
	x + y + 2z = 9 \\
	2x + 4y - 3z = 1 \\
	3x + 6y - 5z = 0 \\
	\end{matrix}
	$$
	Is described by the matrix
	$$
	\begin{Bmatrix}
	1 & 1 & 2 & 9 \\
	2 & 4 & -3 & 1 \\
	3 & 6 & -5 & 0
	\end{Bmatrix}
	$$
	Where the first three columns of each row are the coefficients to $x,\ y$ and $z$, respectively, and each row of the final column are the constants on the right side of each equation. This is called the ***augmented matrix*** for the system.

- The basic method for solving a linear system is to perform algebraic operations on the system that do not alter the solution set and that produce a succession of increasingly simpler systems, until a point is reached where the consistency of the system is clear as well as its solutions. Typically, the algebraic operations are:
	1. Multiply an equation through by a nonzero constant.
	2. Interchange two equations.
	3. Add a constant times one equation to another.

- Since the rows of an augmented matrix correspond to the equations in the associated system, these three operations correspond to the following operations on the rows of the augmented matrix:
	1. Multiply a row through by a nonzero constant.
	2. Interchange two rows.
	3. Add a constant times one row to another.
	
	These are called elementary row operations on a matrix.
	- Example of using EROs
		![[la_image10.png]]
		![[la_image9.png]]

## 1.2 - Gaussian Elimination

#### Echelon Forms
The matrix in "Example of using EROs" above is in ***reduced row echelon form***. The criteria for this include:
1. If a row does not consist entirely of zeros, then the first nonzero number in the row is a $1$. This is called a ***leading 1***.
2. If there are any rows that consist entirely of zeros, then they are grouped together at the bottom of the matrix.
3. In any two successive rows that do not consist entirely of zeros, the leading $1$ in the lower row occurs further right than the leading $1$ in the higher row.

A matrix for which all three of these criteria are met is in ***row echelon form***. A matrix is in ***reduced row echelon form*** if these are met along with a fourth:

4. Each column that contains a leading $1$ has zeros everywhere else in that column.

- Matrices in reduced row echelon form are also in row echelon form but the inverse is not true.
- Every matrix has a unique reduced row echelon form.
- There are matrices with multiple row echelon forms.

#### Examples of matrices in reduced row echelon form
$$
\begin{matrix}

\begin{Bmatrix}
1 & 0 & 0 & 4 \\
0 & 1 & 0 & 7 \\
0 & 0 & 1 & -1 \\
\end{Bmatrix}
&
\begin{Bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{Bmatrix}
\end{matrix}
$$
#### Examples of matrices in row echelon form
$$
\begin{matrix}

\begin{Bmatrix}
1 & 4 & 6 & 7 \\
0 & 1 & -3 & 2 \\
0 & 0 & 1 & 5 \\
\end{Bmatrix}
&
\begin{Bmatrix}
1 & 1 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{Bmatrix}
\end{matrix}
$$
- The first matrix of the second examples is in row echelon but not reduced row echelon form because criteria $4$ is false; the second column contains a leading $1$ (the $1$ is leading in the second row) but the other elements in the column are not all $0$.

#### Elimination methods

Matrices in row and reduced row echelon form are easy to identify solutions for. Detailed below is an algorithm for transforming a matrix to either echelon form.
- Algorithm
		![[la_image8.png]]
		![[la_image6.png]]

- The algorithm detailed above for transforming a matrix into row echelon form is called ***Gaussian elimination***.
- The same algorithm with the added step to bring it to reduced row echelon form is called **Gauss-Jordan elimination.***

#### Homogeneous linear systems

- A linear system is called homogeneous if all its equations are homogeneous.

- Every homogeneous system is consistent because there is guaranteed to be at least one solution, the solution with all unknowns equaling $0$. This solution is called the ***trivial solution***. If other solutions exist where the unknowns are not all $0$ these are called ***non-trivial solutions***

- If a homogeneous system has more unknowns than equations it is guaranteed to have ***non-trivial*** solutions. Below is an example of the augmented matrix, brought to reduced row echelon form, for a homogenous system formed from 3 equations in 4 unknows.
$$
\begin{Bmatrix}
1 & 0 & 0 & 0 & 5 \\
0 & 1 & 0 & 0 & 6 \\
0 & 0 & 1 & 0 & 7 \\
0 & 0 & 0 & 0 & 0
\end{Bmatrix}
$$
	This expresses the four unknowns as:$$
	\begin{matrix}
	1x_1 = 5 & 1x_2 = 6 & 1x_3 = 7 & 0x_4 = 0
	\end{matrix}
	$$It is clear to see the values of $x_1,\ x_2$ and $x_3$ but $0x_4 = 0$ is true for any number and thus $4$ cannot be ascertained. Any augmented matrix for a system constructed from $m < n$ equations in $n$ unknowns will include a row of all $0$s, neither elimination method will change this since the only way to do so is to add a row, times a constant, to the zero row; however, this is not useful. Therefore, the matrix in reduced row echelon form also contains those rows of all zeros and there is not enough information to define all the unknowns.

#### Back-substitution
- A linear system can be solved via Gaussian elimination alone:
	If$$
	\begin{Bmatrix}
		1 & 4 & 6 & 7 \\
		0 & 1 & -3 & 2 \\
		0 & 0 & 1 & 5 \\
	\end{Bmatrix}
	$$is the row echelon form augmented matrix for a linear system then it represents this system:
	$$
	\begin{matrix}
	x_1 + 4x_2 + 6x_3 = 7 \\
	x_2 + -3x_3 = 2 \\
	x_3 = 5 \\
	\end{matrix}
	$$
	Which simplifies to
	$$
	\begin{matrix}
	x_1 = 7 - 4x_2 - 6x_3  \\
	x_2 = 2 + 3x_3 \\
	x_3 = 5 \\
	\end{matrix}
	$$
	Substituting the value of each unknown where it's referenced in the equation above it, starting at the bottom:
	$$
	\begin{matrix}
	x_1 = 7 - 4(2 + 3(5)) - 6(5) \\
	x_2 = 2 + 3(5) \\
	x_3 = 5 \\
	\end{matrix}
	$$
	This gives the solution to the system, $(-91,\ 17,\ 5)$

- If a system has infinite solutions then a parametric equation can be arrived at in the same manner:
	If$$
	\begin{Bmatrix}
1 & 3 & -2 & 0 & 2 & 0 & 0 \\
0 & 0 & 1 & 2 & 0 & 3 & 1 \\
0 & 0 & 0 & 0 & 0 & 1 & \frac13 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 \\
	\end{Bmatrix}
	$$
	is the row echelon form augmented matrix for a linear system then it represents this system$$
	\begin{matrix}
	x_1 + 3x_2 + -2x_3 + 2x_5 = 0 \\
	x_3 + 2x_4 + 3x_6 = 1 \\
	x_6 = \frac13
	\end{matrix}
	$$Which simplifies to$$
	\begin{matrix}
	x_1 = -3x_2 + 2x_3 - 2x_5 \\
	x_3 = 1 - 2x_4 - 3x_6 \\
	x_6 = \frac13
	\end{matrix}
	$$
	And, by back-substitution:$$\begin{matrix}
	x_1 = -3x_2 + 2(1 - 2x_4 - 3(\frac13)) - 2x_5 \\
	x_3 = 1 - 2x_4 - 3(\frac13) \\
	x_6 = \frac13
	\end{matrix}$$
	Which simplifies to$$\begin{matrix}
	x_1 = -3x_2 + 4x_4 - 2x_5 \\
	x_3 = 2x_4 \\
	x_6 = \frac13
	\end{matrix}$$
	Which is expressed in parametric form as$$\begin{matrix}
	x_1 = -3r + 4s - 2t \\
	x_3 = 2s \\
	x_6 = \frac13
	\end{matrix}$$
	The solutions are$$
	\begin{matrix}
	x_1 = -3r - 4s - 2t, & x_2 = r, & x_3 = -2s, & x_4 = s, & x_5 = t, & x_6 = \frac13
	\end{matrix}
	$$
#### Pivot positions and columns
- Although row echelon forms are not unique, the reduced row echelon form and all row echelon forms of a matrix $A$ have the same number of zero rows and the leading $1$s always occur in the same positions. Those are called the pivot positions of $A$. The columns containing the leading $1$s in a row echelon or reduced row echelon form of $A$ are called the pivot columns of $A$, and the rows containing the leading $1$s are called the pivot rows of $A$. A nonzero entry in a pivot position of $A$ is called a pivot of $A$.

	For example, if the row echelon form of a matrix $A$ is$$
	\begin{Bmatrix}
	0 & 0 & -1 & 0 & 7 & 12 \\
	2 & 4 & -10 & 6 & 12 & 28 \\
	2 & 4 & -5 & 6 & -5 & -1
	\end{Bmatrix}$$
	$$
	\begin{Bmatrix}
	1 & 2 & -5 & 3 & 6 & 14 \\
	0 & 0 & 1 & 0 & -\frac72 & -6 \\
	0 & 0 & 0 & 0 & 1 & 2
	\end{Bmatrix}$$
	Then the pivot positions are $A_{11}$, $A_{23}$, $A_{35}$. The pivot rows are $1$, $2$ and $3$. The pivot columns are   $1$, $3$ and $5$. The pivots are the nonzero numbers at the pivot positions $-10$ and $-5$.

## 1.3 - Matrices and Matrix Operations

- A matrix with $n$ rows and $n$ columns is called a ***square matrix of order $n$***.
- The entries of a square matrix $a_{11}, a_{22}, ..., a_{nn}$ is called its ***main diagonal***.
- Matrix multiplication as linear combinations
	$$
	\begin{matrix}
	
	\begin{Bmatrix}
	a_{11} & a_{12} & ... & a_{1n} \\
	a_{21} & a_{22} & ... & a_{2n} \\
	\vdots & \vdots & \ddots & \vdots \\
	a_{m1} & a_{m2} & ... & a_{mn} \\
	\end{Bmatrix}

	\begin{bmatrix}
	x_1 \\ x_2 \\ \vdots \\ x_n
	\end{bmatrix}

	= \begin{Bmatrix}
	a_{11}x_1 & a_{12}x_2 & ... & a_{1n}x_n \\
	a_{21}x_1 & a_{22}x_2 & ... & a_{2n}x_n \\
	\vdots & \vdots & \ddots & \vdots \\
	a_{m1}x_1 & a_{m2}x_2 & ... & a_{mn}x_n \\
	\end{Bmatrix}

	\\\\

	= x_1 \begin{bmatrix}
	a_{11} \\ a_{21} \\ \vdots \\ a_{m1}
	\end{bmatrix}
	+ x_2 \begin{bmatrix}
	a_{12} \\ a_{22} \\ \vdots \\ a_{m2}
	\end{bmatrix}
	+ \dots + x_n \begin{bmatrix}
	a_{1n} \\ a_{2n} \\ \vdots \\ a_{mn}
	\end{bmatrix}

	\end{matrix}
	$$
	*"If $A$ is an $m \times n$ matrix and $x$ is an $n \times 1$ column vector then the product $Ax$ can be expressed as a linear combination of the column vectors of $A$ in which the coefficients are the entries of $x$"*

- There are a few different ways to express a matrix product (all with the same result matrix) detailed in the document below.
- PDF
  ![[F13_341_book_sec_6-2.pdf]]

- The transpose $A^T$ of a matrix $A$ is $A$ with its rows and columns swapped, that is, $(A^T)_{ij} = A_{ji}$.
- The trace $tr(A)$ of a matrix $A$ is the sum of the entries along its main diagonal. $tr(A)$ is undefined unless $A$ is a square matrix.

## 1.4 - Inverses; Algebraic Properties of Matrices

- Basic algebraic properties of matrix operations:
	$$
	\begin{matrix}
	(a) & A + B = B + A \\
	(b) & A + (B + C) = (A + B) + C \\
	(c) & A(BC) = (AB)C \\
	(d) & A(B + C) = AB + AC \\
	(e) & a(B + C) = aB + aC \\
	(f) & (a + b)C = aC + bC \\
	(g) & a(bC) = (ab)C \\
	(h) & a(BC) = (aB)C = (B)aC
	\end{matrix}
	$$
- It is not generally true that $AB = BA$; however, it is true in some cases and in those cases $A$ and $B$ are said to ***commute***.
- For arithmetic in $n \times n$ (square) matrices there are zero and identity matrices like 1 and 0 in real arithmetic:
		$$
		\begin{Bmatrix}
		1 & 0 & 0 \\
		0 & 1 & 0 \\
		0 & 0 & 1
		\end{Bmatrix}
		\begin{Bmatrix}
		a & d & g \\
		b & e & h \\
		c & f & i
		\end{Bmatrix} =
		\begin{Bmatrix}
		a & d & g \\
		b & e & h \\
		c & f & i
		\end{Bmatrix}
		$$
		$$
		\begin{Bmatrix}
		0 & 0 & 0 \\
		0 & 0 & 0 \\
		0 & 0 & 0
		\end{Bmatrix}
		\begin{Bmatrix}
		a & d & g \\
		b & e & h \\
		c & f & i
		\end{Bmatrix} =
		\begin{Bmatrix}
		0 & 0 & 0 \\
		0 & 0 & 0 \\
		0 & 0 & 0
		\end{Bmatrix}
		$$
- Zero matrices are denoted **0**.
- The identity matrix is denoted $I$.
- All matrices commute with the zero and identity matrices.

- The ***inverse*** of a matrix $A^{-1}$ has the property, $AA^{-1} = I$. Not all matrices have inverses, ones which do are called invertible. Matrices without inverses are called ***singular***. If $AA^{-1} = I$ then $A$ is invertible, $A^{-1}$ is the inverse of $A$ and $A$ is the inverse of $A^{-1}$.

- A square matrix with a row or column of zeros is singular.
	Let
		$$
		A = \begin{Bmatrix}
		a & d & 0 \\
		b & e & 0 \\
		c & f & 0 \\
		\end{Bmatrix}
		$$
	Iff $A$ is singular then there is no matrix $B$ such that $AB = BA = I$.

	Let $c_1, c_2, 0$ be the column vectors of $A$. $BA = B[c_1\ \ c_2\ \ 0] = [Bc_1\ \ Bc_2\ \ B0]$. This result has a column of zeros so $BA \neq I$.

- Matrices have unique inverses.
		Suppose $B$ and $C$ are inverses of $A$.$$
		\begin{matrix}
		BA = I \\
		(BA)C = IC \\
		B(AC) = B = C
		\end{matrix}
		$$
		$B$ and $C$ are equal and thus $A$ has only one inverse.

- Calculating inverses of $2 \times 2$ matrices
	The inverse of a $2 \times 2$ matrix $A = \begin{bmatrix}a & b \\ c & d\end{bmatrix}$ is given by the formula:
	$$A^{-1} = \frac1{ad - bc}\begin{bmatrix}d & -b \\ -c & a\end{bmatrix}$$
	The quantity $ad - bc$ is called the ***determinant*** of $A$ and is denoted $det(A)$. Iff $det(A) = 0$ then $A$ is singular.

- If $A$ and $B$ are invertible matrices of the same size, then $AB$ is invertible and $(AB)^{-1} = B^{-1}A^{-1}$. The reverse is also true (see book for proof)
	$(AB)(B^{-1}A^{-1}) = A(BB^{-1})A^{-1} = AIA^{-1} = AA^{-1} = I$.

- Powers of a matrix
	If $A$ is a square matrix, then $A^n = AA \dots A\ [n\ factors]$ where $n$ is a positive integer.
	If $A$ is invertible then for powers of negative integers, $A^n = A^{-1}A^{-1} \dots A^{-1}\ [n\ factors]$.
	From these definitions many of the same laws from elementary algebra can be derived, for example $A^{a + b} = A^aA^b$,    $A^{a - b} = A^aA^{-b}$,    $A^0 = I$ and so on.

- Matrix polynomials
	Polynomials in matrices instead of the usual real numbers are called ***matrix polynomials***.

	If $p(x) = a_0 + a_1x + a_2x^2 + \dots + a_mx^m$ then $p(A) = a_0I + a_1A + a_2A^2 + \dots + a_mA^m$ is a matrix polynomial in $A$.

- Powers of square matrices commute
	$A^rA^s = A^{r + s} = A^{s + r} = A^sA^r$
	It follows from this (find out how) that $p_1(A)p_2(A) = p_2(A)p_1(A)$.

## Properties of the Transpose

- Main properties of the transpose
	$$
	\begin{matrix}
	(a) & (A^T)^T = A \\
	(b) & (A + B)^T = A^T + B^T \\
	(c) & (A - B)^T = A^T - B^T \\
	(d) & (kA)^T = kA^T \\
	(e) & (AB)^T = B^TA^T
	\end{matrix}
	$$

- If $A$ is an invertible matrix, then $A^T$ is also invertible and $(A^T)^{-1} = (A^{-1})^T$
	$A^T(A^{-1})^T = (A^{-1}A)^T = I^T = T$
	$(A^{-1})^TA^T = (AA^{-1})^T = I^T = I$

## 1.5 - Elementary Matrices and a Method for Finding $A^{-1}$

The elementary row operations on a matrix are:
1. Multiply a row by a nonzero constant $c$.
2. Interchange two rows.
3. Add a constant $c$ times one row $r_1$ to another $r_2$

These operations have the inverses:
1. Multiply a row by $1/c$.
2. Interchange the same two rows.
3. Add $-c$ times $r_1$ to $r_2$.

- An ***elementary matrix*** is a matrix which can be constructed through elementary row operations on an identity matrix.

- Multiplication by an elementary matrix constructed through a series of EROs $S$, for example $EA$ (note multiplication on the left) is the matrix which results from $S$ being applied to $A$. For example, $EA$ is $A$ with its first and last rows swapped if $E$ encodes that operation.

- The inverse of an elementary matrix $E$ encodes the inverse of the operation encoded by $E$. Consequently, if a matrix can be expressed as $A = E_1 \dots E_nI$ then $I = E_1^{-1} \dots E_n^{-1}A$ so $A$ can be transformed to $I$ via elementary row operations.

- All elementary matrices are invertible and their inverses are also elementary matrices.
	$E = EI \implies E^{-1}E = I$. $E^{-1}$ exists because it just encodes the inverses of the operations encoded in $E$. $E^{-1}$ is an elementary matrix for the same reason.

- Matrices $A$ and $B$ are said to be ***row equivalent*** if either is expressible as the other multiplied by a product of elementary matrices, e.g. if $A = E_1 \dots E_nB$ or $B = E_1 \dots E_nA$.

- Equivalent statements about $n \times n$ square matrices (see book for proofs)
	1. $A$ is invertible.
	2. $Ax = 0$ has only the trivial solution.
	3. The reduced row echelon form of $A$ is $I_n$.
	4. $A$ is expressible as a product of elementary matrices.
	5. $Ax = b$ is consistent for every $n \times 1$ matrix $b$.
	6. $Ax = b$ has exactly one solution for every $n \times 1$ matrix $b$.

- A method for finding $A^{-1}$
	By the 4th equivalent statement, if $A^{-1}$ exists then $A = (E_1 \dots E_n)I$. This implies that $(E_1 \dots E_n)^{-1}A = I$. By previous theorems $(E_1 \dots E_n)^{-1} = (E_1^{-1} \dots E_n^{-1})$.
	So $(E_1^{-1} \dots E_n^{-1})A = I$ and $A^{-1} = (E_1^{-1} \dots E_n^{-1})I$.

	Using this knowledge, $A^{-1}$ can be found by applying each inverse elementary matrix to $A$ and $I$, one by one, and the result is that $A$ has become $I$ and $I$ has become $A^{-1}$. This algorithm is detailed further in the book.

## 1.6 - More on Linear Systems and Invertible Matrices

- Proof of all linear systems having either $0$, $1$ or $\infty$ solutions.
	If $Ax = b$ is a linear system then it either has no solutions, one solution or more than one solution.

	Suppose $Ax = b$ has two solutions; $x_1$ and $x_2$. Let $x_0 = x_1 - x_2$.
	$Ax_0 = A(x_1 - x_2) = Ax_1 - Ax_2 = b - b = 0$
	Let $k$ be any scalar and consider $A(x_1 + kx_0)$.
	$A(x_1 + kx_0) = Ax_1 + A(kx_0) = Ax_1 + k(Ax_0) = b + k0 = b$
	$(x_1 + kx_0)$ is a solution to $Ax = b$ for all values of $k$, hence $Ax = b$ has infinite solutions when it has more than one solution.

- Proof of all linear systems $Ax = b$ for which $A^{-1}$ exists having one solution, $A^{-1}b$
	![[la_image0.png]]

![[la_image4.png]]
![[la_image7.png]]![[la_image5.png]]

## 1.7 - Diagonal, Triangular and Symmetric Matrices

- A square matrix in which all the entries off the main diagonal are zero is called a ***diagonal*** matrix.
- A general $n \times n$ diagonal matrix $D$ is defined as
	$$
	D = \begin{bmatrix}
	d_1 & 0 & \dots & 0 \\
	0 & d_2 & \dots & 0 \\
	\vdots & \vdots & \ddots & \vdots \\
	0 & 0 & \dots & d_n \\
	\end{bmatrix}
	$$
- A diagonal matrix is invertible if and only if all of its diagonal entries are nonzero; in the general case the inverse is
	$$D^{-1} = \begin{bmatrix}
	d_1^{-1} & 0 & \dots & 0 \\
	0 & d_2^{-1} & \dots & 0 \\
	\vdots & \vdots & \ddots & \vdots \\
	0 & 0 & \dots & d_n^{-1} \\
	\end{bmatrix}$$
	$$DD^{-1} = I$$
- Powers of diagonal matrices
	$D^k = [a_{ij}^k]$

- Triangular matrices
	- A square matrix in which all the entries above the main diagonal are zero is called ***lower triangular***.
	- A square matrix in which all the entries below the main diagonal are zero is called ***upper triangular***.
	- The transpose of a lower triangular matrix is upper triangular and the transpose of an upper triangular matrix is lower triangular.
	- The product of lower triangular matrices is lower triangular.
	- The product of upper triangular matrices is lower triangular.
	- A triangular matrix is invertible if and only if its diagonal entries are all nonzero.
		- The inverse of an invertible lower triangular matrix is lower triangular and the inverse of an invertible upper triangular matrix is upper triangular (because inversion is multiplication by a scalar).
	- If $A$ and $B$ are two triangular matrices which are both upper or both lower and $diag(M)$ denotes the vector constructed from the main diagonal of a matrix $M$, then $diag(AB) = diag(BA) = diag(A) \odot diag(B)$.

- Symmetric matrices
	- A square matrix $A$ is symmetric if $A^T = A$.
	- If $A$ and $B$ are symmetric matrices, then $kA$, $(A + kB)$ and $A^T$ are also symmetric.
	- $AB = (AB)^T$ is not generally true, this is true if and only if $A$ and $B$ commute.
	- If $A$ is an invertible symmetric matrix then $A^{-1}$ is also invertible. ***Proof*** $A = A^T$, from a previous theorem, $(A^{-1})^T = (A^T)^{-1} = A^{-1}$. Hence we have $(A^{-1})^T = A^{-1}$ and $(A^{-1})^T$ is symmetric.
	- If $A$ is an invertible square matrix, then $AA^T$ and $A^TA$ are also invertible. ***Proof*** Since $A$ is invertible, so is $A^T$ and because the product of two invertible matrices is itself an invertible matrix, $AA^T$ and $A^TA$ are both invertible.
	- $AA^T$ and $A^TA$ are symmetric
		- $(AA^T)^T = (A^T)^TA^T = AA^T$
		- $(A^TA)^T = A^T(A^T)^T = A^TA$

## 1.8 - Introduction to Linear Transformations

- A ***transformation*** from $R^n$ to $R^m$ is a function with domain $R^n$ and codomain $R^m$. Such a transformation $T$ is denoted $T : R^n \rightarrow R^m$. In the special case where $n = m$, a transformation is called an ***operator*** on $R^n$. For example, $T(v) = (-v_2,\ v_1)$ is an operator over $R^2$.
- A linear system $Ax = b$ is a transformation mapping $x \in R^n$ to $b \in R^m$. Because the transformation is a matrix multiplication, it is called a ***matrix transformation***. If $n = m$ then it is called a ***matrix operator***. It is denoted $T_A : R^n \rightarrow R^m$. Or occasionally $x \xrightarrow{T_A} w$, read "$T_A$ maps $x$ into $w$".
- ![[la_image3.png]]
- ![[la_image2.png]]
- A function mapping $R^n$ to $R^m$ is a matrix transformation if and only if the following relationships hold for all vectors $u$ and $v$ and for every scalar $k$:
	(i)  $T(u + v) = T(u) + T(v)$
	(ii) $T(ku) = kT(u)$
	***Proof*** If (i) and (ii) are true, then:$$T(k_1u_1 + k_2u_2 + \dots + k_ru_r) = k_1T(u_1) + k_2T(u_2) + \dots + k_rT(u_r)$$For all vectors $u$ and $v$ and all scalars $k$.
	
	Consider the matrix $A = [T(e_1) \mid T(e_2) \mid \dots \mid T(e_n)]$,
	$Ax = x_1T(e_1) + x_2T(e_2) + \dots + x_nT(e_n)$
	$Ax = T(x_1e_1 + x_2e_2 + \dots + x_ne_n) = T(x)$

	The "only if" relation is proven by taking the conclusion and reversing the process to arrive at the premise.

	(i) and (ii) are called ***linearity conditions*** and a transformation satisfying these conditions is called a ***linear transformation***.

- $T_A(x) = T_B(x) \implies A = B$
  ***Proof*** - if the transformations are equal for all $x$ then they are equal for all basis vectors in $R^n$, that is, if:$$Ae_j = Be_j\ \ \ [j = 1,\ 2,\ \dots,\ n]$$
  then, since in $e_j$ the entries are all $0$ except for the $j^{th}$ which is $1$, the corresponding columns of $A$ and $B$ are the same, hence $A = B$. $\blacksquare$

	This result shows that every linear transformation is described by a unique matrix and vice-versa. That unique matrix is called the ***standard matrix*** for the transformation.

### A procedure for finding a standard matrix

As detailed in the penultimate proof, $A = [T(e_1) \mid T(e_2) \mid \dots \mid T(e_n)]$. With this, $A$ can be computed when $T(e_i)\ [i = 1,\ 2,\ ...,\ n]$ is known.

For example:
If $T : R^2 \rightarrow R^2$ and $T(e_1) = \begin{bmatrix}2\\0\end{bmatrix},\ T(e_2) = \begin{bmatrix}0\\2\end{bmatrix}$, then $A = \begin{Bmatrix}2&0\\0&2\end{Bmatrix}$.

### Reflections, rotations and projections in $R^2$ and $R^3$ as linear transformations

- Reflections
	If $P = (x, y)$ is a point in $R^2$, then $(-x, y)$ is that point, reflected about the $y$ axis. This is a linear transformation and thus can be described as a matrix multiplication:
	The transform is $T(x, y) = (-x, y)$, $T(e_1) = \begin{bmatrix}-1\\0\end{bmatrix},\ T(e_2) = \begin{bmatrix}0\\1\end{bmatrix}$. So $A = \begin{Bmatrix}-1&0\\0&1\end{Bmatrix}$.
	$A$ is called a ***reflection operator***.

- Rotations
	The standard basis vectors under rotation through an angle $\theta$ are $$\begin{matrix}T(e_1) = (cos\ \theta, sin\ \theta) \\ T(e_1) = (-sin\ \theta, cos\ \theta)\end{matrix}$$This makes the standard matrix for this transformation $A = [T(e_1) \mid T(e_2)]$,$$\begin{Bmatrix}cos\ \theta & sin\ \theta \\ -sin\ \theta & cos\ \theta\end{Bmatrix}$$Which is the ***rotation matrix*** for $R^2$.

- Projections
	If $P = (x, y, z)$ is a point in $R^3$, then $(x, 0, z)$ is that point, projected onto the $xz$ plane. This is a linear transformation and thus can be described as a matrix multiplication:
	The transform is $T(x, y, z) = (x, 0, z)$, $$\begin{matrix}T(e_1) = \begin{bmatrix}1\\0\\0\end{bmatrix}&T(e_2) = \begin{bmatrix}0\\0\\0\end{bmatrix}&T(e_3) = \begin{bmatrix}0\\0\\1\end{bmatrix}\end{matrix}$$So $A = \begin{Bmatrix}1&0&0\\0&0&0\\0&0&1\end{Bmatrix}$.
	
	$A$ is called a ***projection operator***.

*more examples in the book*

## 1.9 - Compositions of Matrix Transforms

- Compositions of matrix transformations are themselves matrix transformations which represent the successive application of multiple transformations and those transformations are the matrix factors of the standard matrix for the composition:
	If $T_A : R^n \rightarrow R^m$ and $T_B : R^p \rightarrow R^q$ then $T_A(x) = Ax$, $T_B(x) = Bx$ and $T_{BA} = T_B(T_A(x)) = BAx$.
	$BAx$ is the composition of $A$ and $B$, denoted $(T_B \circ T_A)(x)$.
- Matrix inverses reverse transformations. Not all transformations have inverses.
- Since not all matrices commute and all matrices can be used in matrix transformations, not all matrix/linear transformations are commutative.
## 1.10d - Polynomial Interpolation

