
- If $A$ is an $n \times n$ matrix, then a nonzero vector $x$ in $R^n$ is called an ***eigenvector*** of $A$ and $\lambda$ is called an ***eigenvalue*** of $A$ if $Ax = \lambda x$ where $\lambda$ is any scalar.

- Finding eigenvalues
	The equation $Ax = \lambda x$ can be rewritten as $(\lambda I - A)x = 0$. Since eigenvectors are nonzero, if $\lambda$ is an eigenvalue of $A$ then the system must have nonzero solutions, hence $|\lambda I - A| = 0$ because if $(\lambda I - A)^{-1}$ existed then $x = 0$ would be the only solution, yielding no eigenvectors or corresponding eigenvalues.

	So if $\lambda$ satisfies $|\lambda I - A| = 0$, then $\lambda$ is an eigenvalue of $A$. This is called the ***characteristic equation of $A$***.

	$|\lambda I - A|$ is in the form $$\begin{vmatrix}\lambda - a_{11} & \dots & -a_{1(n - 1)} & -a_{1n} \\ -a_{21} & \lambda - a_{22} & -a_{2(n - 1)} & -a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ -a_{n1} & -a_{n2} & -a_{n(n - 1)} & \lambda - a_{nn}\end{vmatrix}$$
	The expansion of $|\lambda I - A|$ is an order $n$ polynomial in $\lambda$.

	Example:
	 The matrix $$\begin{Bmatrix}1 & -2 & 3 \\ -4 & 5 & -6 \\ 7 & -8 & 9\end{Bmatrix}$$
	 Has characteristic equation $$\begin{vmatrix}\lambda - 1 & 2 & -3 \\ 4 & \lambda - 5 & 6 \\ -7 & 8 & \lambda - 9\end{vmatrix} = 0$$
	 Expanding this determinant gives$$-\lambda^3 - 18\lambda^2$$
	 This is the ***characteristic polynomial*** of $A$ and its roots are eigenvalues of $A$. Such polynomials of $n \times n$ matrices are always order $n$ because the expansion involves the product of the $n$ entries along the diagonal which is $(\lambda - a_{11})(\lambda - a_{22})\dots(\lambda - a_{nn})$. All other terms in the expansion are of order $n - 1$ or less, so the characteristic polynomial is order $n$.

- If $T$ is an $n \times n$ triangular matrix, then the eigenvalues of $T$ are the entries on the main diagonal of $A$.
	***Proof*** The determinant of a triangular matrix $T$ is the product of the entries along its main diagonal, $\lambda I - T$ is also triangular and has entries along its diagonal $\lambda - t_{11},\ \dots,\ \lambda - t_{nn}$, hence$$|\lambda I - T| = (\lambda - t_{11})\ (\lambda - t_{22})\ (\lambda - t_{nn})$$
	This is the characteristic equation for $T$ and its roots are eigenvalues of $T$. Since it is factored, the roots can be seen by inspection; $t_{11},\ t_{22},\ t_{nn}$ which are the entries along the main diagonal of $T$.

- Equivalent statements for any $n \times n$ matrix $A$ about eigenvalues
	(a) $\lambda$ is an eigenvalue of $A$
	(b) $\lambda$ is a solution to the characteristic equation $|\lambda I - A| = 0$
	(c) The system of equations $(\lambda I - A)x = 0$ has nontrivial solutions
 	(d) There is a nonzero vector $x$ such that $Ax = \lambda x$

- Finding eigenvectors
	For a given eigenvalue $\lambda$, all solutions to the system $(\lambda I - A)x = 0$ are eigenvectors of $A$. Meaning the eigenvectors can be found simply by solving the system.

- Eigenspaces
	The eigenvectors of $A$ for a given $\lambda$ form the solution space for $(\lambda I - A)x = 0$, this is referred to as the ***eigenspace of $A$ corresponding to $\lambda$*** and is equal to $null(\lambda T - A)$.

	Bases for eigenspaces are found by finding the basis to $null(\lambda I - A)$.

