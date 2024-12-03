## 2.1 - Determinants by Cofactor Expansion

 - If $A$ is a square matrix, then the ***minor*** of entry $a_{ij}$ is denoted $M_{ij}$ and is the determinant of the submatrix which remains after the $i^{th}$ row and $j^{th}$ column of $A$ are deleted.
	 Example:
	 Let $A = \begin{Bmatrix}3 & 1 & -4 \\ 2 & 5 & 6 \\ 1 & 4 & 8\end{Bmatrix}$,
	 
	 The minor of $a_{11}$ is $det(\begin{Bmatrix}5 & 6 \\ 4 & 8\end{Bmatrix})$, that is the determinant of the matrix resulting from deleting the $i^{th}$ row and $j^{th}$ column from $A$. This determinant is $16$.
 - If $A$ is a square matrix, the the ***cofactor*** of $a_{ij}$ is the number $M_{ij}(-1)^{i + j}$, denoted $C_{11}$
	 Example:
	 Taking $A$ from the previous example: $M_{11} = 16$, $C_{11} = M_{11}(-1)^{i + j}$.
	 Hence, $C_{11} = 16 \times (-1)^{2} = 16$.

- Cofactor expansions of a $2 \times 2$ matrix
	The determinant of a $2 \times 2$ matrix $A$ is $ad - bc$, this can be expressed in terms of its cofactors as $C_{11}a + C_{21}c$. This is called a ***cofactor expansion*** of $det(A)$.

- If $A$ is an $n \times n$ matrix and $cof(a_{ij})$ denotes the cofactor of a matrix entry $a_i$ then there exists a unique value $det(A)$ which is equal to $$cof(a_1)a_1 + \dots + cof(a_n)a_n$$where $a$ denotes an *arbitrary* column *or* row vector of $A$. Such sums are called **cofactor expansions of $det(A)$**

- $det(A)$ is the product of entries along the main diagonal when $A$ is a triangular matrix.
## 2.2 - Evaluating Determinants by Row Reduction

- Let $A$ be a square matrix, if $A$ has a row or column of zeros then $det(A) = 0$
	***Proof*** Cofactor expansion along a row or column of zeros yields $det(A) = 0$

- $det(A) = det(A^T)$
	***Proof*** Cofactor expansion along a row of $A$ is cofactor expansion along a column of $A^T$.

- Effects of EROs on $det(A)$
	(a) - If $EA$ multiplies a single row of $A$ by a scalar $k$ then $det(EA) = k \cdot det(A)$
	(b) - If $EA$ interchanges two rows or columns of $A$ then $det(EA) = -det(A)$
	(c) - If $EA$ adds a multiple of a of $A$ row to another then $det(EA) = det(A)$

- Effects of EROs on $det(I)$
	(a) - If $EI$ multiplies a single row of $I$ by a scalar $k$ then $det(EI) = k$
	(b) - If $EI$ interchanges two rows or columns of $I$ then $det(EI) = -1$
	(c) - If $EI$ adds a multiple of a row of $I$ to another then $det(EI) = 1$

- If two rows in a square matrix $A$ are proportional then $det(A) = 0$
	***Proof*** $A$ is row-equivalent to a matrix with a row of zeros, the relevant row operation adds a multiple of one row to another, this has no effect on $det(A)$ and a matrix with a row of zeros has a determinant of zero.

- Evaluating determinants by row reduction
	General idea: if a matrix is made triangular through row reduction then its determinant can be computed as the product of entries along the main diagonal.
	
	See examples in book p130.
## 2.3 - Properties of Determinants; Cramer's Rule

- Basic properties of determinants
	$det(kA) = k^ndet(A)$, where $A$ is a $n \times n$ matrix.
	
	$det(A + B) \neq det(A) + det(B)$
	
	$det(A) + det(B) = det(C)$, if and only if $A$ a differs from $B$ by either one row or one column and where $C$ is the resultant matrix from adding the differing row or column of $A$ to the corresponding row or column of $B$.

	$det(AB) = det(A)det(B)$
	The proof of the above theorem is lengthy and included in the textbook.

- If $A$ is invertible then $det(A^{-1}) = det(A)^{-1}$
	***Proof*** Since $AA^{-1} = I$, it follows that $det(A^{-1}A) = det(I) = 1$. Therefore $det(A^{-1})det(A) = 1$ which implies $det(A^{-1}) = det(A)^{-1}$

- $Adj(A)$
	Cofactor expansions yield the determinant regardless of which row/col is chosen for the expansion. However, if instead of multiplying the entries along a row/col with their corresponding cofactors, they are multiplied by cofactors from a different row/col; for example, $a_{11}C_{21} + a_{12}C_{22} + a_{13}C_{23}$ then the result is $0$. This is true for all rows and columns.

	If $A$ is a $n \times n$ matrix and $C{ij}$ is the cofactor of $a_{ij}$, then the matrix
	$$
	C = \begin{Bmatrix}
	C_{11} & C_{12} & C_{1n} \\
	\vdots & \ddots & \vdots \\
	C_{n1} & C_{n2} & C_{nn} \\
	\end{Bmatrix}
	$$
	Is called the **cofactor matrix** of $A$.
	$C^{T}$ is called the **adjoint of $A$** and is denoted $adj(A)$.

- $A^{-1} = adj(A)det(A)^{-1}$
	
	***Proof*** consider the product $A \cdot adj(A)$, since $adj(A)$ is the transpose of the cofactor matrix of $A$, multiplying corresponding rows of $A$ and $adj(A)$ yields cofactor expansions of $det(A)$ and multiplying non-corresponding rows yields $0$. Hence, the result of multiplying $A$ by $adj(A)$ is a diagonal matrix with each entry along the diagonal equal to $det(A)$. That is, $A \cdot adj(A) = det(A)I$.

	Since $A$ is invertible, $det(A) \neq 0$ and the previous result can be written as $A[det(A)^{-1}adj(A)] = I$. Here we have $A$ times a matrix equalling $I$ so that matrix must be $A^{-1}$, hence $A^{-1} = adj(A)det(A)^{-1}$ $\blacksquare$

	*This is given in more explicit detail in the book*.

- Cramer's Rule
	If  $Ax = b$ is a system of $n$ linear equations in $n$ unknowns such that $det(A) \neq 0$ then the system has a unique solution. This solution is $$x_1 = \frac{det(A_1)}{det(A)},\ \dots,\ x_n = \frac{det(A_n)}{det(A)}$$
	Where $A_j$ is the matrix which results from replacing the $j^{th}$ column of $A$ with $b$.

	This is proven in the book, potential point of confusion: towards the end of the proof it is stated that "Since $A_j$ differs from $A$ only in the $j^{th}$ column, it follows that the cofactors of entries $b_1, b_2, \dots, b_n$ in $A_j$ are the same as the cofactors of the corresponding entries in the $j^{th}$ column of $A$.", this is true because taking cofactors involves taking minors which involves deleting rows and columns; in the relevant cofactor expansion along $j$, $j$ itself is deleted so the expansion is equal along $j$ for both $A$ and $A_j$. This is true for all $b$.