# Documentation
Credits.com Documents
# CREDITS: Peer-to-peer (P2P) network and its components

![Credits peer-to-peer diagram](https://c.radikal.ru/c18/1804/93/d2e0e7464d8b.jpg)

CREDITS blockchain platform is a direct node interaction, decentralized, computer network or, so-called, peer-to-peer network. It works via the Internet and uses the TCP/IP network model as the main model for data and commands transmission within the network. Network members interact with each other on a peer-to-peer basis — equal to equal. All data is transferred to the network and back with application of User Datagram Protocol (UDP), and the storage concept represents itself a high-performance NoSQL system for storing data in a LevelDB key-value format.

The network includes the following services:

Node (peer)

Nodes are key components for creating a decentralized network.

A node is a client application installed on a user’s computer. It performs processing and storage of transactions, execution and confirmation of the terms of the smart contracts, processes requests from third-party systems, and provides data upon requests.

Also, the latest version of the Java library is required to run the system and, in particular, to create and process SmartContracts. To download it please click the following link: https://www.java.com/ru/download/

Any network node has the same specified functionality and performs the functions described above by the means of the following five modules:

CREDITS transmission/transfer protocol (CSP)
The decision-making module
Data Storage
Smart contract processing module
API
The general concept of CREDITS transmission/transfer protocol (CSP) is as follows:
The TCP/IP network model is represented by the UDP (User Datagram Protocol) transmission protocol. Computer applications can send messages (in this case referred to as datagrams) using UDP to other hosts over an IP-network without obligatory preliminary messages for selection of a special data transmission protocol.

2. Decision-making (consensus) module

Conceptually, the description of the consensus algorithm for the CREDITS network is as follows:

Generation of the list of nodes participating in a particular round, according to DPoS technology
DPoS establishes a rating system of reputation. In other words, it creates a group of nodes with the right to validate transactions, generate a transaction pool, validate and send the pools to the nodes, for further chain recording.

Each new round is organized every 5 milliseconds (5×10–3 seconds). Only one transaction pool is created within one round. The list of all used network nodes is formed. Each node is assigned a random number (rating). Based on these numbers, the list of nodes is sorted in a descending order. The first node in this list becomes the main network node. The following nodes in the list become trusted nodes, and their number is calculated according to the following algorithm: if the total number of nodes is equal to 10, then 50% of them become trusted nodes (but not less than 3). 
For the number of nodes from 100 and higher only 10% become trusted. The average number of such nodes varies in the range of 10%-50% of the total number of used network nodes. With the generated list of nodes participating in the round it is possible to get the number of a particular pool. Nodes involved in processing the pool do not participate in a new round. Using the mentioned number, the system starts a new round by the above described algorithm, without waiting for the finish of processing the previous one. Thus, asynchronous processing of transaction pools is carried out and a chain of pools is created.

Validation within one round and building a chain of pools (according to BFT technology).
Byzantine Fault Tolerance (BFT). This algorithm allows generals (validators) to manage the network state and exchange messages and, thus, provides honesty and make a decision on validity of a transaction and pool.

Upon creation any transaction is forwarded to the main node and from this point to trusted nodes, where it undergoes validation. Each trusted node is connected to the neighbor node, for joint transaction validation. The trusted nodes make the decision on validity of transactions using the BFT mathematical model. After that, transactions are sent back to the main node for recording to a pool. Upon termination of the mentioned time period, or after accumulation of a certain number of transactions, the pool is closed. A hash sum of the pool is generated according to the number of such pool and a hash sum of the previous pool. After that it is sent to all nodes of the network for further recording in a chain. Thus, the round ends.

3) Data Storage

To store data this platform uses LevelDB, a high-performance, replicable NoSQL system with a key-value data storage format developed by Google. LevelDB Data Storage is written in C++ and connects to applications as a shared library, providing the possibility of storage of ordered data sets in which arbitrary binary keys are mapped to arbitrary binary values.

Data storage algorithm. Data is stored in SS-tables (Sorted String Tables) as key-value pairs. The set of SS-tables forms a LSM-tree. LSM-trees (Log-structured merge-trees) have several levels of storage. The first (zero or MemTable) level is in RAM, and the rest is on a disk. Each level represents a tree or a list of trees, and each level has a size limit (usually 10x per level).

