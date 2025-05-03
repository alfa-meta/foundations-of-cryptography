Greatest Common Divisor - gcd(a, b), is the largest positive integer that divides both a and b, with the special case gcd(0, 0).

Least Common Multiple - lcm(a, b), is the smallest non-negative integer divisible by both a and b.

Relatively prime - two integers a and b, if gcd(a, b) = 1

Keystream - is a sequence of symbols e<sub>1</sub>e<sub>2</sub> e<sub>3</sub> ... e<sub>i</sub> ∈ K

Stream cipher - takes the plaintext string m<sub>1</sub>m<sub>2</sub>m<sub>3</sub> ... and produces a ciphertext string c<sub>1</sub>c<sub>2</sub>c<sub>3</sub> ... where c<sub>i</sub> = E<sub>ei</sub>(m<sub>i</sub>) 

If d<sub>i</sub> denotes the inverse of e<sub>i</sub> then D<sub>di</sub> (c<sub>i</sub>) = m<sub>i</sub> 

## The Vernam Cipher 

c<sub>i</sub> = m<sub>i</sub> ⊕ k<sub>i</sub>

m<sub>i</sub> = m<sub>i</sub> ⊕ k<sub>i</sub> 

XOR can be used for both encryption and decryption because applying it twice will reverse the previous process.

When the keystream digits are generated randomly, and never used again, the Vernam cipher is called a one-time pad.


## Synchronous stream ciphers

Synchronous stream cipher - keystream is generated independently of the plaintext and the ciphertext.

Binary additive stream cipher - is a synchronous stream cipher where the output function h is the XOR function.

Encryption process:
	σ<sub>i+1</sub> = f(σ<sub>i</sub>, k),
	z<sub>i</sub> = g(σ<sub>i</sub>, k),
	c<sub>i</sub> = h(z<sub>i</sub>, m<sub>i</sub>)

σ<sub>0</sub> is the initial state, perhaps determined from the key k;
f is the next-state function;
g is the function that produces the keystream z<sub>i</sub>;
h is the output function which combines the keystream and plaintext m<sub>i</sub> to produce ciphertext c<sub>i</sub>.

Properties of Synchronous stream ciphers:
	Synchronisation - sender receiver must be synchronised - using the same key and the same state (position in the keystream). If synchronisation is lost then decryption fails until it is regained, perhaps by special markers in the ciphertext, re-initialisation, or exhaustive search of keystream positions.
	No error propagation - ciphertext digit that is modified, but not deleted, does not affect the decryption of other ciphertext digits.
	Active Attacks - inserting, deleting, or replaying ciphertext digits leads to immediate loss of synchronisation and may be detected.

Due to no error propagation active attacker can change ciphertext digits allowing them to get clues about the key.

Asynchronous stream cipher - is where the key-stream is generated as a function of the key and a fixed number (t) of previous ciphertext digits.


Self synchronising stream cipher:
	σ<sub>i</sub> = (c<sub>i-t</sub>, c<sub>i-t+1</sub>, ..., c<sub>i-1</sub>),
	z<sub>i</sub> = g(σ<sub>i</sub>, k),
	c<sub>i</sub> = h(z<sub>i</sub>, m<sub>i</sub>)

σ<sub>0</sub> is the initial state
k is the key;
g is the function which produces the keystream z<sub>i</sub>;
h is the output function.

## Linear Feedback Shift Registers (LFSR)

1. LFSRs can be implemented in hardware.
2. Can produce a large period (sequence before it repeats itself).
3. Produce sequences with good statistical properties.
4. LFSR of length L consists of L stages each capable of storing one bit and having one output.

![[Pasted image 20250503134741.png]]


Connection Polynomial:
LFSR is denoted (L, C(D)), where C(D) is the connection polynomial, C(D) = 1 + c<sub>1</sub>D + c<sub>2</sub>D<sup>2</sup> + ... + C<sub>L</sub>D<sup>L</sup>
