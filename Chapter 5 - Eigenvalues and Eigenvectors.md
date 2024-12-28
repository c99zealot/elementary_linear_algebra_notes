
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

## 5.3 - Complex Vector Spaces

 - Review of complex numbers, if $z = a + bi$ is a complex number then
	- $Re(z) = a$, $Im(z) = b$
	- $|z| = \sqrt{a^2 + b^2}$ is the ___modulus___ or ___absolute value___ of $z$
	- $\overline{z} = a - bi$ is the ___complex conjugate___ of $z$
	- $z\overline{z} = a^2 + b^2 = |z|^2$
	- $\phi = \tan^{-1}(\frac{Im(z)}{Re(z)})$ is the angle $z$ makes with the $x$ axis and is called an ___argument___ of $z$
	- $Re(z) = |z|\cos\phi$, $Im(z) = |z|\sin\phi$
	- $|z|(\cos\phi + \sin\phi)$ is called the ___polar form___ of $z$

- Complex eigenvalues
	The characteristic equation of a matrix is a polynomial equation so may have complex roots, the roots are the eigenvalues so a matrix may have complex eigenvalues.
	For example,$$
	\begin{pmatrix}-2 & -1 \\ 5 & 2\end{pmatrix}
	$$Has characteristic equation$$\begin{vmatrix}\lambda + 2 & -1 \\ 5 & \lambda - 2\end{vmatrix} = \lambda^2 + 1 = 0$$Which has solutions $\lambda = i$ and $\lambda = -i$
\
	If a matrix $A$ has complex eigenvalues then $Ax = \lambda x$. $\text{complex} \times \text{real} = \text{complex}$ so the matrix $A$ and/or the vector $x$ must have complex entries/components. This introduces complex vectors and matrices.

- Complex vectors
	Complex vectors are tuples of $n$ numbers just like real vectors, only complex vectors are allowed to have complex components, the space of all complex vectors with $n$ components is referred to as $C^n$. For example, $(3 + 7i, \pi  -i, 12)$ is a vector in $C^3$.

	Every vector in $C^n$ can be expressed as$$v = (a_1,\ \dots,\ a_n) + i(b_1,\ \dots,\ b_n)$$Also denoted $Re(z) + i(Im(z))$ where $Re(v) = (a_1,\ \dots,\ a_n)$ and $Im(v) = (b_1,\ \dots,\ b_n)$

	The vector $\overline v = (\overline v_1,\ \dots,\ \overline v_n) = Re(v) - i(Im(v))$ is called the ___complex conjugate___ of $v$

- Algebraic properties of the complex conjugate, with $u, v \in C^n$ and $k \in \mathbb{C}$ :
	- $\overline{\overline u} = u$
	- $\overline{ku}$ = $\overline k \overline u$
	- $\overline{u + v} = \overline u + \overline v$
	- $\overline{u - v} = \overline u - \overline v$

- Complex matrices
	Complex matrices are grids of $m \times n$ numbers just like real matrices, only complex matrices are allowed to have complex entries. For example,$$\begin{pmatrix}3 + 7i & \pi - i & 6 + 5i  \\ 12 & \sqrt2 - i & 64\end{pmatrix}$$Is a $3 \times 2$ complex matrix.

	If $A$ is an $m \times k$ complex matrix and $B$ is a $k \times n$ complex matrix, then:
	- $\overline{\overline A} = A$
	- $\overline{A^T} = \overline{{A}}\ ^T$
	- $\overline{AB} = \overline A\ \overline B$

