## 4.1 - Real vector spaces
- Let $V$ be an arbitrary nonempty set of objects on which two operations are defined: addition and multiplication by scalars. By "addition" it is meant that a rule exists for associating each pair of objects in the set, $u$ and $v$, with an object $u + v$, also in $V$. By scalar multiplication it is meant that a rule exists for associating each scalar $k$ and object in $V$ with an object $ku$, called the scalar multiple of $u$ by $k$. If the following axioms are satisfied by all objects $u$, $v$ and $w$ in $V$ and all scalars $k$ and $m$, then it is said that $V$ is a vector space and the objects within $V$ are vectors.
	1.   $u, v \in V \implies u + v \in V$
	2.   $u + v = v + u$
	3.   $u + (v + w) = (u + v) + w$
	4.   $\exists 0 \in V \mid \forall u \in V,\ 0 + u = u + 0$
	5.   $\forall u \in V,\ \exists\ {-u} \mid u + (-u) = (-u) + u = 0$
	6.   $u \in V \implies ku \in V$, where $k$ is any scalar
	7.   $k(u + v) = ku + kv$
	8.   $(k + m)u = ku + mu$
	9.   $k(mu) = (km)u$
	10. $1u = u$
## 4.2 - Subspaces
- A subspace is a subset of a vector space which is itself a vector space
  
- Not every subset of a vector space is a subspace and to determine whether a given subset is one the vector space axioms must be verified. Not all of them need to be checked, however, since some are "inherited" by all subsets of a vector space. For example, if $V$ is a vector space then, is is true that $1v = v$, where $v \in V$.
  $U \subset V \implies u \in V$, where $u \in U$
  However, other axioms such as $u, v \in V \implies u + v \in V$ may not hold.
  The axioms which are guaranteed to hold are axioms $2,3,7,8,9,10$. The others must be verified but it is sufficient to show that a subset of vectors is closed under addition and multiplication because those imply the existence of negative and zero vectors within the subset; if multiplication is closed then, negatives exist and if negatives exist and addition is closed then, $v + -v = 0$ exists within the set.
  
- Lines through the origin are subspaces of $R^2$
- Planes through the origin are subspaces of $R^3$

## 4.3 - Spanning Sets
- A _linear combination_ $w$ of a set of vectors $S = \{v_1,\ v_2,\ ...,\ v_n\}$ is a vector in the form:
  $$w = k_1v_1\ +\ k_2v_2\ +\ ...\ +\ k_nv_n$$
- A span $span\{S\}$ of a set of vectors $S$ is the set of all linear combinations of those vectors. $span\{S\}$ is always a subspace of the vector space $V$ to which the vectors in $S$ belong and it is said that the vectors in $S$ span the subspace $span\{S\}$. Note that $span\{S\}$ is not necessarily equal to $V$.
  
- $span\{S\}$ is the "smallest" subspace containing all vectors in S
- $span\{v\}$, where $v \in R^2, v \neq 0$ is a line through the origin
	- The span of a single vector is all the possible ways to scale that vector.
- $span\{u, v\}$, where $u \in R^3, v \in R^3$ and $u$ and $v$ are not colinear, is a plane through the origin
	- A span of two vectors is all the ways to scale and add them. Two vectors can systematically trace out a plane by adding them together to create an irregular "L" shape and scaling both to "reach out" to the boundaries of the plane. Negative scalars provide full coverage of the space.
	
- The standard unit vectors span $R^n$
	- This is fairly obvious; all linear combinations of the unit vectors in $R^n$ give all vectors in $R^n$.
	  
- The set $P_n = span\{1, x^2, ..., x^n\}$ of all polynomials with $0 \leq$ degree $\leq n$ form a subspace of $F(-\infty, \infty)$, where $F(-\infty, \infty)$ denotes the vector space of all real-valued functions.
	- The set of all polynomials of degree n (not $\lt n$) does not form a vector space because it is not closed under addition, e.g.:
	  $$(ax^3 + bx^2 + cx + d) + (-ax^3 + bx^2 + cx + d) = bx^2 + cx + d$$

- Given a set $S$ of vectors in $V$ and a vector $v$ in $V$, determine whether $v$ is a linear combination of the vectors in $S$
	- Construct system of equations from $v = k_1v_1\ +\ ...\ +\ k_nv_n$ 

- Given a set $S$ of vectors in $R^n$, determine whether the vectors span $R^n$
	- $u = k_1v_1\ +\ ...\ +\ k_nv_n$, where $u$ is an arbitrary vector. If the coefficient matrix for the system has a non-zero determinant, then the system is consistent and any vector in $R^n$ can be expressed as a linear combination of vectors from $S$, thus $S$ spans $R^n$.
 
- The solution set of a homogenous system in $n$ unknowns is a subspace of $R^n$, i.e. in the following:
$$
\begin{Bmatrix}
   a_{11} & a_{12} & a_{13}  \\
   a_{21} & a_{22} & a_{23}  \\
   a_{31} & a_{32} & a_{33}  \\
\end{Bmatrix}
\begin{bmatrix}
	x \\
	y \\
	z \\
\end{bmatrix}
=
\begin{bmatrix}
	0 \\
	0 \\
	0 \\
\end{bmatrix}
$$
	$S = \{x,\ y,\ z\}$ is the solution set and is a subspace of $R^3$
	Intuitively, the solution set of a homogenous system is a set of vectors which can be scaled and summed to equal the zero vector. In $R^2$ and $R^3$ this is only possible if the vectors are colinear or coplanar, respectively. It seems to follow that, since lines and planes are subspaces in $R^2$ and $R^3$, subspaces in general are formed by sets with this property.
	More formally, with
	$$
	A = \begin{Bmatrix}
	    a_{11} & a_{12} & a_{13}  \\
	    a_{21} & a_{22} & a_{23}  \\
	    a_{31} & a_{32} & a_{33}  \\
	\end{Bmatrix}
	$$
	By definition, any vector $v$ from the solution set $S$ has the property that
	$$
	Av =
	\begin{bmatrix}
		0 \\
		0 \\
		0 \\
	\end{bmatrix}
	$$
	Which implies that $$
	Au + Av = A(u + v) =
	\begin{bmatrix}
		0 \\
		0 \\
		0 \\
	\end{bmatrix}
	$$
	Which highlights $(u + v)$ as a solution to the system and thus also a member of $S$, making $S$ closed under addition. 
	Similarly, 	$$Av = A(kv) = k(Av) =
	k\begin{bmatrix}
		0 \\
		0 \\
		0 \\
	\end{bmatrix}$$
	Which shows that scaling any vector from $S$	gives a vector also in $S$.
	With closure under addition and multiplication both shown to hold, it can be concluded that $S$ is a subspace. Since $S$ is a subspace and a solution set it is referred to as a *solution space*.
	The example is for a solution space of cardinality $\geq 1$ which can be assumed because $S$ contains at least the trivial solution with $x$ being the zero vector.
