## Basic Definitions for Cryptography

Kryptos - hidden

Grafo - write

Cryptography - study of message secrecy.
	Study of mathematical techniques related to aspects of information security such as confidentiality, data integrity, entity authentication, and data origin authentication.

Cryptanalysis - is the study of mathematical techniques for attempting to defeat cryptographic techniques.

Cryptanalyst - is someone who engages in cryptanalysis.

Cryptology - is the study of cryptography and cryptanalysis.

Cryptosystem - is a general term referring to a set of cryptographic primitives to provide information security services.

Entity (party) - is someone or something which sends, receives or manipulates information. 

Sender (Alice) - is an entity which is the legitimate transmitter of information.

Receiver (Bob) - is an entity which is the intended recipient of information.

Adversary - which is neither the sender nor receiver and which tries to defeat the information security service in use.

Channel - is a means of conveying information from one entity to another.

Unsecured Channel - is one which any entity, including the adversary, can reorder, delete, insert or read information.

Secured Channel - is one from which an adversary does not have the ability to reorder, delete, insert or read.
	A channel can be secured by use of cryptographic techniques, the subject of this module.

Confidentiality - keeping the content of information from all but those authorised to have it- either by physical protection or the use of algorithms to render data unintelligible.

Data Integrity - is ensuring that data has not been subject to unauthorised alterations - the ability to detect alterations is necessary to assure integrity.

Authentication - process of verifying the identity of a user, device, or system and ensuring that messages come from a legitimate source.
	Relates to identification of both entities and information.
	
Non-repudiation - is preventing an entity from denying previous comments or actions.

Cryptographic Primitive - tools to provide information security; such as 

Criteria for evaluating primitives include:
	Level of Security - amount of work necessary to defeat the intended objective.
	Functionality - what the primitive actually does; typically it has one job.
	Methods of operation - a given primitive may provide different functionality depending on how it is used.
	Performance - efficiency of a primitive in a particular mode of operations.
	Ease of implementation - how difficult it is to realise the primitive in a practical instantiation

## Mathematical Preliminaries:

Domain - is the input of a function.

Co-domain - is the output of a function.

Example: X = {a, b, c}, Y = {1, 2, 3}
y = f(a) = 2; a is domain, 2 is co-domain.
y = f(b) = 3; b is domain, 3 is co-domain.
y = f(c) = 1; c is domain, 1 is co-domain.

Sets - a set consists of distinct elements.
	A set X might consist of the elements a, b, c denoted X = {a, b, c}

Membership - if an element of a is a member of a set X then we write a ∈ X;
	Conversely if a is not in X then we write a ∉ X.

Function - defined by two sets X and Y and a rule f which assigns to each element in precisely one element in Y.
	i.e f : X -> Y

Image of an element - If an element of X, x ∈ X, then the image of x is the element y ∈ Y, which the rule f associates with x.
	i.e y = f(x)

Pre-image - if y ∈ Y then the pre-image of y is an element x ∈ X for which f(x) = y.

Image - the set of all elements in Y which have at least one pre-image is called the image of f, denoted Im(f).

![[Pasted image 20250424000812.png]]

One-to-one - a function is 1-1 if each element in the co-domain Y is the image of at most one element in the domain X.

Onto - function where each element in the co-domain Y is the image of at least one element in the domain, i.e. f:X -> Y is onto if Im(f) = Y.

Injection - a one to one function.

Surjection - an onto function.

Bijection - function that is both a one-to-one function and a bijection.

Inverse - if f is a bijection from X to Y then a bijection g from Y to X may be defined such that for each y  ∈ Y, g(y) = x where x ∈ X and f(x) = y.
	g is called the inverse of f, written g = f^-1

Bijections are used to encrypt messages.
Inverses are used to decrypt them.

One-way function - a function f from X to Y is called a one-way function if f(x) is "easy" to compute for all x ∈ X but for "essentially all" elements y ∈ Im(f) it is "computationally infeasible" to find any x ∈ X such that f(x) = y.

Trapdoor one-way function - is a one-way function f:X --> X with additional property that, given some extra information (the trapdoor information), it becomes feasible to find x ∈ X and given y ∈ Im(f), such that f(x) = y. 

Permutation - let S be a finite set of elements, then a permutation p on S is a bijection from S to itself: p: S --> S
	A permutation is a rearrangement of elements to create confusion or hide patterns in plaintext.

Involution - let f be a bijection from S to S, then f is an involution if f = f^-1
	or equivalently f(f(x)) = x

Alphabet of definition - defines a finite set.
	Alphabet - symbols used to construct messages.
	Binary alphabet, A = {0, 1}

Message space - M denotes a set called the message space, which are strings of symbols form an alphabet of definition.

Plaintext - an element M that contains any information.
	Such as binary strings, some text or a program.

Ciphertext space - element C consisting of strings of symbols from an alphabet of definition which may differ from the alphabet used for M.

Ciphertext - an element of C is called a ciphertext.

Key space - K denotes a set called key space
	A set of all possible keys available in the set.

Key - an element of K is called a key.

Encryption function - each element e K uniquely determines a bijection from M to C, denoted E<sub>e</sub> 

Decryption function - for each d ∈ K, D<sub>d</sub> denotes a unique bijection from C to M called a decryption function.

Encrypting - applying E<sub>e</sub> to a message m ∈ M is usually referred to as encrypting m.

Decrypting - similarly the application of D<sub>d</sub> to a ciphertext c is usually referred to as decrypting c.

Encrypting scheme - consists of sets {E<sub>e</sub> : e ∈ K} and {D<sub>d</sub> : d ∈ K} with the property that for each e ∈ K there is a unique key d ∈ K such that D<sub>d</sub> = E<sub>e</sub><sup>-1</sup> , that is D<sub>d</sub>(E<sub>e</sub>(m)) = m 

e and d are known as a key pair.






















