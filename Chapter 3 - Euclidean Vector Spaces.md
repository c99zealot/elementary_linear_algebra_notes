## 3.2 - Norm, Dot Product and Distance in $R^n$

- If $v$ is a vector in $R^n$, then the ***norm*** (length, magnitude) of ***v*** is denoted $||v||$ and defined as:$$||v|| = \sqrt{v_1^2 + v_2^2 + \dots + v_n^2}$$- Properties of $||v||$
	(a) $||v|| \geq 0$
	(b) $||v|| = 0 \iff v = 0$
	(c) $||kv|| = |k| \times ||v||$
	
- $||v||^{-1}v$ is a unit vector sharing a direction with $v$, if $v$ is a vector in $R^n$ then $||v||^{-1}v$ is a normalisation of $v$.

- If $u$ and $v$ are nonzero vectors in $R^n$ and $\theta$ is the angle between them, then their ***dot product*** or ***Euclidean inner product*** is denoted $u \cdot v$ and defined as:$$u \cdot v = ||u||\ ||v|| \cos\theta$$
	From which it follows that$$\cos \theta = \frac{u \cdot v}{||u|| \ ||v||}$$
	Using this definition for $\cos\theta$ and the fact that $0 \leq \theta \leq \frac\pi2$, information about $\theta$ can be obtained by computing $u \cdot v$:
	- $u \cdot v = 0 \implies \cos\theta = 0 \implies \theta = \frac\pi2$
	- $u \cdot v < 0 \implies \cos\theta < 0 \implies \theta > \frac\pi2$
	- $u \cdot v > 0 \implies \cos\theta > 0 \implies \theta < \frac\pi2$

- Component form of $v \cdot u$
	Alternatively, $v \cdot u$ can be computed as $$v_1u_1 + \dots + v_nu_n$$*See derivation from law of cosines on p163*

	***Proof***
	$u \cdot v = ||u|| \hat u \cdot ||v|| \hat v$ *(hat means normalised)*
	$= ||u||\ ||v||\ \hat u \cdot \hat v$

	By the definition of the dot product, $\hat u \cdot \hat v$ must equal $\cos\theta$ for the two expressions to be equal.
	So we must prove that the dot product of two unit vectors is the cosine of the angle between them.

	Let $a$ and $b$ be unit vectors and let $p = \text{proj}_b(a)$, $c = a - p$, $d = b - a$.
	![[BwIE3.png]]

	$||p||^2 = ||a||^2 - ||c||^2$
	$= 1 - ||c||^2$

	$||c||^2 = ||d||^2 - (||b|| - ||p||)^2$
	$= ||d||^2 - (1 - ||p||)^2$
	$= ||d||^2 - 1 + 2||p|| - ||p||^2$

	$\implies ||p||^2 = 1 - ||d||^2 - 1 + 2||p|| - ||p||^2$
	$\implies 2||p|| = 2 - ||d||^2$

	$d = b - a \implies d_i = b_i - a_i$

	$||d||^2 = d \cdot d = \sum^id_i^2$
	$= \sum^i(b_i - a_i)^2$
	$= \sum^i{b_i^2} - 2b_ia_i + a_i^2$
	$= \sum^i{b_i^2} - \sum^i{2b_ia_i} + \sum^i{a_i^2}$ 
	$= ||b||^2 - \sum^i{2b_ia_i} + ||a||^2$
	$= 1 - \sum^i{2b_ia_i} + 1$
	$= 2 - 2\sum^i{b_ia_i}$

	$2||p|| = 2 - ||d||^2$
	$= 2 - (2 - 2\sum^i{b_ia_i})$
	$= 2\sum^i{b_ia_i}$
	$\implies ||p|| = \sum^i{b_ia_i}$
	$\blacksquare$
- Cauchy-Schwarz Inequality
	$$|u \cdot v| \leq ||u||\ ||v||$$
	This implies$$-1 \leq \frac{u \cdot v}{||u||\ ||v||} \leq 1$$
	This is important because the angle between vectors in $R^n$ is defined as $$\cos^{-1}(\frac{u \cdot v}{||u||\ ||v||})$$ which would be invalid were the inequality false since $\cos^{-1}$ has a domain of $[-1, 1]$.

