
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

- If $T$ is an $n \times n$ triangular matrix, then the eigenvalues of$T$ are the entries on the main diagonal of $A$.
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
	***Proof***
	$(\lambda I - A)x = \lambda Ix - Ax = 0$
	$A^{-1}(\lambda Ix - Ax) = \lambda A^{-1}x - x = 0$
	$A^{-1}x = \lambda^{-1} x$

	Hence, $A^{-1}$ exists if and only if $\lambda \neq 0$. Additionally, this shows that if $\lambda$ is an eigenvalue of $A$ then $\lambda^{-1}$ is an eigenvalue of $A^{-1}$.

	*See book for alternative proof which highlights that the constant term of the characteristic polynomial of $A$ is $|\lambda I - A|$ when $\lambda = 0$*
