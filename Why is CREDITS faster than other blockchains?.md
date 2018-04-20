![fast blockchain](https://d.radikal.ru/d10/1804/5d/f6644b53d9b5.jpg)

# Why is CREDITS faster than other blockchains?

Introduction
Disputes about whether or not blockchain will be able to compete with the payment systems which have found their way into the market continue unabated. They are hardly caused by the complexity of technology as such — it’s all about transaction processing speed. Giants like Bitcoin and Ethereum are still unable to boast a large number of transactions executed per unit of time. Bitcoin processes as few as 4 to 7 transactions per second, preceded by somewhat faster Ethereum, with 10 to 30 TPS. However, Bitcoin Cash demonstrates higher capacity, 60 transactions per second (most recently recorded indicator).

What happens when users try to send, let’s say, 8 transactions per second and network bandwidth is not more than 7 TPS? The remaining transactions with lower commission rates find themselves at the end of the line, thus increasing waiting times and/or putting an upward pressure on the commission rates. For example, when the Bitcoin network is used for simple transactions, the transaction waiting time can reach 10 minutes, and commission rates can surge from $0.05 to $2. This is a pronouncedly arresting factor which prevents the widespread use of popular blockchain platforms for the execution of continuous transactions.

If we drew a parallel with the VISA payment system, comparison would still count against the blockchain. According to VISA, the system is capable of processing up to 40,000 transactions per second, typically barely using one-third of its aggregate capacity.

Another notable player, Ripple, declares its ability to process 1,500 transactions per second. This sounds like a more decent rate, almost ten times higher than the throughput indicators of, for instance, PayPal, whereas transfer commission rates are hugely reduced.

The CREDITS platform is a decentralized computer network or the so-called peer-to-peer network. It operates through the Internet and uses the TCP/IP network model as the principal model for intra-network data and command transfer. Network participants interact with each other based on peer-to-peer models. All data transfers to and from network use the UDP transport layer protocol of the network model, and high-performance NoSQL system is the storage concept employed for key-value data storage (LevelDB).

While the alpha version of the CREDITS platform was tested, the peak-load system was able to process a pool/block of 488,403 transactions per second. Our tests also entailed redrafting the overall data storage architecture (API) and certain components of the platform. The video about these tests is available on our Youtube channel.

![Tab](https://b.radikal.ru/b23/1804/29/1a12bf3dee8d.png)
Still, why can the Credits blockchain process hundreds and thousands of times more transactions per second than other popular systems? In order to answer this question, a few critical aspects are well worth consideration.

1. Platform optimization for transaction processing speed
The source code of the platform is optimized for a very specific task, i.e. high data transfer and processing speed. This is primarily achieved through direct device processor operations. The operational efficiency of hardware is ensured by low-level programming languages, time-critical or memory-critical program sections are written in assembler language. They subsequently take the shape of subprograms and are combined with the code in a high-level language.

Speed is raised through the optimization of a computing algorithm and more sound core memory access, data redistribution, spreadsheet calculations of functions.

2. Reduction of data packet size
Any transaction has a dynamically varying size depending on balance, address size, transaction currency, the use of digital signature, and further comments. 90% represent the minimum transaction sizes (120–150 byte), thus increasing transfer and processing speeds. If a transaction or a pool of transactions has large data volumes, a transmission packet is broken down into smaller (65,535 byte) datagrams used by the UDP protocol subject to the upper limit size.

This makes it possible to reduce data leaks and increase intra P2P network data transfer speed.

3. Distributed transaction pooling
A new round is created every 5 milliseconds (5×10–3seconds). One transaction pool per round is generated. All nodes in the network are listed. Each node is assigned a random number (ranking). The list is sorted downwards based on these values. The first node in this list becomes the master node. All subsequent nodes in the list become trusted nodes to the number determined using the following algorithm: if the total number of nodes is ten, 50% become trusted, yet at least three. If the total number of nodes is at least 100, then 10% are trusted. The average quantity varies between 10% and 50% of the total number of nodes in the network. The final list of nodes involved in any round makes it possible to determine the number of this pool. The nodes involved in pool processing do not participate in building the new round. The system starts a new round using the number based on the algorithm described above without waiting until the processing of the last one is over. This is how asynchronous processing of transaction pools unfolds and the chain of pools is built.

4. Employment of dynamically optimized data flow in a distributed network
In the stochastic control theory, some results in the systems with hidden Markov processes allow them to be employed in the control problems in respect of data transfer systems. The proposed approach is based on the following preconditions:

– channel status is described by a Markov chain with the finite set of states and known transition intensities;

– data transfer speed is a control parameter and packet loss intensity is a known monotonic function of transfer speed and channel status;

– the goal of control is to select the law of variation of data transfer speed which makes it possible to achieve the maximum mean value of successfully transmitted packets.

The problem-solving method relies on building a family of sufficient statistics for the current channel status and selecting a transfer speed value which ensures the maximum conditional real transfer speed (conditional difference between data transfer speed and loss flow intensity).

5. Employment of findings from stochastic simulation of similar systems
A group of events is modeled in the test medium, namely: into the distributed information system with multithreaded data processing option. This allows system bottlenecks to be detected and remedial action to be taken.

Stochastic simulation is the simulation of random events. Multiple repetitions of simulation exercises with the aim of obtaining statistics concerning system properties, obtaining data about the features of random events and values.

The goal of stochastic simulation is to obtain an estimated mathematical expectation, dispersion, and random values distribution law for the parameters of objects.

“Random event” means any fact which may or may not occur as a result of an exercise. The types of random events are as follows:

Certain (event occurring in every exercise).
Impossible (event which cannot occur as a result of an exercise).
Characteristics:

The “frequency of occurrence” means the likelihood of any given event assuming an unlimited number of exercises.

“Mathematical expectation” means the number around which the values of random variable are concentrated.
The variance of random variable characterizes the measure of spread of random variable around its mathematical expectation.
Probability density functions represent a function type determined by random values distribution law.

6. Optimization of the transaction pool access and storage mechanism
Data access and storage. Currently, data storage in the chain of pools is the most secure option. However, the verification of a transaction necessitates verifying the entire chain from the first block onwards.

Data storage on the platform is implemented with employment of LevelDB, a high-performance, replicable NoSQL system for key-value data storage developed by Google. The LevelDB warehouse is written in С++ and connected to applications as a shared library, which makes it possible to store ordered data sets in which arbitrary binary keys are associated with arbitrary binary values.

Data is stored in the form of transaction pools. The use of key-value format allows quick access to all necessary data with no need for checking the whole warehouse.

The conclusion
Summing it up, we can draw the following conclusions. Raising transaction processing speeds is high on the agenda for the blockchain technology development. For the time being, there are not so many systems which are capable of processing more than 1,500 transactions per second. In this context, the Credits.com platform with a throughput of 400,000 transactions per second (in Alpha-version) appears to be a really solid player in the blockchain market, which is in a position to compete even with popular payment systems offering extremely high speeds.
