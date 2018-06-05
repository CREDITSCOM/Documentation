![Logical layers of CREDITS blockchain network software](https://d.radikal.ru/d32/1806/7d/3dab63a12c8e.jpg)
Blockchain is a distributed system which brings together independent users into a single network. Like any distributed software system, blockchain is built around a multi-tier architecture. Let us now discuss in more detail the logical layers that make up the CREDITS system, denote the fundamental principles behind their functioning and component interactions.

Typically, there are three logical layers in the distributed networks software. These include both abstract and distinct layers depending on the network implementation method:

1.Presentation Layer;
2.Application Logic Layer;
3.Data Layer.

**Characteristics of logical layers**

Presentation layer. The software system components ensuring that information is converted and provided to the user make up the presentation layer. It is possible for clients to be either external, independent of the system, or totally inherent in the system. In the latter case, it is the client that forms the presentation layer, which is typical of client-server systems. The same principle is often employed in the blockchain networks where network interactions go through the client program.

Application logic layer. This layer delivers the transactions requested by the client through the presentation layer. Programs and business processes are determined by the network. Depending on functional requirements, a layer can be further split into components, each in the form of a suite of processes, separate programs and classes.

Data layer. This part is designated to manage database connections and handle data uses.
 A process at one level requires no direct data access at the other level, every process can therefore be assigned a separate program.
 
**Network tiers and multi-tier systems**
Conceptually, there are a variety of possible layer combinations, so it’s about time we talk about tiers. 
For example, 1-tier networks that form fairly cumbersome systems suggest that all components are arranged in a single tier. Normally, this type of systems is written in the simplest languages, they are relatively difficult to maintain due to their monolithic design, and yet low-budget from the standpoint of data conversion costs. 
In turn, 2-tier architectures are fairly common in client-server systems where the presentation layer holds a separate tier. 
3-tier and multi-tier networks, as opposed to 1-tier and 2-tier networks, are more adaptable to elaborate integration models. These architectures entail introducing the second (software-based) tier in the client-server interactions. A dedicated space for integration logic is the key advantage of such architectures. Middleware tier programs offer the opportunity of introducing additional functional properties, such as event recording, data integrity guarantees and the like. 
Blockchain is a multi-tier system – adaptive, yet costly to implement.

**Principle underpinning CREDITS network design**
 Let us take a closer look at how exactly a multi-tier architecture is delivered in the CREDITS decentralized network and how its logical components interact with each other.

*Presentation layer*
The first layer is made up of the components ensuring user interactions with the blockchain platform, which are web interface, desktop application, and Monitor (network monitoring system) or any other application developed by external users. Client application must be installed and started on a computer with an active Internet connection in order to interact with the CREDITS network. It is through this client application that all requests are sent to the blockchain network, it is here too that the user is able to see both middleware and final results of transactions. Any blockchain system has overlay network in its architecture; in order for connection to the network to be established, a computer must be capable of processing messages specific to this network and affect its status. In fact, it is the real purpose behind installing the client. In some blockchain networks, this level is characterized by a limited access to the common system, e.g., Bankchain allows only banks to make a connection to the distributed network. CREDITS does not impose this kind of restrictions, and an application is accessible to any user wishing to become part of the blockchain system. 
In addition, a simplified network interaction option can be delivered through a web version, which requires no installation of the full node or client application. Virtually all transactions can be carried out using nothing but web interface. This is much easier and faster to handle for users who are not accustomed to operating software consoles.
The “lightest” interaction option is the use of viewing version, or Monitor. It displays the overall network status, the recent transactions and other information. However, manipulations cannot be performed through this service.
 	
  *Application logic layer*
The second layer where applied mechanisms are delivered is split into network nodes, transport protocol, and platform kernel. Node is a computer with the installed client and ledger storage connected to the common network. It is nodes that form the blockchain system, which in its simplest form is as follows: nodes are amalgamated to form a united network, communicate with each other, with information distributed among the nodes in compliance with the consensus algorithm. The arrangement of nodes also has its logic behind it, they are broken down into regular, trusted and head nodes based on validation data and voting rounds. The type of node affects its intended purpose too, ranging from participation in selecting trusted and head nodes to making the decision to add information to a block.
The CREDITS network relies on the principle of peer-to-peer underpinning data transfer from one node to another. In order to ensure faster data transfer, the network employs UDP (User Datagram Protocol), an optimal protocol for the fastest possible message delivery from a huge number of users. Many of the blockchain project developers have been struggling to solve the problem of low throughput in this kind of networks. The CREDITS system offers a radical solution to the issue: a number of technological finds enable developers to achieve the average network throughput of more than 480,000 transactions per second.

*Data layer*
Data layer in the blockchain system is made up of two major components, which are distributed ledger and the consensus algorithm. 
Distributed ledger. This logical component is a data structure controlled through the use of node application. Once a client application is launched, the user is allowed to access and view the content of the blockchain system's ledger. For example, when operating Ethereum the user is in a position to access and interact with the Ethereum ledger in compliance with the network rules set forth in the application software code, namely: apply smart contracts, carry out other kinds of transactions, etc. A similar principle is employed in the CREDITS network. The network nodes store data in distributed hash tables, the user is allowed to access distributed ledger (level three) and perform manipulations with this ledger by sending commands through the application (level one) using the software methods delivered in this application (level two). 
Consensus algorithm. It is delivered as part of the client application, offering the “rules of the game,” i.e., the provisions that prescribe how blocks should be built on the blockchain. Participation in the consensus formation process can be supported by several different frameworks: Proof-of-Work, Proof-of-Interest, proving time; regardless of the method being used, nodes must qualify as confirmed before being added to the consensus acceptance process. The same framework is embedded in the CREDITS logical architecture. 

*Middleware layers*
On top of that, the system also has middleware layers, such as digital signature, hash sum generation, etc. The opportunities offered by smart contracts also imply that their functionality is leveraged throughout the system.
We have discussed the blockchain network architecture through the lens of its logical components. Judging from this design principle, it can be argued that CREDITS is a very promising blockchain network with high throughput indicators and an internal multi-tier logic. The project keeps growing and developing, while improving the existing and adding new techniques. We see a continuous expansion of the network user community every day. Hopefully, the network members will assist in taking the platform to the next – even higher – level soon. 
					