## 4.4 - Linear Independence
- If $S = \{v_1,\ ...,\ v_r\}$ is a nonempty set of vectors in a vector space $V$, then the vector equation $$k_1v_1\ +\ ...\ +\ k_rv_r = 0$$
	Has at least one solution, namely, $$k_1 = 0,\ ...,\ k_r = 0$$
	This is called the *trivial solution*. If this is the only solution, then $S$ is said to be a *linearly independent set*. If there are solutions in addition to the trivial solution, then $S$ is said to be a *linearly dependent set*.
	
	The standard unit vectors in $R^n$ are linearly independent. $k_1i + k_2j + k_3k = 0 \implies (k_1,\ k_2,\ k_3) = 0$, where $i,\ j$ and $k$ are the standard unit vectors in $R^3$ . This idea extends to $R^n$.

#### Determining the linear independence of a set of vectors
\	- Given a set of vectors $\{(1,-2,3),\ (5,6,-1),\ (3,2,1)\}$, construct the equation: $$k_1(1,-2,3) + k_2(5,6,-1) + k_3(3,2,1) = 0i + 0j + 0k$$
\
	  Equate components to yield the homogenous linear system:
	$$
	\begin{matrix}
	k_1 + 5k_2 + 3k_3 = 0i \\
	-2k_1 + 6k_2 + 2k_3 = 0j \\
	3k_1 - k_2 + k_3 = 0k
	\end{matrix}
	$$
	To show that there exist nontrivial solutions ($k_1 \neq 0, k_2 \neq 0, k_3 \neq 0$), it is sufficient to solve the system:$$k_1 = -\frac12t,\ \ k_1 = -\frac12t,\ \ k_3 = t\ \ $$
	Or show that $det(A) \neq 0$, where $A$ is the coefficient matrix for the system.


- A set $S = \{v_1,\ ...,\ v_n\}$, where $n \geq 2$, is linearly dependent if and only if at least one of the vectors in $S$ is expressible as a linear combination of the other vectors in $S$

***Reword this***
	The equation
	$$k_1v_1\ + \ ...\ + k_mv_m + k_nv_n\ = 0$$
	Has the trivial solution with $k_1 =\ ...\ = k_m = k_n = 0$  
	It follows that
	$$k_1v_1\ + \ ...\ + k_nv_n\ = -k_mv_m$$
	And if $k_m \neq 0$ (i.e. if there exists a nontrivial solution)
	$$\frac1{-k_m}(k_1v_1\ + \ ...\ + k_nv_n)\ = v_m$$
	(an arbitrary vector $v_m$ in $S$ is expressible as a linear combination of the other vectors in $S$ )
	Hence, the $y \implies x$ relation is proven. The $x \implies y$ relation is proven by doing the above in reverse.

- $S$ is linearly independent if and only if no vector in $S$ is expressible as a linear combination of the other vectors in $S$.
	Proof:
	Given a linear combination in $S$ equaling the zero vector
	$$k_1v_1\ + \ ...\ + k_mv_m + k_nv_n\ = 0$$
	Knowing that $S$ is linearly independent, all scalars equal $0$ and the following expression for an arbitrary vector in $S$ involves a division by $0$.
	$$\frac1{-k_m}(k_1v_1\ + \ ...\ + k_nv_n)\ = v_m$$
	Hence, the $x \implies y$ relation is proven.

	Knowing that no vector from $S$ can be expressed as a linear combination of the others, consider
	the existence of a nontrivial solution where some scalar $k_m \neq 0$. This implies the possibility of an expression for $v_m$ which is a linear combination of vectors from $S$. $$\frac1{-k_m}(k_1v_1\ + \ ...\ + k_nv_n)\ = v_m$$
	However, this contradicts the initial statement that no vector from $S$ can be expressed as a linear combination of the others. Hence, only the trivial solution must exist and $S$ is linearly independent. This proves the $y \implies x$ relation.

#### Sets with one or two vectors
  - A finite set containing the zero vector is linearly dependent
    $$k_1v_1 + ... + k_mv_m + k_nv_n = 0$$
    Has infinite nontrivial solutions if $v_n = 0$ since all coefficients can be 0 while $k_n$ is any nonzero real number.
    
  - A set with exactly one vector is linearly independent if and only if that vector is not the zero vector
    If the vector is nonzero, then there's only the trivial solution to $kv = 0$ with $k = 0$. If there is only the trivial solution, then the only value of $k$ for which $kv = 0$ is $k = 0$ which necessarily means $v \neq 0$.
    
  - A set with exactly two vectors is linearly independent if and only if neither vector is a scalar multiple of the other
    If $u = kv$, then $u$ can be expressed as a linear combination of the other vectors in the set ($v$) and hence the set is linearly dependent. The "only if" relation here is obvious. If $u \neq kv$, then the set is independent.

- Two linearly independent vectors do not lie on the same line; otherwise one would be a scalar multiple of the other.
- Three linearly independent vectors do not lie on the same plane; otherwise one would be a linear combination of the others since $span\{u, v\}$ is a plane.


- Let $S = \{v_1, v_2, ..., v_r\}$ be a set of vectors in $R^n$. If $r > n$, then $S$ is linearly dependent.

	***Proof*** Suppose that
