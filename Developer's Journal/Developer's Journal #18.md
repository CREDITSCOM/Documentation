![Dev's journal#18](https://credits.com/uploads/ap/news/951f744448b54febb94bfd3c5dc7beb0.jpg)
Credits development team is delighted to announce the release of the platform technical update - Testnet 2.1. This release is a stable version of the software. The most important goals that have been achieved are the optimization of the transport protocol and the synchronization process. At the moment we can confidently say  that we are very close to the External Load Test and there is a lot of work going in this direction. The precise start date of stage 2  will be announced 1-2 weeks in advance.
 
We would like to note that technical documentation on the development of the Credits platform, instructions and links for the latest version download can be found on the Developer Portal, the technical content is regularly updated.
Check out the latest updates via the links below:
 

Creating tokens on the CREDITS standard;
Example of a token on the Credits platform;
Integrated development environment - (IntelliJ IDEA, NetBeans, Eclipse Java);
 
Highlights
 

Testnet 2.1 release;
Developers Portal updates;
Smart contract improvements;
API improvements;
Consensus protocol improvements;
Transport protocol optimization;
Desktop Wallet improvements;
Web Wallet improvements;
Monitor optimizations;
Next sprint aims.
 
Smart contracts
 
We have updated algorithm aimed to verify types of the smart contract method within the current smart contract algorithm debug;
We have implemented extended token standard, the addition and usage of tokens;
API function that returns the method and arguments of the executed smart contract is implemented. The executed method with arguments returns according to specified address of the wallet;
The method of the wallet address search with the use of identifier and its transfer to the executor as a parameter has been implemented. Testing, debugging and optimization of API and external services were completed;
The ability (API method added) for external clients to receive information about smart contract methods and its parameters has been implemented.
 
API
 

In order to improve and achieve stable operation of the API:
 

Changes to thrift file were implemented;
Bug (node failure) that occurs within a search of mistakenly entered public key which size is less than 32 bytes;
Transaction size is optimized (for development and implementation processes referred to the wallet).
 
In order to refine the functions of smart contracts, the SmartContractGet function has been improved:
 

The function returns the status of the executed smart contract;
An additional parameter binary object State has been added to the output struct Smart Contract structure.
 
Transport protocol
 
Due to the fact that if the node does not show network activity in relation to the signal server (CC) for a long time, sending the network data packet to the CC, we will face a situation where it becomes unknown for CC. To resolve this kind of situations that have arisen, a re-registration process is carried out. Signal server, which have received a  data packet from an unknown node before a request to register on the network, sends an innovative command to the node to re register.
 
An exchange of verification packets (trusted nodes) has been implemented.
A mechanism for trusted nodes leading packets generating, transmitting over the network, processing and storing has been implemented.
Debugging of the distributed transaction collection, debugging of the transport module.
The validation of transaction packets and their placement to the block has been implemented.
 
Testing, debugging and optimization of the NAT mechanism were performed, the following problems were solved:
 

Bug with hanging while receiving registration packages, round tables
Determination of the node’s type in a separate thread
The blockchain block synchronization mechanism has been improved, which includes algorithms for detecting missed blocks in the chain and methods for blocks requesting from other network participants.
Mechanism aimed to synchronize the node buffer between all signal servers during node registration has been implemented.
 
Consensus Protocol
 
1) Consensus mechanism for the characteristic function has been implemented.
2) The algorithm of transaction validation by graph structure in accordance with attached architectural description has been implemented.
3) Write-off, calculation and transfer of the commission.
 
The function of commissions calculation has been added to the consensus functionality. Commission for each transaction is calculated in a round by each trusted node while building a transaction vector. The calculated commission is recorded to the counted_fee field; if the value in this field is greater than the value in the max_fee field, the transaction is rejected.
At the moment the process of the platform kernel testing and optimizing continues.
 
Desktop Wallet
 
The creation of a token (advanced token standard, addition and use) has been worked out. At the moment, the ability is not implemented;
The ability to send tokens between wallets is added;
The ability to add wallet balance at the specified smart contract via modified list has been implemented;
Redesigned CREDITS Desktop Wallet interface.
 
Web Wallet
 

Smart contract execution has been implemented;
Transaction transfer with created token has been implemented.
 
Monitor
 
During the optimization process the platform monitor was debugged;
API methods that let you to get public methods and variables of  smart contract with the use of its address has been added. Their integration with the platform monitor on the page for a specific smart contract has been fulfilled.
 
Next sprint aims

The display of tokens balances created on the platform according to the Credits standard via platform monitor. This requires the development of a relational database working in conjunction with the blockchain on the platform monitor;
Developing an advanced network settings configurator for node;
Developing the abilities of  a smart contract call with the use of another smart contract;
Development of smart contracts decentralized execution by trusted nodes.