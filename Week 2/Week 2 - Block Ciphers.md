## Introduction

Symmetric key encryption - given a key pair (e, d), it is computationally "easy" to determine d knowing only e, and similarly to determine e from d.

![[Pasted image 20250425114359.png]]

Key distribution problem - how to exchange keys efficiently and securely.

## Block Ciphers


Block cipher - an encryption scheme which breaks up the plaintext into strings or blocks of fixed length n and encrypts one block at a time.

If n is too small then the cipher may be vulnerable to statistical analysis.
If n is too large then implementation difficulties occur due to the complexity of the cipher rising rapidly as the size of the block increases.

Block size and length of key are primary parameters in determining the characteristics of a cipher.

# Key space

The size of the key space is the number of encryption/decryption keys available.

Transposition cipher has a cipher block length of n, has n! encryption functions.

Keyspace needs to be large enough to prevent exhaustive search.

Calculation for brute-force attempts needed:
	if n is 30-bits
	2<sup>29</sup> number of operations will be needed.
		Meaning 2<sup>n-1</sup> attempts needed to exhaust the key.

On average, the correct key is found after searching half the keyspace.

# Security of block ciphers
To evaluate block cipher security it is assumed that an adversary:
	1. Has access to all data transmitted over the ciphertext channel.
	2. Knows all details of the encryption function except the key.

Classifications based on access:
	1. Ciphertext-only - no additional information.
	2. Known-plaintext - plaintext-ciphertext pairs are available.
	3. Chosen-plaintext - ciphertexts are available corresponding to plaintexts of the adversary's choosing.

Security measurements based on the complexity of the best known attack:
	1. Data complexity - the expected number of input data units required to break the cipher.
	2. Storage complexity - the expected number of storage units required.
	3. Processing complexity - the expected number of operations required to process input data/fill storage units.

Block cipher is computationally secure if k is large enough to preclude exhaustive search.
	And n is large enough to preclude exhaustive data analysis.

The more years a cipher has withstood testing the more reliable it becomes.

# Components of Block Ciphers

Substitution cipher - a block cipher which replaces groups of symbols with other groups of symbols.
	Example: a,b,c,d --> 1,2,3,4


Homophonic substitution cipher -  where single plaintext letter can map to multiple ciphertext symbols to make frequency analysis harder.

Homophonic substitution cipher makes statistical analysis of the ciphertext more difficult.

Polyalphabetical cipher can be seen as this:
	Alphabet: {A, B, C}
	Permutations: p<sub>1</sub|> = (A -> B, B -> C, C -> A), p<sub>2</sub> = (A -> C, B -> A, C -> B)
	Plaintext block "AB"
	Encrypted block "BA"


Transposition Cipher - re-orders the symbols in a block.

Function Composition - applying one function to the result of another, often to strengthen security.

![[Pasted image 20250426132934.png]]

Product Cipher -

Electronic Code-Book mode (ECB) -

Cipher Block Chaining (CBC) -

Cipher Feedback Mode (CFB) -

Output Feedback Mode (OFB) -