$$
\begin{matrix}
v_1 = (v_{11}, v_{12}, ..., v_{1n}) \\
v_2 = (v_{21}, v_{22}, ..., v_{2n}) \\
\vdots \\
v_1 = (v_{r1}, v_{r2}, ..., v_{rn}) \\
\end{matrix}
$$
	and consider the equation $$k_1v_1 + k_2v_2 +\ ...\ + k_rv_r = 0$$
	Express both sides of this equation in terms of components and equate the corresponding
	components to obtain the system
	$$
	\begin{matrix}
	v_{11}k_1 + v_{21}k_2 +\ ...\ + v_{r1}k_r = 0 \\
	v_{12}k_1 + v_{22}k_2 +\ ...\ + v_{r2}k_r = 0 \\
	\vdots \\
	v_{1n}k_1 + v_{2n}k_2 +\ ...\ + v_{rn}k_r = 0
	\end{matrix}
	$$
	This is a homogenous system of $n$ equations in $r$ unknowns. Since $k > r$, it follows that the system has nontrivial solutions. Therefore, $S = \{v_1, v_2, ..., v_r\}$ is a linearly dependent set.

	This system is represented as
	$$
	\begin{Bmatrix}
	v_{11} & v_{21} & ... & v_{r1} \\
	v_{12} & v_{22} & ... & v_{r2} \\
	... \\
	v_{1n} & v_{2n} & ... & v_{rn} \\
	\end{Bmatrix}
	
	\begin{bmatrix}
	k_1 \\
	k_2 \\
	... \\
	k_r
	\end{bmatrix}
	=
0_n
	$$
	Where $0_n$ is the zero vector in $R^n$
	
	Since $r > n$, the matrix must be "padded out" with some zero coefficients
		$$
	\begin{Bmatrix}
	v_{11} & v_{21} & ... & v_{r1} \\
	v_{12} & v_{22} & ... & v_{r2} \\
	\vdots \\
	v_{1n} & v_{2n} & ... & v_{rn} \\
	0 & 0 & ... & 0
	\end{Bmatrix}
	
	\begin{bmatrix}
	k_1 \\
	k_2 \\
	\vdots \\
	k_r
	\end{bmatrix}
	=
0_n
	$$
	Which introduces the possibility for arbitrary $k$ values, exposing nontrivial solutions.

If $f_1 = f_1(x),\ f_2 = f_2(x),\ ...,\ f_n = f_n(x)$ are functions that are $n - 1$ times differentiable on the interval $(-\infty, \infty)$, then the determinant
$$
W(x) = \begin{vmatrix}
\begin{bmatrix}
f_1(x) & f_2(x) & ... & f_n(x) \\
f_1'(x) & f_2'(x) & ... & f_n'(x) \\
\vdots \\
f_1^{(n-1)}(x) & f_2^{(n-1)}(x) & ... & f_n^{(n-1)}(x)
\end{bmatrix}
\end{vmatrix}
$$
is called the ***Wronskian*** of $f_1,\ f_2,\ ...,\ f_n$

The following is a proof that if the Wronskian of a set of functions is not identically zero, then the functions form a linearly independent set.

Suppose that $f_1 = f_1(x),\ f_2 = f_2(x),\ ...,\ f_n = f_n(x)$ are linearly dependent.
This implies that $$k_1f_1 + k_2f_2 +\ ...\ + k_nf_n = 0$$ has a nontrivial solution. Or equivalently, that for a certain set of coefficients $$k_1f_1(x) + k_2f_2(x) +\ ...\ + k_nf_n(x) = 0$$
is true for all $x$ in $(-\infty, \infty)$.

Using this equation together with those that result by differentiating it $n - 1$ times yields the linear system
$$
\begin{matrix}
k_1f_1(x)\ +\ k_2f_2(x)\ +\ ...\ +\ k_nf_n(x) = 0\\
k_1f_1'(x)\ +\ k_2f_2'(x)\ +\ ...\ +\ k_nf_n'(x) = 0\\
\vdots \\
k_1f_1^{(n-1)}(x)\ +\ k_2f_2^{(n-1)}(x)\ +\ ...\ +\ k_nf_n^{(n-1)}(x) = 0
\end{matrix}
$$
The linear independence of $f_1,\ f_2,\ ...,\ f_n$ implies that the system
$$
\begin{Bmatrix}
k_1f_1(x)\ +\ k_2f_2(x)\ +\ ...\ +\ k_nf_n(x)\\
k_1f_1'(x)\ +\ k_2f_2'(x)\ +\ ...\ +\ k_nf_n'(x)\\
\vdots \\
k_1f_1^{(n-1)}(x)\ +\ k_2f_2^{(n-1)}(x)\ +\ ...\ +\ k_nf_n^{(n-1)}(x)
\end{Bmatrix}
\begin{bmatrix}
k_1 \\
k_2 \\
\vdots \\
k_n
\end{bmatrix}
=
\begin{bmatrix}
0 \\
0 \\
\vdots \\
0
\end{bmatrix}
$$
Has a nontrivial solution. This in turn implies that the determinant of that matrix is zero for all $x$. Since this determinant is the Wronskian, this proves that *linearly independent implies an identically zero Wronskian*. Because this is true its contrapositive is also true; *non identically zero Wronskian implies linear dependence*

- Example using the Wronskian to show that a set of functions is linearly independent
	$f_1 = x,\ f_2 = sin\ x$

	$$
	W(x) = \begin{vmatrix}
	x & sin\ x \\
	1 & cos\ x
	\end{vmatrix}
	= x\ cos\ x - sin\ x
	$$
	The Wronskian is not identically zero, $x = \frac\pi2$ gives a result of $\frac\pi2$. Thus, the functions are linearly independent.  
## 4.5 - Coordinates and basis
#### Examples of coordinate systems
![[la_image20.png]]
![[la_image19.png]]
- Coordinate systems are defined in terms of unit vectors, for example, the first system in the second image is just the standard cartesian coordinate system with unit vectors $u_1 = (1, 0);\ u_2 = (0, 1)$. However, the second system has the unit vectors $u_1 = (1, 0);\ u_2 = (2, 0)$. This idea is continued in the 3rd and 4th systems w
	After defining unit vectors, providing that they are linearly independent, any point in the coordinate system can be described using a linear combination in the following form:
	$$\vec{OP} = au_1 + bu_2$$
	This is a vector from the origin to a point $P$ and the coordinates $a,\ b$ are attached to $P$.

#### Extending the concepts of basis vectors and coordinate systems to general vector spaces
A vector space $V$ is either ***finite-dimensional*** or ***infinite-dimensional***. The former is true if there is a finite set of vectors which spans $V$ and the latter is true if such a set does not exist.
\
	If $S = \{v_1,\ v_2,\ ...,\ v_n\}$ is a set of vectors in a finite-dimensional vector space $V$, then $S$ is called a ***basis*** for $V$ if:
		*(a)* $S$ spans $V$.
		*(b)* $S$ is linearly independent.