- Complex Norm & Dot Product
	For $v, u \in C^n$:
	- $u \cdot v = u_1\overline v_1 + \dots + u_n\overline v_n$ (conjugates ensure $u \cdot v \in \mathbb R$)
	- $||v|| = \sqrt{v \cdot v} = \sqrt{|v_1|^2 + \dots + |v_n|^2}$

	As with real vectors, $u \cdot v$ implies orthogonality and unit vectors have $||v|| = 1$.

	Properties of the complex dot product
	- $u \cdot v = \overline{v \cdot u}$
	- $u \cdot (v + w) = u \cdot v + u \cdot w$
	- $k(u \cdot v) = (ku) \cdot v$
	- $u \cdot kv = \overline k (u \cdot v)$
	- $v \cdot v \geq 0 \wedge v \cdot v = 0 \iff v = 0$

- A theorem about complex eigenvalues
	If $\lambda$ is an eigenvalue of a real $n \times n$ matrix $A$ with corresponding eigenvector $x$, then $\overline\lambda$ is also an eigenvalue of $A$, and $\overline x$ is a corresponding eigenvector.
	***Proof***
	$Ax = \lambda x \implies \overline{Ax} = \overline A \overline x = \overline{\lambda x} = \overline \lambda \overline x$
	$\overline{A} = A$, since $A$ has real entries, so $\overline A \overline x = A \overline x$
	Because $\overline A \overline x = \overline\lambda \overline x$, $A \overline x = \overline\lambda \overline x$, revealing $\overline\lambda$ as an eigenvalue of $A$ with corresponding eigenvector $\overline x$.

- If $A$ is a $2 \times 2$ matrix, then $det(\lambda I  - A) = \lambda^2 - tr(A)\lambda + det(A)$
	$det(\lambda I - A) = \begin{vmatrix}\lambda - a & -b \\ -c & \lambda - d\end{vmatrix} = (\lambda - a)(\lambda - d) - bc = \lambda^2 - (a + d)\lambda + (ad - bc)$
	$a + d = tr(A)$
	$ad - bc = det(A)$

	Substituting $a = 1$, $b = -tr(A)$, $c = det(A)$ into the discriminant of the quadratic equation, $b^2 - 4ac$, gives $tr(A)^2 - 4det(A)$. Call this $d$, then:
	$d > 0 \implies \text{A has two distinct real eigenvalues}$
	$d = 0 \implies \text{A has one repeated real eigenvalue}$
	$d < 0 \implies \text{A has two complex conjugate eigenvalues}$

- If $A$ is a real symmetric matrix, then $A$ only has real eigenvalues
	***Proof***
	Let $A$ be a real symmetric matrix with complex eigenvalues and corresponding eigenvectors in $C^n$.

	Multiplying both sides of $Ax = \lambda x$ by $\overline{x}^T$ gives $\overline{x}^TAx = \lambda||x||^2$, since:
	$\overline{x}^TAx = \overline{x}^T(\lambda x) = \lambda(\overline{x}^T x) = \lambda(x \cdot x)^\text{[1]} = \lambda||x||^2$
	
	\[1]  -  $\overline{x}^Tx\ =\ x \cdot x$ because $\overline{x}^Tx = \overline{x} \cdot x$ and the complex inner product takes the conjugate components of the left vector, making $\overline{x} \cdot x = \overline{\overline x} \cdot x = x \cdot x$

	$\overline{x}^TAx = \lambda ||x||^2 \implies \lambda = \frac{\overline{x}^TAx}{||x||^2}$
	Proving $\frac{\overline{x}^TAx}{||x||^2} \in \mathbb R$ proves $A$ has only real eigenvalues.
	$||x||^2 \in \mathbb R$, by the definition of the norm.
	
	$\overline{x}^TAx \in \mathbb R$ if $\overline{\overline{x}^TAx} = \overline{x}^TAx$ :
	
	$\overline{\overline{x}^TAx} = x^T\overline{Ax} = \overline{(Ax)}^Tx = (\overline A \overline x)^Tx = (A\overline x)^Tx \text{ [because }$$\overline A = A$$\text{, since }$$A \in \mathbb R\text{]}$
	$= \overline{x}^TA^Tx = \overline{x}^TAx \text{ [because }$$A^T = A$$\text{, since }$$A$$\text{ is symmetric]}$

