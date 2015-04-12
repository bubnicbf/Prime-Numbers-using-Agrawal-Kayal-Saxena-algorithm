# Prime-Numbers-using-Agrawal-Kayal-Saxena-algorithm
tests whether a number is prime is a polynomial-time algorithm based on an elementary theorem about Pascal triangles

Prime numbers are of fundamental importance in mathematics in general, and number theory in particular.
So it is of great interest to study different properties of prime numbers. Of special interest are
those properties that allow one to efficiently determine if a number is prime. Such efficient tests are also
useful in practice: a number of cryptographic protocols need large prime numbers.

Let PRIMES denote the set of all prime numbers. The definition of prime numbers already gives a
way of determining if a number n is in PRIMES: try dividing $n$ by every number $m ≤ \sqrt{n}$ —if any $m$
divides $n$ then it is composite, otherwise it is prime. This test was known since the time of the ancient
Greeks—it is a specialization of the Sieve of Eratosthenes (ca. 240 BC) that generates all primes less
then $n$. The test, however, is inefficient: it takes $Ω(\sqrt{n})$ steps to determine if $n$ is prime. An efficient
test should need only a polynomial (in the size of the $input = \log{n}$) number of steps. A property that
almost gives an efficient test is Fermat’s Little Theorem: for any prime number $p$, and any number a not
divisible by $p$, $a^{p−1} = 1 (mod p)$. Given an $a$ and $n$ it can be efficiently checked if $a^{n−1} = 1 (mod n)$ by using repeated squaring to compute the $(n − 1)^{th}$ power of $a$. However, it is not a correct test since many
composites n also satisfy it for some a’s (all a’s in case of Carmichael numbers). Nevertheless, Fermat’s Little Theorem became the basis for many efficient primality tests.

The theorem on which the test is based can be stated as follows: 

a number p is prime if and only if all the coefficients of the polynomial expansion of $(x − 1)^p − (x^p − 1)$
are divisible by $p$.

####For example, trying $p = 3$:

$$
(x − 1)^3 − (x^3 − 1) = (x^3 − 3x^2 + 3x − 1) − (x^3 − 1) = − 3x^2 + 3x
$$

And all the coefficients are divisible by 3 so 3 is prime.

#####Note

The task given here is related to the elementary theorem, not the actual AKS algorithm. Using the elementary theorem directly as a way of testing for primes is interesting as an exercise but impractical.