- $Au \cdot v = u \cdot A^Tv$, $Av \cdot u = A^Tu \cdot v$
	***Proof*** for $A_{3 \times 3}$ :
	Let $$A = \begin{Bmatrix}a & b & c \\ d & e & f \\ g & h & i\end{Bmatrix}$$
	$$Au \cdot v = \begin{bmatrix}au_1 + bu_2 + cu_3 \\ du_1 + eu_2 + fu_3 \\ gu_1 + hu_2 + iu_3\end{bmatrix} \cdot v = \begin{matrix}\ \ \ \ au_1v_1 + bu_2v_1 + cu_3v_1 \\ +\ du_1v_2 + eu_2v_2 + fu_3v_2 \\ +\ gu_1v_3 + hu_2v_3 + iu_3v_3\end{matrix}$$
	Swapping $u$ and $v$ in the original dot product,
	$$Av \cdot u = \begin{bmatrix}av_1 + bv_2 + cv_3 \\ dv_1 + ev_2 + fv_3 \\ gv_1 + hv_2 + iv_3\end{bmatrix} \cdot u$$
	But this involves the dot product of $v_1$ the rows of $A$ instead of the columns as in the previous calculation, this is solved by taking the transpose:$$A^Tv \cdot u = \begin{bmatrix}av_1 + dv_2 + gv_3 \\ bv_1 + ev_2 + hv_3 \\ cv_1 + fv_2 + iv_3\end{bmatrix} \cdot u$$
	Then, multiplying by $u$ :$$
	\begin{bmatrix}av_1 + dv_2 + gv_3 \\ bv_1 + ev_2 + hv_3 \\ cv_1 + fv_2 + iv_3\end{bmatrix} \cdot u = \begin{matrix}\ \ \ \ av_1u_1 + dv_2u_1 + gv_3u_1 \\ +\ bv_1u_2 + ev_2u_2 + hv_3u_2 \\ +\ cv_1u_3 + fv_2u_3 + iv_3u_3\end{matrix}$$
	Which is equal to the previous sum. This extends to $n \times n$ matrices and vectors in $R^n$.
	$Av \cdot u = A^Tu \cdot v$ is evident from the commutative property of the dot product.

## 3.3 - Orthogonality

- Two nonzero vectors are said to be ***orthogonal*** or perpendicular if $u \cdot v = 0$

- Vector equation for lines and planes
	Lines and planes can be defined using two vectors; a line is the set of all points in $R^2$ orthogonal to a vector, $n$, called the ***normal vector***. If the tail of $n$ is $P_0$, then the equation $n \cdot \overrightarrow{P_0P} = 0$, where $P$ is an arbitrary 2D vector, describes all the points on the line. If $\overrightarrow{P_0P}$ and $n$ are in $R^3$ then it describes a plane.

	With $\overrightarrow{P_0P} = (x - x_0, y - y_0)$ and $n = (a,\ b)$ : $$(x - x_0, y - y_0) \cdot (a, b) = a(x - x_0) + b(y - y_0) = 0$$
	If $P$, $P_0$ and $n$ are in $R^3$ then $$a(x - x_0) + b(y - y_0) + c(z - z_0) = 0$$
	These are the ***point-normal*** forms for equations describing lines and planes. Point-normal forms expand and simplify to the familiar homogeneous forms $ax + by + c = 0$ and $ax + by + cz + d = 0$.

- Orthogonal projections
	If $u$ and $a \neq 0$ are vectors in $R^n$, then $u$ is uniquely expressed as $w_1 + w_2$ where $w_1$ is a scalar multiple of $a$ and $w_2$ is orthogonal to $a$.
	***Proof***
	We have $w_1 = ka$, so $u = ka + w_2$
	$u \cdot a = (ka + w_2) \cdot a$
	$= ka \cdot a + w_2 \cdot a$
	$= k||a||^2 + w_2 \cdot a$
	
	$w_2 \cdot a = 0 \implies u \cdot a = k||a||^2 \implies k = \frac{u \cdot a}{||a||^2}$

	Then $w_1 = \frac{u \cdot a}{||a||^2}a$ and $w_2 = u - \frac{u \cdot a}{||a||^2}a$
	
	$w_2 \cdot a = u \cdot a - \frac{u \cdot a}{||a||^2}a \cdot a$
	$= u \cdot a - \frac{u \cdot a}{||a||^2}||a||^2 = u \cdot a - u \cdot a = 0$
	
	Hence, there exists a scalar $k$ such that, for any two vectors $u$ and $a$, $u$ is uniquely expressed as $ka + w_2$ where $w_2$ is orthogonal to $a$.

	Simply stated, every vector is expressible as a sum of orthogonal vectors. Expressing $u$ as $w_1 + w_2$ is called ***decomposing*** it into $w_1$ and $w_2$.

	$w_1$ and $w_2$ are called **vector components** of $u$ and $w_1$ is the vector component *along* $a$ while $w_2$ is the vector component *orthogonal* to $a$. $w_1$ is also referred to as the ***projection of $u$ along $a$*** and is denoted $\text{proj}_au$.
	
	 $$w_1 = \text{proj}_au = \frac{u \cdot a}{||a||^2}a$$$$w_2 = u - \text{proj}_au$$

