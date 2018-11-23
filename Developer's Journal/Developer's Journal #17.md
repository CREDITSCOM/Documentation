![Dev's journal#17](https://credits.com/uploads/ap/news/7797c4fde31849f8814dc18aff3a5a0a.jpg)
Here you find the details of the latest completed Credits Development Cycle as well as information on what is to come. We are delighted to share the improvements we’ve made to the platform since our last update and Phase One Testing.
 

Highlights
 

Public Testnet Version 2.0 Nodes are now available for download
Consensus Protocol Improvements
Transport Protocol Improvements
Removal of VPN
Major Consensus Updates
Data Compression Updates
Desktop Wallet Improvements
Credits Monitor Improvements
Storage Optimizations
Smart Contract Improvements
Github Source Code updates
Current Release Bugs Report
Public Testnet Version 2.0
 

The long awaited Version 2.0 of our Public Testnet is now available for download. It has been 3 long months since we’ve updated the Nodes on our Testnet. With this latest release we’ve bundled all the improvements we’ve made to the product to make sure our community can participate in testing the product at its best. With this release, the VPN has been removed and prior Synchronization issues have been solved. Currently there are two versions of software for Windows and for Linux operational systems. We expect our eager community will be spooling up nodes to assist us in testing the platform.
 

Consensus Protocol Improvements
 

Several changes to the Consensus Algorithm have been made to improve performance and security. These changes have been incorporated into the Public Testnet nodes available for download. We are going to publish detailed article about new implementations further.
 

In order to optimize network performance we have implemented the following list of updates:
Synchronization mechanism improvement
Transaction Validation algorithm improved to process multiple transactions from a wallet per round
Addition of Transaction Fee Calculation
Additional Memory Storage requirement for Fee Data at a storage cost of 2 bytes per transaction
Implementation of Serialization of Signature Verification required for the new transaction structure
Time-based calls of consensus methods were tested and streamlined in order to debug the current state of consensus
The call stack minimization was optimized
Optimization of work with the code including functions and variables calls
An article detailing the Consensus Protocol and the improvements we’ve made will be published soon.
 

Transport Protocol Improvements
 

1) Various Improvements have been made to the transport protocols to eliminate the disadvantages of current solutions for collecting, distributing and processing of unconfirmed transactions packages. The following optimizations were done on this field:
 

Creation of a transaction pool on a node and allowing its distribution to neighbour nodes
Synchronization mechanism, ensuring that missing packets are requested by their hash
Dividing transaction packages into sub-packages when the number of transactions is greater than 500
Creation of a list of transactions packages being processed in a round spreadsheet to improve its deserialization and distribution
Enhancement of block distribution mechanism. A block is now formed on a writing node and recreated on all network nodes via characteristic function
2) In order to decrease the amount of redundant data transfer, the package distribution mechanism was optimized, ensuring a reduction in traffic between neighbour nodes during blocks distribution in the network
 

3) LZ4 data compression algorithm was implemented replacing the previous Snappy data compression algorithm
 

4) Network node identification via public key was implemented. Information about an individual node’s IP address is available only to its direct neighbours, to which it is exchanging packets. As this information is not included in the round spreadsheet or the block, this ensures the network is completely anonymous;
 

5) It is now possible to connect to the network without the signal server. As a temporary workaround, until a complete fix is in place, node testers can input addresses of neighbour nodes manually to bypass the signal server.
 

6) IPv6 is now supported on a protocol level.
 

Desktop Wallet
 

User interface errors were fixed and functions to optimize interactions with the user were added. The following updates were incorporated:
The issue with double modal window during node launch was fixed
The issue with dropdown lists was fixed
Button interaction was animated
Transaction hash is now displayed in transaction history
It is now possible to select wallet fields containing public and private keys while creating a wallet
It is now possible to save a smart contract
It is now possible to work with the node asynchronously
Monitor
 

In order to improve the visualization of information we added the ability to scale the transactions per second chart. The problem with the horizontal scrolling of the graph is fixed. We’ve also added the ability for a user to choose the point range for monitor display.
 

Storage
 

In order to optimize application performance and network bandwidth the following tasks were performed:
Implemented a procedure for serialization and deserialization of the optimized transaction format
Improved database structure
Optimized storage of internal currency by storing the the public key and wallet ID in a more compact way
Optimized transaction size
Smart contracts
 

The architecture of smart contracts operation was improved
Standards for the creation of tokens on the CREDITS platform was developed
A list of methods, including smart contract examples, will be published later on Credits Developers Portal
Credits Developers Portal
Learn how to start development on the Credits platformdevelopers.credits.com
 

 
Github Update
 

We will be placing a greater importance on publishing our work to Github by updating the published source code on regular basis (targeted at every 5–7 days). The source code of the latest node version will be released as soon as possible.
At the moment the following code is available on our Github:
 

Credits Wallet
— Source code
— Client for interaction with the database
 

Credits Web Wallet
— Source code
 

Credits Node
— Source code
 

— Network modules
 

— API example
 

— Cryptography
 

— Snappy Compression Algorithm
 

— Blake2s/2b Hashing Algorithm Implementation
 

— Apache Thrift
 

— Database
 

— Elliptic curve ed25519 Implementation
 

Credits Monitor
— Source code
 

Credits API
— Apache Thrift-based API
 
 

 
 

 
Bugs report
 

1) Process of synchronization takes extended periods of time. This happens due to the fact that synchronization is based on consensus. The block request occurs once per round. The number of synchronized blocks depends on the network capacity, the geographical distance of the node which processes the block, and the presence of the interaction between requested and processing nodes.
 

2) The balance of the wallet isn’t updated immediately. In order to get an accurate information it is required to check Credits Monitor. Incompatibilities with different versions of JAVA may be the reasons of this flaw, all wallet’s requests are executed based on JAVA and transmitted to the node via Apache Thrift.
 

3) Displaying of the wallet unfavourable balance is possible. Port 8081 and port 80 are required for the correct node operation. If one of the ports is stretched in other processes, the correctness of the node work is violated. At the same time transaction delays are possible, including transactions referred to the execution of smart contracts as well as an incorrect displaying of the wallet balance.
 

4) Transactions are not always transferred to the network. The reason is incompatibility with JAVA. Sometimes transaction can be generated incorrectly.
 

5) User field is not implemented in the current release. This function will be finalized in the upcoming versions.
 

6) Credits Desktop Wallet doesn’t display a commision. The status of transaction and the filed “commission” haven’t been implemented in the section “details of transaction” yet. A pop-up window “success” after sending a transaction indicates that a transaction was sent for processing but doesn’t show whether the transaction had passed.