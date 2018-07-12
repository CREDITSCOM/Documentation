![How to compress data by 90%](https://c.radikal.ru/c07/1806/23/2e7387455aef.jpg)
Typically, designing data stores has a key role to play in most projects. A properly designed database makes it possible to make alterations to the system or restructure it almost seamlessly and hardly takes up a lot of storage space.
We at CREDITS use a non-relational database known as LevelDB. LevelDB is a high-performance NoSQL system developed by Google specifically to store data in key-value format. The LevelDB store is written in С++ and connected to applications as a shared library (like SQLite or BerkeleyDB), thus offering the opportunity of storing ordered data sets in which keys are associated with values. LevelDB is an open source store licensed under a BSD license.

There is no need to convert such database to normal forms as it is already limited to key-value pair, which means normalized.

Storing hundreds of thousands of key-value pairs under the CREDITS project requires sizeable server memory. In order for the storage space used by such database to be reduced, data compression algorithms must be employed.

Data compression algorithms

Almost any information can be compressed since in practice the representation of information is always redundant.

There are two main types of data compression:

1) Lossless compression (fully reversible).

2) Lossy compression (a minor part of data is lost and complete restoration is not possible).

The first type of compression is employed when it is important to ensure that the compressed data restored is distortion-free, like in our project. This kind of compression removes none of the original data. It is only due to less space-consuming data representation that compression is achieved.

Let us consider some of the most common lossless (reversible) compression algorithms:

1) Huffman technique. This entails replacing an equal-length code for symbols with unequal-length codes depending on the frequency of occurrence for a symbol in the text. The codes with minimum length are assigned to the most common symbols. Where character frequencies are a power of two (2n), this technique theoretically approaches the entropy limit of compression efficiency for this type of techniques.

2) Shannon–Fano technique. Prefix non-uniform coding algorithm. Represents the compression techniques based on probabilities. Like the Huffman algorithm, this technique builds on message redundancy, which means a non-uniform distribution of frequencies for the symbols of its (primary) alphabet, i.e., replaces the codes of more frequent symbols with short binary sequences, and codes of more rare symbols with longer binary sequences. The Shannon technique is notably worse than the Huffman code.

3) Running (RLE) technique. This refers to replacing the sets of repeated symbols with the symbol code and the number of repetitions. Though easy-to-understand and very simple, this compression technique still lacks efficiency.

4) Lempel–Ziv–Welch techniques. What all compression algorithms of this group (LZ78, LZ77, and LZW) have in common is the idea of searching for text fragment repetitions in data and replacing these repetitions with a reference to the first or previous occurrence of this fragment in data.

We use the Huffman method in an effort to achieve the efficient functioning of the CREDITS project and lossless database archiving. Let us take a closer look at this algorithm invented by David Huffman in 1952. The bottom line is the use of an adaptive algorithm which, whenever a code is made to match a symbol, changes an internal node such that next time the same symbol can match a different code.

The Huffman coding problem is equivalent to the problem of construction of the associated tree.

Huffman Algorithm
The algorithm of constructing optimal unequal codes proposed by Huffman is one of the most important achievements of information theory from both theoretical and applied perspectives.

Let us consider the set of messages Х = {1,…,М} with message probabilities {p1, …,pm}. Without loss of generality, we view messages as enqueued by probability in decreasing order, i.e., p1 < p2 < … < pm. Our objective is to construct an optimal code, which is a code with the lowest possible average length of key words. It is clear that this code is not necessarily the only one for given probabilities, in contrast, a family of optimal codes can exist. Let us find some of the properties of all codes representing this family. Those properties will give us a clue as to a simple way of determining an optimal code.

Let the binary code С = {c1, …, cm} with codeword lengths {l1, …, lM} be optimal for the set of messages in question.

1. If pi < pj, then li > lj.

2. The length lM = maxm1m of at least two codewords is optimal.

3. Two of the codewords whose length is lM = maxmlm will differ only in one — the last — symbol.

4. If the code С’ is optimal for X’, then the code С is optimal for X.

Input: alphabet size M, the probabilities of letters.

Output: Binary tree of the Huffman code.

Initialization:

The number of unprocessed nodes is М0=М.

While M0>1 do

1) Find two nodes with the lowest probabilities in the queue of unprocessed nodes.

2) Remove those nodes from the queue of unprocessed ones.

3) Generate a new node, with the two just-selected nodes as children. That said, the weight of the resulting node is set equal to the sum of child nodes’ weights.

4) Add the newly generated node to the queue. Link the new node with edges to just-removed nodes.

5) М0 <– М <– 1.

6) If there is more than one node in the queue, repeat steps 2–5.

End

The process of decoding is similar. The reason for using this technique is that we consider it the most effective data compression technique.
