
Integer division - if a and b are integers with b >= 1 then dividing a by b (a/b) yields unique integers q (quotient) and r (remainder) satisfying
	a = qb + r, 0 <= r <=b
	r is usually known as a mod(b); q as a / b

Prime number - an integer p is said to be prime if it has exactly TWO positive divisors: 1 and p.

Fundamental Theorem of Arithmetic - every integer n >= 2 has a factorisation as a product of prime powers: 
	n = p<sub>1</sub> <sup>e1</sup> p<sub>2</sub> <sup>e2</sup> ... p<sub>k</sub> <sup>ek</sup> 
	Where pi are distinct primes and ei are positive integers.

Congruence - let n be a positive integer and a and b are integers with 
(a mod n) = (b mod n) then a is congruent to b modulo n, written a === b (mod n)
	Two integers are congruent modulo n if they leave the same remainder when divided by n

Cayley Table

Z<sub>3</sub> 
[+, 0, 1, 2], [x, 0, 1, 2]
[0, 0, 1, 2], [0, 0, 0, 0]
[1, 1, 2, 0],  [1, 0, 1, 2]
[2, 2, 0, 1], [2, 0, 2, 1]

Multiplicative Inverse - if a  ∈ Z<sub>n</sub> then the multiplicative inverse of a mod n is an integer x ∈ Z<sub>n</sub> such that ax === 1 (mod n).
	An integer a has a multiplicative inverse modulo n if there exists an integer x such that a * x === 1 mod n

Invertible - if x exists then it is unique and a is said to be invertible; the inverse of a is written a<sup>-1</sup> .
If a ∈ Z<sub>n</sub> then a is invertible when gcd (a, n) = 1 

Modular division - if a, b ∈ Z<sub>n</sub> then the division of a by b (mod n) (written a/b) is the product of a and b<sup>-1</sup> (mod n) and is only defined if b is invertible (mod n).

1/3 = 1 x 3<sup>-1</sup> = 1 x 3 = 3

Public key encryption (asymmetric encryption) - scheme is one where each entity A has a public encryption key e and a corresponding private decryption key d, with the property that it is infeasible to compute d given e.

Impersonation attack - 

Main objective of public key encryption is confidentiality.

Easier to provide authentic public keys than it is to distribute secret keys securely.
Slower than symmetric key algorithms.


## RSA public-key encryption

e - known encryption exponent.
d - is the decryption exponent.
n - modulus.

Public and private keys are generated as follows:
	1. Generate two distinct primes p and q.
	2. Compute n = pq and Φ = (p - 1)(q - 1)
	3. Select a random integer e, 1 < e < Φ, such that gcd(e, Φ)= 1.
	4. Compute d, multiplicative inverse of e (mod Φ)
	5. A's public key is (n, e); A's private key is d.


![[Pasted image 20250430151839.png]]


### Efficient Algorithms

Euclidean algorithm - calculates the greatest common divisor of two integers, gcd(a, b), a >=b

1. set a<sub>0</sub> <-- a, b<sub>0</sub> <-- b
2. For steps i >= 1, while b<sub>i</sub> != 0 set:
	2 1 r<sub>r-1</sub> <-- a<sub>i-1</sub> mod b<sub>i-1</sub>
	2 2 a<sub>i-1</sub> <-- b<sub>i-1</sub> 
	2 3 b<sub>i</sub> <-- r<sub>i-1</sub>
3. when b<sub>i</sub> = 0, return a<sub>i</sub> 


