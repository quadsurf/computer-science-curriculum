**EXERCISE:**

Reduce the following big-O expressions. If they can't be reduced, explain why.

1. O(5555593939) + O(n^2) + O(n * n * n)

	Can be reduced to O(n^3).

2. O(93939283940) + O(8274920484) + O(12)

	Can be reduced to O(1).

3. O(n * n)

	Is already reduced (unless you'd prefer to write this as O(n^2)).

4. O(3n + 2n + 5n + 9n)

	Can be reduced to O(n).

5. O(n^3 + n) + O(2^n)

	Can be reduced to O(2^n).

6. O(n * log(n) + log(n))

	Can be reduced to O(n * log(n)).

7. O(n^n)

	Is already reduced.

Which is the faster big O runtime (Make sure to reduce both expressions first):

1. O(n + n^2 + 5) or O(3n + 70000000)

	O(n^2) is slower than O(n).

2. O(n * log(n)) or O(n^2)

	O(n * log(n)) is faster than O(n^2).
	
3. O(n^n) or (n^50000)

	O(n^n) is slower than O(n^50000).

4. O(1) or O(9999999999999)

	O(1) and O(1) are equivalent.

5. O(n * n * 5 * n) or O(n^2)

	O(n^3) is slower than O(n^2).

**CHALLENGES:**

1. What is the complexity of each of the functions in [this graph](https://www.desmos.com/calculator/e6335rf6ao)?

	Orange is O(x), red is O(x^(1/2)), blue is O(x^2), purple is O(1).

2. Prove, using the definition of big-O, why constants don't matter in the notation (e.g. why O(2n) is the same as O(n)).

	Suppose f = O(A * g) for some functions f, g, and some constant A. By definition, there exist constants C and t such that f(x) < C * A * g(x) for x > t. But C * A is again a constant, which we can call D; so f(x) < D * g(x) for x > t. By definition, then, f = O(g).

3. Prove that big-O notation is _transitive_. In other words, if `f(x)` is `O(g(x))`, and `g(x)` is `O(h(x))`, then `f(x)` is `O(h(x))`.

	f = O(g) implies that there exist constants C<sub>0</sub> and t<sub>0</sub> such that f(x) < C<sub>0</sub> * g(x) for x > t<sub>0</sub>. g = O(h) implies that there exist constants C<sub>1</sub> and t<sub>1</sub> such that g(x) < C<sub>1</sub> * h(x) for x > t<sub>1</sub>.
	
	Let C = C<sub>0</sub> * C<sub>1</sub>, and let t = max(t<sub>0</sub>, t<sub>1</sub>). Then for all x > t, f(x) < C<sub>0</sub> g(x) < C<sub>0</sub> * C<sub>1</sub> h(x) = C * h(x). So f(x) < C * h(x) for x > t, and therefore by definition f = O(h).