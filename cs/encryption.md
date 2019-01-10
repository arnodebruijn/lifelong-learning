Encryption
==========

Symmetric ciphers
-----------------
A cipher that uses the same key for both encryption and decryption. Two parties communicationg using a symmetric cypher have to agree on the key beforehand.

A public key may be thought of as an open safe. When a correspondent encrypts a document using a public key, that document is put in the safe, the safe shut, and the combination lock spun several times. The corresponding private key is the combination that can reopen the safe and retrieve the document. In other words, only the person who holds the private key can recover a document encrypted using the associated public key.

If you want to encrypt a message to Alice, you encrypt it using Alice's public key, and she decrypts it with her private key. If Alice wants to send you a message, she encrypts it using your public key, and you decrypt it with your key.

Public-key ciphers
------------------
Uses a pair of keys (public, private) that belong to the receiver for sending messages.
* public key    may be given to anybody
* private key   is kept secret by the owner
A sender encrypts a message using the public key. Once encrypted only the private key can decrypt it. This way there is no need for sender and receiver to agree upon a key.


Hybrid ciphers
--------------
A hybrid cipher uses both a symmetric cipher and a public-key cipher. It works by using a public-key cipher to share a key for the symmetric cipher.


Digital signatures
------------------
A digital signature verifies and timestamps a document. A digital signature makes a document tamper-resistant, namely if a document is modified in any way, a verification of the signature will fail.

A document's digital signature is the result of applying a hash function to the document. Some public-key ciphers could be used to sign documents. The signer encrypts the document with his private key. Anybody wishing to check the signature and see the document simply uses the signer's public key to decrypt the document. This algorithm does satisfy the properties needed from a good hash function, but in practice, this algorithm is too slow to be useful.

An alternative is to use hash functions like SHA and MD5. Using such an algorithm, a document is signed by hashing it, and the hash value is the signature. Another person can check the signature by also hashing their copy of the document and comparing the hash value they get with the hash value of the original document. If they match, it is almost certain that the documents are identical.

A signature is created using the private key of the signer. The signature is verified using the corresponding public key

Alice would use her own private key to digitally sign her latest submission to the Journal of Inorganic Chemistry. The associate editor handling her submission would use Alice's public key to check the signature to verify that the submission indeed came from Alice and that it had not been modified since Alice sent it. A consequence of using digital signatures is that it is difficult to deny that you made a digital signature since that would imply your private key had been compromised.


Key management
==============
https://www.gnupg.org/gph/en/manual/c235.html