Data compression in LevelDB is carried out using the internal Snappy library. On a single-core CPU Core i7 the 64-bit Snappy assembly is capable of compressing data streams at 250 Mb/s and decompressing at 500 Mb/s. For normal text, the level of compression provided by Snappy is 1.5–1.7x, for HTML-files — 2–4x.

4) Smart contract processing module

Any smart contract is a code written in Java.

The smart contract processing module receives contracts from a desktop wallet and stores them in its data storage at a certain address, then they are executed by a contract constructor (named «initialization process»). After that, from a decision-making module we receive a signal for the execution of a certain part of the contract and values of the input data. In other words, a certain Java method in the class is executed and the global variables data are stored for each contract in the data storage. The new tokens creation function is also available. It interacts with the network via API providing a core.

5) Node’s API

To communicate with third-party services CREDITS platform uses the Apache Thrift technology. This is an interface description language used for determination and creation of services for different programming languages. It combines a program pipeline with a code generation engine to develop services, to some extent efficiently and easily working with such languages as C#, C++, Delphi, Java, Perl, PHP, Python, JavaScript, etc. In other words, Thrift is a binary communication protocol.

The following methods are used to implement the connection of third-party services to the core of the platform. They are divided into 2 types (get — request and result — response):

BalanceGetResult, BalanceGet — balance of a particular wallet
TransactionGetResult, TransactionGet — hash of a particular transaction
TransactionsGetResult, TransactionsGet — the list of transactions, for a particular wallet
TransactionFlowResult, TransactionFlow — transaction
PoolListGetResult, PoolListGet — pool of transactions
PoolGetResult PoolGet — hash of a pool
NodesCounteGet, NodesCounteResult — the number of used network nodes
System requirements for node installation:

Minimum system requirements:

Operating system: Windows® 7 / Windows® 8 / Windows® 10 64-bit (with the last update package)
Processor (CPU): with frequency of 1 GHz (or faster) with PAE, NX and SSE2 support;
Memory (RAM): 2–4 Gb
HDD: 1 Gb
Internet connection: 3 Mbit/s
Recommended system requirements:

Operating system: Windows® 7 / Windows® 8 / Windows® 10 64-bit (with the last update package)
Processor (CPU): Intel® Core ™ i3 or AMD Phenom ™ X3 8650
Memory (RAM): 4–8 Gb
SSD: 1 Gb
Internet connection: 5 Mbit/s.
Desktop-wallet

CREDITS Wallet Desktop is a desktop version of the wallet. This version of the wallet provides a high level of security, privacy and stability. The functionality of the desktop application is more complex, than that of a web version.

Wallet Desktop works only together with the network node that must be engaged before working with this version of the wallet.

Functional features

Creation of a transaction
History of transactions analysis
Balance analysis
Creation of a new token (by means of a smart contract)
Creation of a smart contract
Web-wallet

CREDITS wallet is a client interface for safe and easy interaction with a P2P network, easy to use, flexible and easy-to-customize.

CREDITS Web-Wallet allows to transfer currency from one user to another quickly, without installing a complete node, and perform operations with an already deployed smart contract, if there is no need for its self-compilation. Synchronization with a network is performed automatically in real time. Connection to a P2P network is carried out by means of an API platform.

Basic functions:

Creation of a transaction
Series of operations within already deployed smart contracts
Exchange and transfer of currency and valuables (CS and other tokens issued based on our standard)
Possibility to trace details of current and previously completed transactions
Checking the balance
Checking the history of transactions
The described operations duplicate options available via our desktop application, excluding the possibility to compile and upload new smart contracts. Initiation and execution of transactions is carried out by analogy with the above described scenario.

![Sys](https://b.radikal.ru/b07/1804/c9/e378c88e0ddc.jpg)
System Requirements:

The updated version of a web browser is required to use the web client. Minimum requirements:

IE 10;
Safari 9, iOS 9;
Android 5.0, Edge 13 (and later)
Monitor
CREDITS monitor is a web-based version of the application that provides the possibility to analyze the public transfer register. The monitor is implemented in Java + Angular JS and connected to a P2P network by means of an API platform. Statistics are updated every 30 seconds.

The following information is presented on the CREDITS monitor page:

Total number of network nodes
Statistics on transactions
Balance
Details of transactions for a certain wallet
General information on a certain smart contract
Details of an opened smart contract
