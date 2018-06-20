![Digital Signature](https://b.radikal.ru/b11/1806/5a/68b3b1b562bc.jpg)
Digital signature is a detail of an electronic document which is used to identify the person that transmits data. DS makes it possible to ascertain the non-distortion status of information in a document once signed and check whether or not the signature belongs to the key certificate holder. The detail’s value is a result of cryptographic transformation of information through the use of a private and public key.

DS is treated as a substitute for handwritten signature to the extent permitted by law. From the standpoint of applications, it:

● Allows value control in respect of the document being transmitted — whenever a document gets exposed to a malicious modification, the signature is invalidated since it conforms solely to the initial document status;

● Guarantees protection from falsification: the existing signature algorithms render falsification infeasible in most cases;

● Ensures non-repudiation of origin — any signature is generated using a private key which is known only to its owner, who is therefore unable to repudiate his/her signature added to the document;

● The latter factor also enables the authorship of a document to be supported by evidence in the event of a dispute.

DS algorithms
RSA
Public-key encryption algorithm. Security features of this algorithm stem from the difficulty of the factorization problem. The algorithm employs two keys — the public and the private, which form the relevant pair. Public key is used for data encryption purposes. If a message is encrypted using a public key, then it can only be decrypted using the associated private key.

Advantages:

● Convenient distribution of public keys, no secrecy is required;

● Bigger networks have a much smaller number of keys vs. a symmetric cryptosystem.

Disadvantages:

● Low operating speed;

● High computing costs in connection with ensuring encryption strength relative to falsification attempts;

● Susceptibility to a multiplicative attack. In other words, it allows a malicious user who does not know a secret key to generate a signature for the documents in which the hash result can be computed as the product of hash results of the already signed documents.

The RSA system is used in hybrid cryptosystems in combination with symmetric algorithms. RSA is employed by operating systems, such as Microsoft, Apple, Sun, and Novell. The hardware applications of the RSA algorithm include secure voice telephones, Ethernet network cards, smart cards, large-scale applications in cryptographic equipment. Furthermore, the algorithm is inherent in all major secure Internet communications protocols, including S/MIME, SSL, and S/WAN, and leveraged by government authorities, most corporations, government laboratories and universities.

ElGamal encryption system
Public-key encryption algorithm. Security features of this algorithm stem from the difficulty of computing discrete logarithms in the finite field. The ElGamal encryption system encompasses both encryption and digital signature algorithms.

Advantages:

● Probabilistic nature of encryption, offering high strength levels;

● Ability to generate digital signatures for a large number of messages using just one secret key.

Disadvantages:

● Doubling of the encrypted text length as compared with the initial one, causing longer computing times and tougher requirements for communication channel security.

This solution is employed in public key certificates for the purposes of protecting connections in TLS (SSL, HTTPS, WEB), messages in XML Signature (XML Encryption), and the integrity of IP addresses and domain names (DNSSEC).

DSA
Public-key encryption algorithm designated to create an electronic signature. A signature is created “in private” but can be verified “in public.” In other words, there is only one subject that can create a signature added to a message, but anyone is in a position to check whether or not the signature is correct. Security features of this algorithm stem from the computational complexity of taking logarithms in the finite fields.

The DSA algorithm is a modification of the ElGamal encryption algorithm and offers a number of benefits:

● Shorter signature length despite the identical strength levels;

● Lower signature computation speed;

● Reduced required storage space.

Disadvantages:

● Signature verification must entail complicated remainder operators, whereby the quickest possible action is hampered;

The DSA algorithm was adopted as the U. S. national standard with applications in both secret and non-secret communications.

ECDSA
Public-key encryption algorithm designated to create an electronic signature. A modification of the DSA algorithm. Being defined in the group of elliptic curve points rather than over the ring of integers is what makes it stand out. The strength levels of the algorithm stem from the problem of solving the discrete logarithm in the group of elliptic curve points. The ECDSA algorithm is resistant to an attack based on a fitted open text with the existing falsification.

Advantages of ECDSA:

● Ability to operate in much lower fields than in cases where the DSA algorithm is employed;

● No application performance issues;

● Rapid signing and verifying process;

● Compliance with ever-growing protection requirements;

● Support for national information protection standards;

Disadvantage:

● A chance of error which makes it possible to select a private key value such that identical signatures for different documents can be obtained. However, enormous computational performance is required for this chance to materialize.

Elliptic curve algorithms are used in TLS, PGP, SSH. Thys type of encryption is further employed on the Bitcoin and other blockchain platforms.

GOST R 34.10–2012
Russian standard describing the DS generation and verification algorithms. The algorithm is based on elliptic curves.

Being a copy of ECDSA, this standard still offers a few advantages:

● GOST 34.10–2012 contains no recommendations for curve uses, offering only a set of requirements for such curves, thus allowing the standard to be kept unchanged whenever new results about “weak” classes of elliptic curve come up.

Disadvantage:

● A lack of recommended parameters requires further efforts to select and justify those parameters, have them agreed by the regulators and develop guidelines.

Its possible applications include public key certificates, S/MIME (PKCS#7, Cryptographic Message Syntax), connection security in TLS (SSL, HTTPS, WEB), connection security and message security in XML Signature (XML Encryption) and TLS (SSL, HTTPS, WEB), protecting the integrity of IP addresses and domain names (DNSSEC).

Schnorr signature algorithm
The security features of the scheme build on the computational complexity of discrete logarithms. Being a modification of the ElGamal encryption system and the Fiat-Shamir scheme, it still offers a benefit in the form of smaller signature size.

The algorithm is used in the national standard of the Republic of Belarus (STB 1176.2–99) and South Korean standards KCDSA and EC-KCDSA.

Rapid digital signature
The principles of rapid signing underpin the following DS algorithms: BLS, Diffie–Hellman, the Fiat-Shamir scheme. This option is leveraged by algorithms with a smaller number of computations. The scheme in question also involves the processes of generating user key pairs, signature computation and verification functions. It relies on the discrete logarithm problem.

Advantage:

● Simplified computing, pushing up performance levels.

Disadvantages:

● substantially under-explored;

● limited to groups with the pair matching function.

This solution is opted for in cases where the key speed and signature size are of essence, e.g., mobile, sensor, personal networks, embedded smart cards, cellphones.

GMR algorithm
This is a modification of RSA. The strength levels of the algorithm stem from the difficulty of integer factorization. Its advantage over RSA is protection from the attacks of adaptive selected messages.

Rabin cryptosystem
Signature scheme with provable strength levels. Security features of this algorithm stem from the difficulty of integer factorization. This algorithm has not become widespread.

Advantage:

● higher operating speed vs. RSA.

Disadvantages:

● necessity of selecting a true message out of four possible ones;

● susceptible to an attack based on the selected ciphertext.

EdDSA algorithm
Signature scheme with employment of the Schnorr option and elliptic curves. The EdDSA algorithm relies on the Ed25519 signature scheme based on SHA-512/256 and Curve25519.

Advantages:

● high speeds;

● independence of the random number generator;

● high performance.

This technique is used in OpenSSH, GnuPG, OpenBSD, Nacl/libsodium, cryptocurrency protocol CryptoNote, WolfSSL, I2Pd.

DS algorithm employed on CREDITS platform
The signature system delivered on the CREDITS platform relies on elliptic curves (EdDSA). If also employs Ed25519, an elliptic curve signature scheme that offers better security than ECDSA and DSA and good performance. Elliptic curve cryptography is used to generate cryptographically protected key pairs.

The code phrase generated to create user account is further hashed through the use of BLAKE2s algorithm. This hash is subsequently used by Ed25519 to generate a private key and a public key.

This kind of protection can only be hacked by large quantum computers. A reasonable assessment of the capabilities offered by conventional computers evidences that Ed25519 is completely secure.

The conclusion
Today, digital signatures are employed all over the Internet. Blockchain systems, representing the future of technology, rely on the DS techniques, too. Every transaction carried out on the blockchain is signed by the sender’s electronic signature using his/her private key. Blockchain cannot exist without hashing or digital signature. Hashing makes it possible to determine the current system status, whereas DS provides evidence showing that all transactions were carried out by true holders only.

The CREDITS platform is built around a state-of-the-art signature algorithm, which offers high security levels and performance. Security technologies collectively enable the platform to achieve excellent network performance coupled with the highest security requirements and make it stand out from other projects.