- The 2D projection matrix
	If $L$ is the line making an angle $\theta$ with the positive $x\text{-axis}$ then the projections of $e_1$ and $e_2$ onto $L$ are found by taking $a$ to be a unit vector along $L$, and projecting $e_1$ and $e_2$ onto that, since $||e_1|| \leq 1$ and $e_2 \leq 1$.$$\text{proj}_ae_1 = \frac{e_2 \cdot a}{||a||^2}a\text{, }\text{proj}_ae_2 = \frac{e_2 \cdot a}{||a||^2}a$$
	$$\begin{matrix}||a||^2 = \cos^2\theta + \sin^2\theta = 1 \\
	e_1 \cdot a = (1, 0) \cdot (\cos\theta, \sin\theta) = \cos\theta \\
	\text{proj}_ae_1 = (\cos\theta)(\cos\theta, \sin\theta) = (\cos^2\theta, \sin\theta\cos\theta) \end{matrix}$$
	Similarly, because $e_2 \cdot a = \sin\theta$ :
	$$\text{proj}_ae_2 = (\sin\theta \cos\theta, \sin^2\theta)$$
	The standard matrix for $T : R^2 \rightarrow R^2$ mapping each point in $R^2$ to a point on $L$ is$$\begin{Bmatrix}T(e_1) \mid T(e_2)\end{Bmatrix} = \begin{Bmatrix}\text{proj}_ae_1 \mid \text{proj}_ae_2 \end{Bmatrix} = \begin{Bmatrix} \cos^2\theta & \sin\theta\cos\theta \\ \sin\theta\cos\theta & \sin^2\theta\end{Bmatrix}$$
	This matrix is commonly denoted $P_\theta$ and alternatively written as:$$\begin{Bmatrix} \cos^2\theta & \frac12\sin2\theta \\ \frac12\sin2\theta & \sin^2\theta\end{Bmatrix}$$

- Reflections about lines through the origin
	$H_\theta : R^2 \rightarrow R^2$, the mapping between each point in $R^2$ and its reflection about a line $L$ through the origin making an angle of $\theta$ with the positive $x\text{-axis}$ can be derived as $P_\theta$ was or alternatively derived from $P_\theta$ :

	It can be observed from the below figure...
	![[Pasted image 20241130201135.png]]
	...that $P_\theta x - x = \frac12(H_\theta x - x)$
	Equivalently, $H_\theta x = (2P_\theta - I)x$, which shows that $H_\theta = 2P_\theta - I$.g

	From the definition of $P_\theta$ :$$H_\theta = \begin{Bmatrix}\cos2\theta & \sin2\theta \\ \sin2\theta & -\cos2\theta\end{Bmatrix}$$

- Norm of a projection
	$$||\text{proj}_au|| = \frac{|u \cdot a|}{||a||}$$
	Alternatively,$$||\text{proj}_au|| = ||u||\ |\cos\theta|\text{, where $\theta$ is angle between $u$ and $a$}$$
- Pythagoras in $R^n$
	The theorem of Pythagoras generalises to $R^n$, that is $$||v||^2 = v_1^2 + \dots + v_n^2$$
	***Proof***
	Let $u$ and $v$ be orthogonal vectors in $R^n$
	$$||u + v||^2 = (u + v) \cdot (u + v) = ||u||^2 + 2(u \cdot v) + ||v||^2$$
	Because $u \cdot v = 0$, $2(u \cdot v) = 0$ and the proof is complete.


- Distance between a point and a line/plane
	![[Pasted image 20241130210019.png]]
	If $Q$ is a point in the plane and $n$ is a vector normal to the plane and with its tail at $Q$ then $D$, the distance between $P_0$ and the plane, is equal to the norm of the orthogonal projection of $P_0$ onto $\overrightarrow{QP_0}$
	$$D = ||\text{proj}_n{\overrightarrow{QP_0}}|| = \frac{|\overrightarrow{QP_0} \cdot n|}{||n||}$$$$\begin{matrix}\overrightarrow{QP_0} = (x_0 - x_1, y_0 - y_1, z_0 - z_1) \\ \overrightarrow{QP_0} \cdot n = a(x_0 - x_1) + b(y_0 - y_1) + c(z_0 - z_1) \\ ||n|| = \sqrt{a^2 + b^2 + c^2} \end{matrix}$$
	So$$D = \frac{|a(x_0 - x_1) + b(y_0 - y_1) + c(z_0 - z_1)|}{\sqrt{a^2 + b^2 + c^2}}$$
	Which expands to$$D = \frac{|ax_0 + by_0 + cz_0 - ax_1 - by_1 - cz_1|}{\sqrt{a^2 + b^2 + c^2}}$$
	Let $d = -ax_1 - by_1 - cz_1$:$$D = \frac{|ax_0 + by_0 + cz_0 + d|}{\sqrt{a^2 + b^2 + c^2}}$$
	This is the formula for the distance from a point to a plane, The formula for the distance from a point to a line is the same, just with $c = 0$.