- A geometric interpretation of complex eigenvalues of $2 \times 2$ matrices
	The eigenvalues of the real matrix $$C = \begin{pmatrix}a & -b \\ b & a\end{pmatrix}$$Are $\lambda = a \pm bi$. If $a$ and $b$ are not both zero, then $C$ can be factored as $$\begin{pmatrix}a & -b \\ b & a\end{pmatrix} = \begin{pmatrix}|\lambda| & 0 \\ 0 & |\lambda|\end{pmatrix}\begin{pmatrix}\cos\phi & -\sin\phi \\ \sin\phi & \cos\phi\end{pmatrix}$$Where $\phi$ is an argument of $\lambda$.
	$C$ is expressible as a multiplication of a dilation matrix by a rotation matrix.

	***Proof*** The characteristic equation of $C$ is $(\lambda - a)^2 + b^2$, from which it follows that the eigenvalues of $C$ are $\lambda = a \pm bi$. Assume $a$ and $b$ are not both $0$ since $\lambda \neq 0$.
	
	Let $\phi$ be an argument of $\lambda$, hence $a = |\lambda|\cos\phi$ and $b = |\lambda|\sin\phi$.
	$C$ can be expressed as $$C = \begin{pmatrix}|\lambda|\cos\phi & -|\lambda|\sin\phi \\ |\lambda|\sin\phi & |\lambda|\cos\phi\end{pmatrix}$$Thus $$C = |\lambda|\begin{pmatrix}\cos\phi & -\sin\phi \\ \sin\phi & \cos\phi\end{pmatrix}$$Or $$C = |\lambda|\begin{pmatrix}1 & 0 \\ 0 & 1\end{pmatrix}\begin{pmatrix}\cos\phi & -\sin\phi \\ \sin\phi & \cos\phi\end{pmatrix}$$So $C = \begin{pmatrix}|\lambda| & 0 \\ 0 & |\lambda|\end{pmatrix}\begin{pmatrix}\cos\phi & -\sin\phi \\ \sin\phi & \cos\phi\end{pmatrix}$

- Similarity of $A$ with $C$ where $A$ is any $2 \times 2$ matrix with complex eigenvalues
	Let $A$ be a real $2 \times 2$ matrix with complex eigenvalues $\lambda = a \pm bi$ (where $b \neq 0$). If $x$ is an eigenvector of $A$ corresponding to $\lambda = a - bi$, then the matrix $P = [Re(x)\ Im(x)]$ is invertible and $$A = P\begin{pmatrix}a & -b \\ b & a\end{pmatrix}P^{-1}$$
	***Proof*** TODO

- A geometric interpretation of $A = PCP^{-1}$
	Let $S = \begin{pmatrix}|\lambda| & 0 \\ 0 & |\lambda|\end{pmatrix}$, $R_\phi = \begin{pmatrix}\cos\phi & -\sin\phi \\ \sin\phi & \cos\phi\end{pmatrix}$
	
	Then $A = PSR_\phi P^{-1}$ and the product $Av = PSR_\phi P^{-1}v$ can be viewed as:
	
	(1) Changing the basis of $v$ from $\{e_1, e_2\}$ to $\{Re(x), Im(x)\}$ via $P^{-1}v$, since $P = [Re(x)\ Im(x)]$ .
	(2) Rotating $P^{-1}v$ by $\phi$ via $R_\phi P^{-1}v$ .
	(3) Scaling that rotated vector by $\lambda$ via $SR_\phi P^{-1}v$ .
	(4) Changing the basis of $v$ back to the standard basis via $SR_\phi P^{-1}v$ .

	So if a $2 \times 2$ real matrix $A$ has complex eigenvalues (with nonzero imaginary parts) it can be viewed as the standard matrix for the above transformation.
	
	*See example on p321 with skewed basis and $S = I$ to map a vector to a point in the ellipse which contains it.*

