## Hasing
Just scrambling some sort of data. Starts at any length, ends at fixed length.
Inputs will always yield the same output. It has to be hard to go backwards.

## Salt
Prevents hackers from using pre-cracked hash tables. Just a random value that is added to the item before it is hashed.

## HMAC
(Hash-Based Message Authentication Code)

Hash that also requires a password. JWTs are like this. (I don't fully get this one)

## Encryption
You create a cypher-text from a document that has a key that allows the cypher-text to be decrypted.
Each encryption should give a different output, even if key and input are the same.
A symmetric encryption requires a key to be shared between the client and server.
`aes256` is a common algorithm
