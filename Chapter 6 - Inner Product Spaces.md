
- An inner product on a real vector space $V$ is a function that associates a real number $\langle u, v \rangle$ with each pair of vectors in $V$ such that the following axioms are satisfied for all vectors $u$, $v$, and $w$ in $V$ and all scalars $k$.

	1. $\langle u, v \rangle = \langle v, u \rangle$
	2. $\langle u + v, w \rangle = \langle u + w, v + w \rangle$
	3. $\langle ku, v \rangle = k\langle u, v \rangle$
	4. $\langle v, v \rangle \geq 0\ \text{and}\ \langle v, v \rangle = 0 \iff v = 0$

- The inner product axioms are based on the properties of the dot product which means the dot product is an inner product

- Using the inner product as a more general definition of the dot product, the norm of a vector and the distance between two vectors can be more generally defined for vectors in an inner product space.
	
	$||v|| = \sqrt{\langle v, v \rangle}$
	$d(u, v) = ||u - v|| = \sqrt{\langle u - v, u - v \rangle}$

	With a more general definition of the norm we now also have a more general definition of a unit vector, $||v|| = \sqrt{\langle v, v \rangle} = 1$.

- All the properties of norm and distance when they are defined using the dot product hold when they are defined using the inner product, $|k|||v|| = ||kv||$, etc.

- Weighted inner product
	An example of an inner product other than the dot product is a **weighted Euclidean inner product**. It is defined as the Euclidean inner product between two vectors with each term being multiplied by a weight:

	$\langle u, v \rangle = w_1u_1v_1 + \dots + w_nu_nv_n$

	An arithmetic average can be represented as a weighted Euclidean product, for example:
	
	To approximate the average roll of a six-sided die one could throw the die $n$ times, recording the frequency of each result, then calculate the following to compute the average roll: $(f_1 + 2f_2 + 3f_3 + 4f_4 + 5f_5 + 6f_6)n^{-1}$

	Where $f_n$ is the frequency at which the die lands on the side displaying $n$.
	Notice that $f_1 + 2f_2 + 3f_3 + 4f_4 + 5f_5 + 6f_6$ is the dot product between the two vectors $(f_1, f_2, f_3, f_4, f_5, f_6)$ and $(1, 2, 3, 4, 5, 6)$ and that the average can be seen as the weighted Euclidean inner product between those two vectors with each term having a weight of $n^{-1}$.

	Note that the weights do not have to be equal as they are here.