\
  	*(a)* guarantees that every vector in $V$ can be expressed as a linear combination of vectors in $S$.
	*(b)* guarantees that there is a unique linear combination of vectors in $S$ for every vector in $V$.

- Show that a set of vectors form a basis for a vector space
	The definition of a basis states that the vectors which make it up must be linearly independent and span the vector space in which they reside. Refer to previous sections for techniques for proving that a set of vectors spans a vector space as well as linear independence.


***Mention here how it's sufficient to just find $det(A) \neq 0$***  


- Standard unit vectors of $P_n$
	The standard unit vectors of $P_n$ are $\{x,\ ...,\ x^n\}$
- Standard unit vectors of $M_{mn}$
	The set of standard unit vectors of $M_{mn}$ is the set of all unique matrices in $M_{mn}$ with a single element equal to $1$ and the rest equal to $0$. For example, the basis for $M_{22}$ is below.
	$$
	\begin{Bmatrix}
	1 & 0 \\
	0 & 0
	\end{Bmatrix},\
	\begin{Bmatrix}
	0 & 1 \\
	0 & 0
	\end{Bmatrix},\
	\begin{Bmatrix}
	0 & 0 \\
	0 & 1
	\end{Bmatrix},\
	\begin{Bmatrix}
	0 & 0 \\
	1 & 0
	\end{Bmatrix}
	$$
- $P_\infty$ is an infinite-dimensional vector space
	![[la_image18.png]]

#### Correspondence between finite-dimensional vector spaces\
If $S = \{v_1,\ v_2,\ ...,\ v_n\}$ is a basis for a vector space $V$ and $$v = c_1v_1 + c_2v_2 +\ ...\ + c_nv_n$$is the expression for a vector $v$ in terms of the basis $S$, then the scalars $c_1,\ c_2,\ ...,\ c_n$ are called ***coordinates*** of $v$ relative to the basis $S$. The vector $(c_1,\ c_2,\ ...,\ c_n)$ in $R^n$ constructed from these coordinates is called the ***coordinate vector of v relative to $S$***; it is denoted by $$(v)_S = (c_1,\ c_2,\ ...,\ c_n)$$$(v)_S$ is a vector in $R_n$ and since it is unique for every $v$, this provides a mapping from vectors in some arbitrary vector space $V$ to geometric vectors in $R^n$, as long as a basis is provided.
	![[la_image17.png]]
#### Finding $(v)_S$ from $v$ and $S$
\Given a vector $v = (5, -1, 9)$ and a basis $S = \{v_1, v_2, v_3\}$ where $v_1 = (1, 2, 1)$, $v_2 = (2, 9, 0)$ and $v_3 = (3, 3, 4)$, the coordinate vector relative to $S$, $(v)_S$, is found by expressing $v$ as a linear combination of vectors in $S$ and, then forming $(v)_S$ from the coefficients in that linear combination.
	$$
	v = c_1v_1 + c_2v_2 + c_3v_3
	$$
	Expresses $v$ as a linear combination of vectors in $S$.$$
	(5, -1, 9) = c_1(1, 2, 1) + c_2(2, 9, 0) + c_3(3, 3, 4)
	$$Expresses the same thing in terms of components.
\
	The linear system$$
	\begin{matrix}
	5 = c_1 + 2c_2 + 3c_3 \\
	-1 = 2c_1 + 9c_2 + 3c_3 \\
	9 = c_1 + 0c_2 + 4c_3
	\end{matrix}
$$ Is formed by equating corresponding components, solving this system gives $c_1 = 1,\ c_2 = -1,\ c_3 = 2$. Therefore, $(v)_S = (1, -1, 2)$

- Finding $v$ from $(v)_S$ and $S$
	Given $(v)_S$ and $S$, a linear combination expressing $v$ can be constructed, e.g. if $(v)_S = (-1,\ 3,\ 2)$, then $v = -v_1 + 3v_2 + 2v_3$. If the basis $S$ is known, then $v_1,\ v_2$ and $v_3$ are known and evaluating this expression is simple.

## 4.6 - Dimension
- The dimension of a vector space is the cardinality of its basis.
	For example, $R^2$ has dimension $2$ and $P_4$, the vector space of polynomials of degree $\leq 4$ has degree $5$ because its standard basis is $\{1,\ x,\ x^2,\ x^3,\ x^4\}$. Additionally, the zero vector space is defined to have dimension $0$.
	
	The notation for dimension is $dim(V) = n$, e.g.:
	$$
	\begin{matrix}
	dim(R^2) = 2 \\
	dim(P_4) = 5 \\
	\ \ \ \ \ \ \ \ dim(M_{mn}) = mn
	\end{matrix}
	$$
- Let $V$ be a finite-dimensional vector space and let $\{v_1,\ ...,\ v_n\}$ be any basis.
	*(a)* If a set has more than $n$ vectors, then it is not linearly independent.
	*(b)* If a set has fewer than $n$ vectors, then it does not span $V$.

	Since the definition of a basis requires linear independence and spanning, all bases for a vector space must have $n$ vectors where $n$ is the dimension of the space, otherwise they would have more or fewer than $n$ vectors and, according to the previous theorem, that would imply that either (a) or (b) was false.

#### Dimension of a solution space
\	Given a homogenous system, such as
	$$
	\begin{matrix}
	2x_1 + 2x_2 - x_3 + x_5 = 0 \\
	-x_1 - x_2 + 2x_3 - 3x_4 + x_5 = 0 \\
	x_1 + x_2 -2x_3 - x_5 = 0 \\
	x_3 + x_4 + x_5 = 0
	\end{matrix}
	$$
	With solution
	$$
	\begin{matrix}
	x_1 = -s - t \\ x_2 = s \\ x_3 = -t \\ x_4 = 0 \\ x_5 = t
	\end{matrix}
	$$
	Which can be written in vector form as
	$$
	\begin{bmatrix}
	x_1 \\ x_2 \\ x_3 \\ x_4 \\ x_5
	\end{bmatrix}
	=
	\begin{bmatrix}
	-s - t \\ s \\ -t \\ 0 \\ t
	\end{bmatrix}
	$$
	Which is equivalent to
	$$
	\begin{matrix}
	v_1 = \begin{bmatrix}
	-1 \\ 1 \\ 0 \\ 0 \\ 0
	\end{bmatrix},\
	v_2 = \begin{bmatrix}
	-1 \\ 0 \\ -1 \\ 0 \\ 1
	\end{bmatrix} \\ \\
		
	\ \ \ \ \ \ \ \begin{bmatrix}
	x_1 \\ x_2 \\ x_3 \\ x_4 \\ x_5
	\end{bmatrix}
	= sv_1	+ tv_2
	\end{matrix}
	$$
	Here, an arbitrary vector in the solution space is expressed as a linear combination of vectors $v_1$ and $v_2$, showing that they span the solution space. Furthermore, either $v_1$ nor $v_2$ can be expressed as a linear combination of the other so $\{v_1,\ v_2\}$ is a linearly independent set and forms a basis for the solution space. The space has dimension $2$.
	