- An $n \times n$ matrix $A$ is invertible if and only if $0$ is not an eigenvalue of $A$.
	*See book for proof which highlights that the constant term of the characteristic polynomial of $A$ is $|\lambda I - A|$ when $\lambda = 0$*

- If $\lambda$ is an eigenvalue of $A$ then $\lambda^{-1}$ is an eigenvalue of $A^{-1}$.
	***Proof***
	$(\lambda I - A)x = \lambda Ix - Ax = 0$
	$A^{-1}(\lambda Ix - Ax) = \lambda A^{-1}x - x = 0$
	$A^{-1}x = \lambda^{-1} x$
## 5.2 - Diagonalisation

- Square matrices $A$ and $B$ are called ***similar*** if there exists an invertible matrix $P$ such that $A = P^{-1}BP$

- If $A$ is similar to $B$ then $B$ is similar to $A$ ; $B = Q^{-1}AQ$ where $Q = P^{-1}$.

- $A$ and $B$ share many properties, such properties are called ***similarity invariants***, some important ones include:
	- $det(A) = det(B)$
	- $A^{-1}$ exists if and only if $B^{-1}$ exists
	- $rank(A) = rank(B)$
	- $nullity(A) = nullity(B)$
	- $tr(A) = tr(B)$
	- The characteristic polynomial of $A$ is equal to that of $B$
	- $A$ and $B$ have the same eigenvalues
	- $dim(null(\lambda I - A)) = dim(null(\lambda I - B))$

- It is useful to find a diagonal matrix which is similar to some matrix $A$ since various properties of diagonal matrices are trivial to compute and many of these properties are similarity invariants. For example, given a particularly large matrix $A$ for which it would be impractical to calculate eigenvalues via solving the characteristic equation, if there exists an invertible matrix $P$ and a diagonal matrix $D$ such that $D = P^{-1}AP$ then the eigenvalues of $A$ can be found on the main diagonal of $D$.

	If $A = P^{-1}DP$ where $P$ is invertible and $D$ is diagonal, then $A$ is said to be ***diagonalisable*** and $P$ is said to ***diagonalise*** $A$.

- Equivalent statements for $A_{n \times n}$
	(a) $A$ is diagonalisable
	(b) $A$ has $n$ linearly independent eigenvectors

	***Proof (a) $\implies$ (b)***
	If $A$ is diagonalisable then there exists an invertible matrix $P$ and a diagonal matrix $D$ such that $P^{-1}AP = D$. Equivalently, $AP = PD$.
	
	Let $p_1,\ ...,\ p_n$ be the column vectors of $P$, the product $AP$ can be expressed as$$A[p_1\ \dots\ p_n] = [Ap_1\ \dots\ Ap_n]$$Let $d_1,\ \dots,\ d_n$ be the entries along the main diagonal of $D$, the product $PD$ can be expressed as$$[d_1p_1\ \dots\ d_np_n]$$Equating these:$$[Ap_1\ \dots\ Ap_n] = [d_1p_1\ \dots\ d_np_n]$$And then equating components:$$Ap_1 = d_1p_1,\ \dots,\ Ap_n = d_np_n$$Reveals that $p_n$ and $d_n$ are corresponding eigenvectors and eigenvalues of $A$. The vectors are linearly independent because they are column vectors of an invertible matrix.
	
	***Proof (b) $\implies$ (a)***
	If $A$ has $n$ linearly independent eigenvectors and $P = [p_1\ \dots\ p_n]$ is the matrix whose column vectors are those eigenvectors, then $AP = A[p_1\ \dots\ p_n]$.
	
	If $D$ is the diagonal matrix whose main diagonal consists of $d_1,\ \dots,\ d_n$, then $PD = [d_1p_1\ \dots\ d_np_n]$, then $[Ap_1\ \dots\ Ap_n] = [d_1p_1\ \dots\ d_np_n]$; $AP = PD$. The column vectors of $P$ are linearly independent so $P$ is invertible, thus $P^{-1}AP = D$.
	