- Distance between two planes
	Using the previous formula, a formula for the distance between two parallel planes can be derived as the distance between one plane and a point in the other plane.

	Let the equations$$\begin{matrix}a_0x + b_0y + c_0z + d_0 = 0 \\ a_1x + b_1y + c_1z + d_1 = 0\end{matrix}$$
	Describe the two planes. $(-\frac{d_0}{a_0}, 0, 0)$ is the point in plane $0$ at which it crosses the $x\text{-axis}$. The distance between this point and plane $1$ is (via the previous formula & some simplification)$$D = \frac{|d - d_0|}{\sqrt{a_1^2 + b_1^2 + c_1^2}}$$
	Similar to previous derivations, this leads to a formula for the distance between two parallel lines by taking $c_1 = 0$.

## 3.4 - The Geometry of Linear Systems

- Alternate vector equations for lines and planes
	- Line
		A general point in a line $L$ can be defined $x = x_0 + tv$ where $v$ is a vector parallel to $L$, $x_0$ is a point along the line and $t$ is a parameter in $[-\infty, \infty]$.
	- Plane
		A general point in a plane $P$ can be defined $x = x_0 + t_1v_1 + t_2v_2$, where $v_1$ and $v_2$ are vectors parallel to $P$, $x_0$ is a point in the plane and $t_1$ and $t_2$ are parameters in $[-\infty, \infty]$.
		
- Vector equation for a line segment
	A general point in a line segment can be defined $x = x_0 + t(x_1 - x_0)$, where $x_0$ and $x_1$ are the points at each end of the line segment and $t$ is a parameter in $[0, 1]$.
	
- Geometric interpretation of the solution set for a homogeneous linear system
	A homogeneous system $Ax = 0$ can be expressed as:$$\begin{bmatrix}r_1 \cdot x\\ \vdots \\ r_n \cdot x\end{bmatrix} = \begin{bmatrix}0 \\ \vdots \\ 0\end{bmatrix}$$Where $r_1 \dots r_n$ are the row vectors of $A$. The dot product of each row vector with $x$ is $0$ which shows that the solution set of a homogeneous linear system is the set of all vectors which are orthogonal to every row vector of the coefficient matrix.
## 3.5 - Cross Product

The cross product is defined for vectors $u$ and $v$, both $R^3$, as $u \times v$ which is a vector in $R^3$ orthogonal to both $u$ and $v$.$$u \times v = (u_2v_3 - u_3v_2,\ u_3v_1 - u_1v_3,\ u_1v_2 - u_2v_1)$$
The above can be obtained analytically using the fact that $w \cdot v = 0$ and $w \cdot u = 0$, where $w = u \times v$. Derivation: https://www.youtube.com/watch?v=BvfcBoFZUkY