#### Plus/Minus theorem
\	Let $S$ be a nonempty set in a vector space $V$.
\	
	(a) If $S$ is linearly independent and $v$ is a vector in $V$ that is outside of $span(S)$, then the set $S \cup \{v\}$ is also linearly independent.
\	
	(b) If $v$ is a vector in $S$ expressible as a linear combination of other vectors in $S$, then $span(S - \{v\}) = span(S)$.
\
	Application of the plus/minus theorem:
		Show that $p_1 = 1 - x^2,\ p_2 = 2 - x^2,\ p_3 = x^3$ are linearly independent.
		$\{p_1,\ p_2\}$ is linearly independent since $p_1$ cannot be expressed as a scalar multiple of $p_2$; $p_1 = kp_2 \implies k = \frac{p_1}{p_2}$ but $p_2$ can equal $0$.
		\
		By the plus/minus theorem, $\{p_1,\ p_2\} \cup \{p_3\}$ is linearly independent if $p_3$ can't be expressed as a linear combination of $p_1$ and $p_2$ which is trivially shown since $p_3$ is of degree $3$ while $p_1$ and $p_2$ are of degree $1$ and $2$, respectively.
		![[la_image16.png]]


- Let $V$ be an $n$-dimensional vector space and $S$ be a set in $V$ with exactly $n$ vectors. $S$ is a basis for $V$ if and only if $S$ spans $V$ or $S$ is linearly independent.

	***Proof*** Assume that $S$ has $n$ vectors and spans $V$. If $S$ is a basis it will also be linearly independent. Assume that this is *not* true, meaning some vector $v$ in $S$ is a linear combination of vectors in $S$. Consider the set $S' = S - \{v\}$, it follows from the plus/minus theorem that $S'$ spans $V$. This is absurd since, as previously stated, a set of $m$ vectors from an $n$-dimensional vector space cannot span that space if $m < n$.

	Assume that $S$ has $n$ vectors and is linearly independent. If $S$ is a basis for $V$, then it also spans $V$. Assume that this is *not* true and that there is some vector $v$ in $V$ that is not in $span(S)$. Consider $S \cup \{v\}$, according to the plus/minus theorem, this set is linearly independent. This is absurd because a set of $m$ vectors from an $n$-dimensional vector space are not linearly independent if $m > n$.

	Thus it is proven that if a set $S$ of $n$ vectors from an $n$-dimensional vector space $V$ is linearly independent, then it must span $V$ and that, if $S$ spans $V$, then it must be linearly independent.
	
- Let $S$ be a finite set of vectors in a finite-dimensional vector space $V$ and let $B$ be some basis for $V$.
	*(a)* If $S$ spans $V$ but is not a basis for $V$, then $B \subset S$.
	*(b)* If $S$ is a linearly independent set that is not a basis for $V$, then $S \subset B$ 

- If $W$ is a subspace of a finite-dimensional vector space $V$, then:
	*(a)* $W$ is finite-dimensional
	*(b)* $dim(W) \leq dim(V)$
	*(c)* $W = V \iff dim(W) = dim(V)$ 


## 4.7 - Change of Basis

#### Coordinate maps
\	If $S = \{v_1, ..., v_n\}$ is a basis for a finite-dimensional vector space $V$ and $[v]_S = (c_1,\  ...,\ c_n)$ is the coordinate vector of $v$ relative to $S$, then the mapping
	$$
	v \rightarrow [v]_S
	$$
	Is a one-to-one correspondence between vectors in the general vector space $V$ and vectors in $R^n$. This correspondence is called the ***coordinate map*** from $V$ to $R^n$.

 #### Change of basis