- Finding $P$
	To find $P$ we need $n$ linearly independent eigenvectors of $A$, these can be the basis vectors for the eigenspaces of $A$, of which you know there are at most $n$; one for each of the $n$ eigenvalues which are roots of the $n\text{-degree}$ characteristic polynomial. There may be fewer than total $n$ basis vectors in which case $P$ does not exist.

	After finding the basis vectors $b_1,\ \dots,\ b_n$, construct the matrix $P = [b_1\ \dots\ b_n]$.
	$P$ diagonalises $A$ and $P^{-1}AP$ is the diagonal matrix whose entries consist of eigenvalues of $A$.

- Determining the existence of $P$
	$P$ exists if and only if $A_{n \times n}$ has $n$ linearly independent eigenvectors, this can be determined by finding $nullity(\lambda I - A)$.

	For a triangular matrix $T$, if (but not iff) the entries along the main diagonal are distinct, they are the distinct solutions to the characteristic equation of $T$ and correspond to at least one basis vector, there are at most an equal number of distinct eigenvalues and total basis vectors for eigenspaces of $T$ so there must be $n$ total vectors in this case, indicating that $P$ exists.

- If a matrix $A$ has distinct eigenvalues then the corresponding eigenvectors of $A$ are linearly independent; hence, $A$ is diagonalisable.
	*Proof on p308*

	This result also shows that all triangular matrices which distinct entries along the main diagonal are diagonalisable, the converse is not true however (proof on p308).

- If $k$ is a positive integer, $\lambda$ is an eigenvalue of $A$ and $x$ is a corresponding eigenvector, then $\lambda^k$ is an eigenvalue of $A^k$ and $x$ is a corresponding eigenvector; $Ax = \lambda x \implies A^kx = \lambda^k x$.
	***Proof*** $A^2x = A(Ax) = A(\lambda x) = \lambda(Ax) = \lambda (\lambda x) = \lambda^2 x$

- Powers of diagonalisable matrices
	$A^k$ can be computed efficiently if $A$ is diagonalisable:

	$P^{-1}AP = \begin{bmatrix}d_{11} & 0 & \dots & 0 \\ 0 & d_{22} & \dots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \dots & d_{nn}\end{bmatrix} = D$

	$(P^{-1}AP)^k = \begin{bmatrix}{d_{11}}^k & 0 & \dots & 0 \\ 0 & {d_{22}}^k & \dots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \dots & {d_{nn}}^k\end{bmatrix} = D^k$
	

	Consider $k = 2$
	$(P^{-1}AP)^2 = (P^{-1}AP)(P^{-1}AP) = P^{-1}APP^{-1}AP = P^{-1}A^2P$

	The pattern continues for all $k$ (proof by induction probably)

	$(P^{-1}AP)^k = P^{-1}A^kP \implies A^k = P(P^{-1}AP)^kP^{-1} = PD^kP^{-1}$

	So $A^k$ can be found as $PD^kP^{-1}$.

- Geometric and Algebraic Multiplicity
	If $\lambda_0$ is an eigenvalue of $A$, then
		(a) ***Geometric multiplicity*** refers to the dimension of the eigenspace corresponding to $\lambda_0$.
		(b) ***Algebraic multiplicity*** refers to the number of times $\lambda - \lambda_0$ appears as a factor of the characteristic polynomial of $A$.
\
		For example, the matrix with characteristic polynomial $(\lambda - 1)(\lambda - 2)^2$ (which is known to have eigenspace dimension $= 2$ when $\lambda = 2$) has geometric and algebraic multiplicities of $2$ and $2$.
\
	If $A$ is a square matrix, then
		(a) For every eigenvalue of $A$, the geometric multiplicity is less than or equal to the algebraic multiplicity.
		(b) $A$ is diagonalisable if and only if the geometric multiplicity is equal to the algebraic multiplicity.