- Important properties of the cross product
	(a) $u \times v = -(v \times u)$
	(b) $||u \times v||^2 = ||u||^2||v||^2 - (u \cdot v)^2 \text{ [Lagrange's identity]}$
	(c) $u \times 0 = 0$
	(d) $u \times u = 0$
	
	*See p139 for proofs and additional properties*

- The cross product as a (sort of) determinant
	Observe that in the definition of the cross product the following is true:$$(u \times v)_1 = (u_2v_3 - u_3v_2) = \begin{vmatrix}u_2 & u_3 \\ v_2 & v_3\end{vmatrix}$$
	This holds for the other components of $u \times v$ and they are minors of the below matrix:$$\begin{vmatrix}a & b & c \\ u_1 & u_2 & u_3 \\  v_1 & v_2 & v_3\end{vmatrix}$$
	*$a$, $b$ and $c$ are arbitrary since the relevant minors are all along the first row*

	The full cross product can be thought of as the cofactor expansion along the first row of the following determinant:$$\begin{vmatrix}i & j & k \\ u_1 & u_2 & u_3 \\  v_1 & v_2 & v_3\end{vmatrix}$$
	Where $\{i, j, k\}$ forms the standard basis for $R^3$.

	Cofactor expansion along the first row produces the following result:$$\begin{vmatrix}u_2 & u_3 \\ v_2 & v_3\end{vmatrix}i - \begin{vmatrix}u_1 & u_3 \\ v_1 & v_3\end{vmatrix}j + \begin{vmatrix}u_1 & u_2 \\ v_1 & v_2\end{vmatrix}k$$
	Which is equal to the cross product.

	*The use of $i, j, k$ as elements of a determinant doesn't align with the standard properties of determinants and the idea serves as more of a mnemonic than a theorem*

- Norm of the cross product
	Starting from Lagrange's identity: $$\begin{matrix}||u \times v||^2 = ||u||^2||v||^2 - (u \cdot v)^2\\ = ||u||^2||v||^2 - ||u||^2||v||^2\cos^2\theta \\\text{by the angle definition of the dot product:}\\= ||u||^2||v||^2(1 - \cos^2\theta) = ||u||^2||v||^2\sin^2\theta\\\\\text{so}\\||u \times v||^2 = ||u||^2||v||^2\sin^2\theta\\\text{which implies}\\\sqrt{||u \times v||^2} = \sqrt{||u||^2||v||^2\sin^2\theta}\\= \sqrt{||u||^2}\sqrt{||v||^2}\sqrt{\sin^2\theta}\\\text{and finally,}\\||u \times v|| = ||u||\ ||v||\sin\theta\end{matrix}$$
	$||v||\sin\theta$ is the height of the parallelogram determined by $u$ and $v$:
	
	![[la_image21.png]]

	The area of this parallelogram is equal to its height, $||v||\sin\theta$, multiplied by its base, $||u||$. As was just demonstrated, this product is equal to $||u \times v||$. This is the geometric interpretation of the cross product.

- The scalar triple product
	For three vectors in $R^3$, their ***scalar triple product*** is defined as:$$\text{scalar triple product} = u \cdot (v \times w) = \begin{vmatrix}u_1 & u_2 & u_3 \\ v_1 & v_2 & v_3 \\ w_1 & w_2 & w_3\end{vmatrix}$$
	The determinant follows from the faux determinant used to define the cross product:$$u \cdot (v \times w) = u \cdot \begin{pmatrix}\begin{vmatrix}v_2 & v_3 \\ w_2 & w_3\end{vmatrix}i - \begin{vmatrix}v_1 & v_3 \\ w_1 & w_3\end{vmatrix}j + \begin{vmatrix}v_1 & v_2 \\ w_1 & w_2\end{vmatrix}k\end{pmatrix}$$Which equals$$\begin{vmatrix}v_2 & v_3 \\ w_2 & w_3\end{vmatrix}u_1 - \begin{vmatrix}v_1 & v_3 \\ w_1 & w_3\end{vmatrix}u_2 + \begin{vmatrix}v_1 & v_2 \\ w_1 & w_2\end{vmatrix}u_3$$
	Which, reversing the cofactor expansion, equals$$\begin{vmatrix}u_1 & u_2 & u_3 \\ v_1 & v_2 & v_3 \\ w_1 & w_2 & w_3 \\\end{vmatrix}$$
	From this it follows that$$u \cdot (v \times w) = v \cdot (w \times u) = w \cdot (u \times v)$$
	Since swapping factors in the product corresponds to swapping rows in the determinant which does not affect the determinant.

- Geometric interpretation of determinants
	(a) The absolute value of $$\begin{vmatrix}u_1 & u_2 \\ v_1 & v_2\end{vmatrix}$$
	Is equal to the area of the parallelogram in $2\text{-space}$ determined by the vectors $u = (u_1, u_2)$ and $v = (v_1, v_2)$. This quantity is $||u \times v||$.

	(b) The absolute value of $$\begin{vmatrix}u_1 & u_2 & u_3\\ v_1 & v_2 & v_3 \\ w_1 & w_2 & w_3\end{vmatrix}$$
	Is equal to the area of the parallelepiped in $3\text{-space}$ determined by the vectors $u = (u_1, u_2, u_3)$, $v = (v_1, v_2, v_3)$ and $w = (w_1, w_2, w_3)$. This quantity is $|u \cdot (v \times w)|$

	*See p197 for proofs*

- Coplanarity of $3$ vectors via the scalar triple product
	From the previous result, the scalar triple product is the signed volume of the parallelepiped described by three vectors. This volume is $0$ if and only if these vectors are co-planar.
	
	Thus, we have$$u \cdot (v \times w) = \begin{vmatrix}u_1 & u_2 & u_3\\ v_1 & v_2 & v_3 \\ w_1 & w_2 & w_3\end{vmatrix} = 0$$
	Whenever $u$, $v$ and $w$ are coplanar.