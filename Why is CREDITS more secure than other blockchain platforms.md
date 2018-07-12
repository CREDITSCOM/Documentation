![CREDITS Secure](https://d.radikal.ru/d08/1805/e5/ea83d9047e79.jpg)
Blockchain offers a fundamentally different approach to ensuring the information security of large-scale systems, which goes beyond nodal servers to encompass user data and infrastructure protection. However, the blockchain sphere faces a variety of challenges, ranging from the development of network infrastructure for a potential spike in transactions, regulation with regard to information storage, the ability to procure data integrity, security, and authenticity. Let us discuss the main algorithms which, once launched, made the CREDITS platform more secure than other blockchain systems.

Information security overview
The philosophy behind blockchain technology in itself implies the highest possible security level which is underpinned by the following parameters:

Blockchain is a generated chain of data blocks linked together via a hash sum of the previous block
Decentralized data storage and processing
The principle of generating a chain of blocks, with each block containing a hash sum of the previous block
Generation of constant chain of pools
CREDITS platform stores data as a sequence of blocks arranged on a first-come, first-served basis. In the case of permutation of blocks, the sequence of time tags is incorrect and hash sums do not conform to the initial data, which renders them incorrect.

Blockchain is generated as an ever-growing chain of blocks with all transaction records. Each block has a header and a transaction list. The block header includes its own hash and a hash sum of the previous block. Accordingly, each new block contains a reference of the previous block hash in the ledger. In turn, the generation of a hash sum guarantees the irreversibility of the entire transaction chain. Changing information on the block already contained in the chain is unreasonable as this would necessitate the editing of information on all subsequent blocks. As a result, a successful double-spending attack (re-spending of earlier expenditure) is highly unlikely to really happen.


Consensus algorithm in networks
In the context of cryptocurrencies, consensus algorithms are designated to ensure the validity of transactions (with validation distributed among many network members) and system fault tolerance due to redundancies.

A description of consensus algorithm in the CREDITS network, conceptually, is as follows:

Generation of the list of nodes participating in the round based on the DPoS technology
DPoS delivers a ranking system of reputation. In other words, it creates a group of nodes entitled to validate a transaction, generate a transaction pool, validate and send pools to nodes for their further recording in a chain.

A new round is created every 5 milliseconds (5×10–3seconds). One transaction pool per round is generated. All nodes in the network are listed. Each node is assigned a random number (ranking). The list is sorted downwards based on these values. The first node in this list becomes the head node. All subsequent nodes in the list become trusted nodes to the number determined using the following algorithm: if the total number of nodes is ten, 50% become trusted, yet at least three. If the total number of nodes is at least 100, then 10% are trusted. The average quantity varies between 10% and 50% of the total number of nodes in the network. The final list of nodes involved in any round makes it possible to determine the number of this pool. The nodes involved in pool processing do not participate in building the new round. The system starts a new round using the number based on the algorithm described above without waiting until the processing of the last one is over. This is how asynchronous processing of transaction pools unfolds and the chain of pools is built.

Validation within one round and pool chain generation. In reliance upon the BFT technology.
The Byzantine Fault Tolerances (BFT) algorithm allows generals (validators) to control network status and exchange messages, thus ensuring honesty and making decisions on the transaction and pool validity.

Once generated, a transaction is sent to the head node and forwarded to trusted nodes for subsequent validation. Each of the trusted nodes is linked to its neighbor for joint transaction verification purposes. Trusted nodes make a decision about the validity of these transactions based on a mathematical model known as the Byzantine Fault Tolerances algorithm. Once done, transactions are sent back to the head node to be recorded in a pool. When the time elapses or a certain number of transactions is reached, a pool is closed. A hash sum of this pool is generated according to the number assigned to this pool and a hash sum of the previous one. After that, it is forwarded to all nodes of the network for subsequent recording in a chain. The round is now complete.

Hash sum generation
CREDITS platform employs data encryption algorithm known as BLAKE2s. This algorithm is not sensitive to the size of hash data and is protected against attacks related to the emergence of collisions during hashing. BLAKE2s serves to embed the BFT consensus while checking the node functionality using a checksum. BLAKE2s is a version of the BLAKE2 algorithm optimized for 8-bit to 32-bit platform sizes. The algorithm relies on HAIFA design; the compression function, on the improved Davies–Meyer method.

The use of BLAKE2s offers the following benefits related to security:

Improved compression function

BLAKE2 enters completion identifiers as auxiliary inputs for the compression function, thus making it more secure. The employment of salt processing protects against dictionary attacks with rainbow tables.

Reduced number of constants

The BLAKE2 function uses a total of 8 instead of 24 word constants, thus saving 64 bytes of ROM and 64 bytes of RAM.

Block of parameters consisting of initialization vectors

Encryption of parameters, key length, and reference table for the security of hash tree.

Faster data transfer

Data transfer with the number of rounds has gone from 14 to 10 (vs. BLAKE-256). As a result, the number of cycles per bit has decreased from 7.49 to 5.34. This changes acceleration results by roughly 29% for the transfer of large data volumes, simultaneously improving the speed of non-massive data transfer.

Digital signature
CREDITS uses cryptographic hashing with the aim of ensuring the security of all system aspects. The platform builds on the elliptic curve signature system known as EdDSA. It also employs Ed25519, an elliptic curve signature scheme that offers better security than ECDSA and DSA and good performance. Elliptic curve encryption is used to generate cryptographically protected key pairs.

The code phrase generated to create user account is hashed through the use of BLAKE2s algorithm. This hash is subsequently used by Ed25519 to generate a private key and a public key. A private key is required for signing the user’s transactions and forwarding them to network. A public key is incorporated in a transaction, and the nodes receiving a transaction can verify the signature with employment of a public key. This provides effective protection to both user and network since a private key is held only by the user and a public key is able to verify the authenticity of the user’s signature.

The Ed25519 algorithm is designated for 128-bit security level. This kind of protection can only be hacked by large quantum computers. A reasonable assessment of the capabilities offered by conventional computers evidences that Ed25519 is completely secure.

The conclusion
Anything could be hacked — but is it rewarding? Bypassing the consensus algorithm is the only possible way to hack a system. The injection of spoof transactions or transaction pools into the system requires a large number of spoof nodes. Deploying that many nodes necessitates enormous computational performance. An abundance of resources required to lease larger data centers, develop a malicious code, deploy spoof nodes renders any hack attempts economically unjustifiable. The greater the number of valid nodes in the network, the higher the intra-network turnover and the greater the resources required by any hack attempts.

CREDITS is a unique platform which provides a fundamentally different approach to tackling any information security problems facing the blockchain system. The employment of state-of-the-art technologies in the data encryption and hashing fields made it possible to develop a platform that can’t be hacked unless considerable resources and costs are dedicated, outweighing the potential profits.