\	If $v$ is a vector in a vector space $V$, what is the relationship between $[v]_S$ and $[v]_T$, where $S$ and $T$ are bases for $V$? For example, if $V = R^2$, $S = \{e_1,\ e_2\}$ and $T = \{(1,\ 1),\ (3,\ 5)\}$, What is the relationship between $[v]_S$ and $[v]_T$ if $v = (9,\ 12)$?
\
	- A general solution for $R^2$:
		Let $B = \{u_1,\ u_2\}$ and $B' = \{u_1',\ u_2'\}$ be bases for a $2$-dimensional vector space.
		A relationship between $[v]_B$ and $[v]_{B'}$ can be found by first finding $[u_1']_B$ and $[u_2']_B$ . Suppose $[u_1']_B = \begin{bmatrix}a \\ b\end{bmatrix}$ and $[u_2']_B = \begin{bmatrix}c \\ d\end{bmatrix}$
		Then
		$$
		\begin{matrix}
		u_1' = au_1 + bu_2 \\
		u_2' = cu_1 + du_2
		\end{matrix}
		$$
		Let $v$ be any vector in $V$ and let
		$$
		[v]_{B'} = \begin{bmatrix}k_1 \\ k_2\end{bmatrix}
		$$
		Then
		$$
		v = k_1u_1' + k_2u_2'
		$$
		Substituting $u_1'$ and $u_2'$ from previous definitions:
		$$
				v = k_1(au_1 + bu_2) + k_2(cu_1 + du_2)
		$$
		Or, expanding, collecting and factoring:
	$$
	v = (k_1a + k_2c)u_1 + (k_1b + k_2d)u_2
	$$
		Thus
		$$
		[v]_B = \begin{bmatrix}k_1a + k_2c \\ k_1b + k_2d\end{bmatrix}
		$$
		Or
		$$
		[v]_B = 
		\begin{Bmatrix}
		a & c \\ b & d
		\end{Bmatrix}
		\begin{bmatrix}
		k_1 \\ k_2
		\end{bmatrix}
		= \begin{Bmatrix}
		a & c \\ b & d
		\end{Bmatrix}
		\ [v]_{B'}
		$$
		In words, the coordinate vector relative to a base $B$ of a vector $v$ is equal to its coordinate vector relative to a base $B'$, multiplied by a matrix whose column vectors are the coordinate vectors, relative to $B$, of the vectors in $B'$ ($[u_1']_B$ and $[u_2']_B$).
\
		The matrix multiplying $[v]_{B'}$ is called the ***transition matrix*** from $B'$ to $B$ and is denoted $P_{B' \rightarrow B}$   - the choice of the letter $P$ is arbitrary.

#### Finding transition matrices
\	Example:
		Consider the bases $B = \{u_1,\ u_2\}$ and $B' = \{u_1',\ u_2'\}$ for $R^2$, where
		$$
		u_1 = (1, 0),\ u_2 = (0, 1)\ \ \ \ \ \ u_1' = (1, 1),\ u_2' = (2, 1), 
		$$
		Find the transition matrix $P_{B \rightarrow B'}$
		\
		$P_{B \rightarrow B'}$ is the matrix whose column vectors are the coordinate vectors, relative to $B'$, of the vectors in $B$.
\
		Observe that
		$$
		\begin{matrix}
		u_1 = -u_1' + u_2' \\
		u_2 = 2u_1' - u_2'
		\end{matrix}
		$$
		And so
		$$
		[u_1]_{B'} = \begin{bmatrix}-1 \\ 1\end{bmatrix}\ \ \ \ and \ \ \ \ [u_2]_{B'} = \begin{bmatrix}2 \\ -1\end{bmatrix}
		$$
		Hence
		$$
		P_{B \rightarrow B'} = \begin{bmatrix}-1 & 2 \\ 1 & -1\end{bmatrix}
		$$
	Example of rotation in $R^2$ through change of basis
	Take the point $(3.8,\ 3.5)$ represented as a coordinate vector relative to a rotated base, $B$. $$
	[v]_B = \begin{bmatrix}3.8 \\ 3.5\end{bmatrix}
	$$![[la_image15.png]]
	\
	To find $[v]_S$ where $S = \{e_1,\ e_2\}$, the basis vectors in $B$ are expressed in terms of $e_1$ and $e_2$:
	![[la_image11.png]]
	If $B = \{u_1,\ u_2\}$, then $u_1 = 0.99e_1 - 0.3e_2$ and $u_2 = 0.3e_1 + 0.99e_2$.
\
	To find $[v]_S$, the components of $[v]_B$ are multiplied by $u_1$ and $u_2$ expressed in terms of $e_1$ and $e_2$.
	$$
	[v]_S = 3.8(0.95e_1 - 0.3e_2) + 3.5(0.3e_1 + 0.95e_2)
	$$
	Through some manipulation this can be expressed as
	$$
	\begin{matrix}
	[v]_S = (3.8 \cdot 0.95e_1 - 3.8 \cdot 0.3e_2) + (3.5 \cdot 0.3e_1 + 3.5 \cdot0.95e_2) \\
	\ \ \ \ \ \ \ \ \ \ = (3.8 \cdot 0.95e_1 + 3.5 \cdot 0.3e_1) + (-3.8 \cdot 0.3e_2 + 3.5 \cdot0.95e_2)
	\end{matrix}
	$$
	Which, in vector form is
	$$
	\begin{bmatrix}
	3.8 \cdot 0.95e_1 + 3.5 \cdot 0.3e_1 \\ -3.8 \cdot 0.3e_2 + 3.5 \cdot0.95e_2
	\end{bmatrix}
	$$
	And is equivalent to
	$$
	\begin{Bmatrix}
	0.95e_1 & 0.3e_1 \\
	-0.3e_2 & 0.95e_2
	\end{Bmatrix}
	\begin{bmatrix}
	3.8 \\ 3.5
	\end{bmatrix}
	$$
	Which shows that $[v]_S$ is $[v]_B$ multiplied by the matrix whose column vectors are $[u_1]_S$ and $[u_2]_S$.
\
	Evaluating this gives the vector $\begin{bmatrix}4.66 \\ 2.185\end{bmatrix}$ which is the original point, translated from $B$ to $S$:
	![[la_image12.png]]
	*(It's a bit off because I only estimated the coordinates to begin with but it's close enough)*
	\
	\
	It's important to note that in applications of rotation matrices it might feel like you're translating from the standard base to the rotated base because the point is going from wherever it is to being rotated $30 \degree$ but, as the following animation shows, the opposite is true. This is because the rotation is done by first imagining that some $[v]_S$ is actually a $[v]_B$, i.e. "I have a point $(4, 5)$ in the standard basis that I want to rotate by $30 \degree$ so I'm going to imagine that it's actually $(4, 5)$ in the rotated-by-$30 \degree$ basis". Then you change the basis of this point from the rotated one back to the standard one.

![[rotation_edit.gif]]
### Invertibility of transition matrices
\
	If $B$ and $B'$ are bases for a finite-dimensional vector space $V$, then	$$
	(P_{B \rightarrow B'})(P_{B' \rightarrow B}) = P_{B \rightarrow B}
	$$Because matrix/matrix multiplication involves transforming the column vectors of a matrix according to a transition matrix. The result is that the basis vectors of $B$, relative to $B'$ are transformed from being relative to $B'$ to being relative to $B$ which has no net effect.

\	If $v = \begin{bmatrix}a \\ b\end{bmatrix}$ is an arbitrary vector then $(P_{B \rightarrow B})v = v$
	$P_{B \rightarrow B}$ is the identity matrix.
\
	It follows that $(P_{B \rightarrow B'})^{-1} = (P_{B' \rightarrow B})$ and $(P_{B' \rightarrow B}) = (P_{B \rightarrow B'})^{-1}$

- End of 4.7 "An Efficient Method for Computing Transition Matrices between Bases for $R^n$"

## 4.8 - Row Space, Column Space and Null Space

- Matrix subspaces
	If $A$ is an $m \times n$ matrix, then:
	- The subspace of $R^n$ spanned by the row vectors of $A$ is denoted $row(A)$ and is called the ***row space*** of $A$.
	- The subspace of $R^n$ spanned by the column vectors of $A$ is denoted $col(A)$ and is called the ***column space*** of $A$.
	- The subspace of $R^n$ which is the solution space of a homogeneous system $Ax = 0$ is denoted $null(A)$ and is called the ***null space*** of $A$.

- $Ax = b$ and $col(A)$
	
	Suppose that
	$$
	\begin{matrix}
	A = \begin{Bmatrix}
	a_{11} & a_{12} & \dots & a_{1n} \\
	a_{21} & a_{22} & \dots & a_{2n} \\
	\vdots & \vdots & \ddots & \vdots \\
	a_{m1} & a_{m2} & \dots & a_{mn} \\
	\end{Bmatrix}
	& and &
	x = \begin{bmatrix}
	x_1 \\ x_2 \\ \vdots \\ x_n
	\end{bmatrix}
	\end{matrix}
	$$
	If $\{c_1,\ \dots,\ c_n\}$ is the set of column vectors of $A$, then the product $Ax$ can be expressed as a linear combination of vectors from $\{c_1,\ \dots,\ c_n\}$:
	$$
	Ax = x_1c_1 + x_2c_2 +\ \dots\ + x_nc_n
	$$
	Thus the linear system $Ax = b$ can be expressed as
	$$
	x_1c_1 + x_2c_2 +\ \dots\ + x_nc_n = b
	$$
	Which shows that the system $Ax = b$ is consistent if and only if $b$ can be expressed as a linear combination of the column vectors in $A$.
	
	$Ax = b$ is consistent if and only if $b \in col(A)$.

- Relationship between $Ax = 0$ and $Ax = b$
	Given a linear system $Ax = 0$ with solution$$\begin{bmatrix}x_1 \\ x_2 \\ x_3 \\ x_4 \\ x_5 \\ x_6\end{bmatrix} = \begin{bmatrix}-3r - 4s - 2t \\ r \\ -2s \\ s \\ t \\ \frac13\end{bmatrix}$$
	$x$ may be expressed$$r\begin{bmatrix}-3 \\ 1 \\ 0\\0\\0\\0\end{bmatrix} + s\begin{bmatrix}-4 \\ 0 \\ -2 \\ 1 \\0\\0\end{bmatrix} + t\begin{bmatrix}-2 \\0\\0\\0\\1\\0\end{bmatrix} + \begin{bmatrix}0\\0\\0\\0\\0\\\frac13\end{bmatrix}$$
	$x - \begin{bmatrix}0\\0\\0\\0\\0\\\frac13\end{bmatrix}$ is the form of a general solution to $Ax = b$.
	
	As shown previously, the vectors being scaled by $r$, $s$ and $t$ form a basis for the solution space of the *homogeneous* system $Ax = 0$. This demonstrates the general theorem:
	
	- If $x_0$ is any solution of a consistent linear system $Ax = b$ and if $S = \{v_1, \dots, v_k\}$ is a basis for the null space of $A$, then every solution of $Ax = b$ can be expressed in the form $$x = x_0 + c_1v_1 + \dots + c_kv_k$$Conversely, for all choices of scalars $c_1, \dots, c_k$, the vector $x$ in the above formula is a solution of $Ax = b$.
	*Proof on p266*.

	![[la_image22.png]]

- Bases for Row, Column and Null spaces
	- If a given matrix $R$ is in row echelon form then its row vectors which contain leading $1$s form a basis for $row(A)$ and its column vectors which contain the leading $1$s form a basis for $col(A)$.

		For example, given $$R = \begin{bmatrix}1 & -2 & 5 & 0 & 3\\0 & 1 & 3 & 0 & 0 \\ 0 & 0 & 0 & 1 & 0 \\ 0&0&0&0&0\end{bmatrix}$$
		A basis for $row(R)$ is formed by$$\{(1, -2, 5, 0, 3),\ (0, 1, 3, 0, 0),\ (0, 0, 0, 1, 0)\}$$
		And a basis for $col(R)$ is formed by$$\{(1, 0, 0, 0),\ (-2, 1, 0, 0),\ (0, 0, 1, 0)\}$$

	- If $A$ and $B$ are row equivalent, $row(A) = row(B)$ and $null(A) = null(B)$
		***Proof*** Elementary row operations (scalar multiplication & linear combinations) scale and translate the row vectors to other vectors in the space, making $row(B)$ a subspace of $row(A)$ and conversely making $row(A)$ a subspace of $row(B)$, hence $row(A) = row(B)$.

		Elementary row operations on $A$ have no effect on the solution space of $Ax = b$, so the solution spaces of $Ax = 0$ and $Bx = 0$ are equal and thus $null(A) = null(B)$.

	- If $A$ and $B$ are row equivalent:
		(a) A given set of column vectors of $A$ is linearly independent if and only if the corresponding column vectors of $B$ are linearly independent.

		*which implies*

		(b) A given set of column vectors of $A$ forms a basis for $col(A)$ if and only if the corresponding column vectors of $B$ form a basis for $col(B)$.

	These results lead to strategies for finding bases for $row(A)$ and $col(A)$ comprised of row/col vectors from $A$:

- Basis for $col(A)$
	Because the corresponding column vectors of row equivalent matrices $A$ and $B$ form bases for $col(A)$ and $col(B)$ (and $col(A) = col(B)$), a basis for $col(A)$ comprised of column vectors from $A$ can be found by bringing $A$ to a row echelon form matrix $R$ and then selecting columns of $A$ which correspond to those in $R$ with leading $1$s.
	*See p270 for example*

- Basis for $row(A)$
	A basis for $col(A^T)$ forms a basis for $row(A)$.

- Basis for $span(S)$
	Construct the matrix $A$ whose column vectors are the vectors in $S$ and find a basis for $col(A)$. This is also a basis for $span(S)$.

## 4.9 - Rank, Nullity and the Fundamental Matrix Spaces

- $dim(row(A)) = dim(col(A))$
	***Proof*** $dim(row(A)) = dim(row(R))$ if $R$ and $A$ are row equivalent, the same is true for the column spaces. So it suffices to prove that $dim(row(R)) = dim(col(R))$, this is evident from inspection of a matrix in row echelon form:$$R = \begin{bmatrix}1 & 0 & 4 & 12 & 16 \\ 0 & 0 & 1 & 7 & 4 \\ 0 & 0 & 0 & 1 & 2 \\ 0 & 0 & 0 & 0 & 0\end{bmatrix}$$
	There is a row vector for every leading $1$ and there is a column vector for every leading $1$, so there are an equal number of basis vectors for $row(R)$ and $col(R)$, hence the dimensions are equal.

- $rank(A)$ and $nullity(A)$
	The dimensionality shared by $row(A)$ and $col(A)$ is called the rank of $A$ and is denoted $rank(A)$.

	$rank(null(A))$ is called the nullity of $A$ and is denoted $nullity(A)$.

	$rank(A)$ and $nullity(A)$ are found by respective methods:
	1. reducing $A$ to an echelon form to identify basis vectors for $row(A)$ or $col(A)$ by inspection.
	2. finding the general solution for $Ax = 0$ and expressing it in column vector form to identify the basis vectors.

- Maximum value for $rank(A)$ with $A$ as a $m \times n$ matrix
	$rank(A) \leq \min(m, n)$
	since
	$dim(row(A)) \leq m$,
	$dim(col(A)) \leq n$
	and
	$dim(col(A)) = dim(row(A))$.

- $rank(A) + nullity(A) = n\ \text{ [dimension theorem]}$
	***Proof*** $A$ has $n$ columns, meaning $Ax = 0$ has $n$ unknowns. The unknowns are categorised as leading and free variables. The number of leading variables is the number of leading $1$s in a row echelon form of $A$ which is also $rank(A)$, so $rank(A) + \text{[free variables]} = n$. The number of free variables is the number of parameters in the general solution and, since each parameter is matched with a basis vector, this is equal to $nullity(A)$. Hence, $rank(A) + nullity(A) = n$.

- If $Ax = b$ is a consistent linear system in $n$ unknowns, then the general solution of the system contains $n - rank(A)$ parameters.
	***Proof*** $n = rank(A) + nullity(A)$ so the claim is that $nullity(A)$ is the number of parameters in the general solution. This is evident by a previous theorem:

	- If $x_0$ is any solution of a consistent linear system $Ax = b$ and if $S = \{v_1, \dots, v_k\}$ is a basis for the null space of $A$, then every solution of $Ax = b$ can be expressed in the form $$x = x_0 + c_1v_1 + \dots + c_kv_k$$
	$c_1 \dots c_k$ are the parameters and each is paired with a basis vector for $null(A)$, this means there are $nullity(A)$ of them.

- The Fundamental Spaces of a Matrix
	- $row(A)$, $col(A)$, $null(A)$ and $row(A^T)$, $col(A^T)$, $null(A^T)$
	- $row(A^T) = col(A)$ and $col(A^T) = row(A)$ so these aren't considered interesting (sad face).

	- $row(A) \subset R^n$
	- $null(A) \subset R^n$
	- $col(A) \subset R^m$
	- $null(A^T) \subset R^m$

	- $rank(A) = rank(A^T$)

	- Dimensions of the four fundamental subspaces$$\begin{matrix}dim[row(A)] = rank(A) & dim[col(A)] = rank(A) \\ nullity(A) = n - rank(A) & nullity(A^T) = m - rank(A)\end{matrix}$$
	- Finding bases for the fundamental spaces
		The basis for $null(A)$ can be found from the general solution to $Ax = 0$.
		An efficient method for finding bases for the three other spaces is as follows:
		1. Construct the augmented matrix $[A \mid I]$ where $I$ is the $m \times m$ identity matrix.
		2. Perform row operations on $[A \mid I]$ to obtain $[R \mid E]$ where $R$ is the reduced row echelon form of $A$ and $E$ is the elementary matrix which transforms $A$ to $R$, in cases where $A$ is invertible $E = A^{-1}$.
		3. Find the bases for $row(A)$ and $col(A)$ by inspection of $R$.
		4. Identify the basis for $null(A^T)$ as the bottom $m - rank(A)$ rows of $E$.

		***Proof of 4.***
		$null(A^T)$ is the solution space for $A^Tx = 0$ which can be written $x^TA = 0^T$.
		The aforementioned matrices $A$, $R$ and $E$ are related by the equation$$EA = R$$
		Since $A$ has rank $r$ and size $m \times n$, the matrix $R$ has $rank(A)$ nonzero rows and $m - rank(A)$ zero rows. By (9) in Section 1.3 of The Book:$$\text{[$i^{th}$ row vector of $E$]}A = \text{[$i^{th}$ row vector of $R$]}$$
		Since the last $m - r$ row vectors of $R$ are zero, the last $m - r$ row vectors of $E$ are solutions to $x^TA = 0^T$ and hence lie in $null(A^T)$.
 
	
	- Geometric link between spaces
		- If $W$ is a subspace of $R^n$, then the set of all vectors in $R^n$ which are orthogonal to every vector in $W$ is called the ***orthogonal complement*** of $W$ and is denoted $W^\perp$.
			- $W \subset R^n$
			- $(W^\perp)^\perp = W$
			- $W \cap W^\perp = \{0\}$
		- If $L$ is a line through the origin then $L^\perp$ is the line perpendicular to $L$.
		- If $P$ is a plane through the origin then $P^\perp$ is the line containing the normal vector for $P$.
		 
		 $P^\perp$ isn't an orthogonal plane to $P$ because then their intersection would be a line and every vector in the line would be orthogonal to itself which is absurd since $(a, b) \cdot (a, b) \neq 0$ for $a, b \neq 0$.

		- $row(A) = null(A)^\perp,\ row(A) \subset R^n$
			If a vector is orthogonal to every vector in a basis then it is orthogonal to every linear combination of vectors in the basis.
			
			$null(A)$ is the set of all vectors $x$ for which $r \cdot x = 0$, hence all the vectors in $null(A)$ are orthogonal to all the vectors in $row(A)$, making $row(A)$ the orthogonal complement of $null(A)$.
		- $col(A) = null(A^T)^\perp,\ col(A) \subset R^m$
			By the last theorem, $row(A^T)$ is the orthogonal complement of $null(A^T)$, $row(A^T) = col(A)$, so $col(A) = null(A^T)^\perp$.

## 4.95 OPTIONAL: Overdetermined and Underdetermined Systems

- If $A$ is an $m \times n$ matrix then
	- If $m > n$, then the linear system $Ax = b$ is inconsistent for at least one vector $b$ in $R^n$ and the system is called ***Overdetermined***.
	- If $n > m$, then for each vector $b$ in $R^m$ the linear system $Ax = b$ is either inconsistent or has infinitely many solutions. The system is called ***Underdetermined***.
	*See proofs on p285*

