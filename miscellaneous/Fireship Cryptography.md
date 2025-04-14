# Fireship Cryptography
## Hashing
Just scrambling some data. It takes any length and produces a fixed-length output. Inputs will always yield the same output, and it is hard to reverse.

## Salt
Prevents hackers from using pre-cracked hash tables. It's just a random value that is added to the item before it is hashed.

## HMAC
(Hash-Based Message Authentication Code)

A hash that also requires a password. JWTs are like this. (I don't fully get this one.)

## Encryption
You create a ciphertext from a document using a key that allows the ciphertext to be decrypted.
Each encryption should produce a different output, even if the key and input are the same.
Symmetric encryption requires a key to be shared between the client and server.
`aes256` is a common algorithm.