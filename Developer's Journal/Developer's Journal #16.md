![Dev's journal#16](https://credits.com/uploads/ap/news/6ec0347fb59f459aaa5ec2683fc9194c.jpg)
Credits team is glad to present a new “Developers Journal” update! This article summarises what was done since the latest software release in details and what needs to be done further before next software release.
 

Moreover, we are ready to announce the date of Credits platform Internal Load Test - the August, 31. You will be able to follow the testing process on official Youtube channel and Credits Monitor. We are going to publish thorough technical testing report few days after the end of testing.
 

At the moment, new version of software is under internal testing, we are running the process of bugs and flaws elimination. Developers have found solutions to major problems which have been determined before, for example routing or VPN and synchronization issues. You can use Credits Monitor Mainnet tab to figure out that VPN issue was fixed and every node IP address is visible now.



 

What has been done since the last update?
 

1) Routing issue has been solved (VPN)
Routing issues with the nodes operating with NAT have been fixed as follows on three levels:
1. Network now operates under IPv6 protocol;
2. Some internet providers don’t support this protocol, in this case IPv4 white addresses will be used;
3. The nodes that are beyond NAT and don’t have white address will use routing according Bittorrent protocol and in this case one “White” node will serve as a router for 3 and more “grey” nodes.
Thus, we’ll be able to involve a range of available addresses for connection to Credits platform.
 

 

2) Synchronization problem is fixed
It is required to have an up-to-date blockchain database containing all blocks that have been signed and sent earlier for a node to become trusted and to participate in transaction validation process as well as in blocks processing.
To solve this problem synchronization according to numerical order has been implemented. Thus, in the absence of any block a node won’t be able to calculate hash of all chain and therefore confirm its right to become a trusted node.
 

3) Consensus algorithm and network architecture was optimized
 

Creating a new network protocol and block synchronization required a significant rework of the network architecture part. Changing network level and implementing full and partial synchronization significantly affected the network consensus work and required implementing additional verification functions not only in the Byzantine Fault Tolerance (BFT) protocol, but also in the level of incoming packets, blocks and etc verification by a common node.
 

To prevent excessive transfers of blocks around the network and to minimize blocks delivery time to all network nodes a transfer mechanism to all neighboring nodes was implemented through the spanning tree. Reading of  such a big data volume from the chain is very time-consuming. Caching was implemented to reduce the time required for this process in-memory, however RAM requirements have been increased to 6 GB.
 



 
What developers are currently working on?
 

1) Increase of CREDITS monitor memory volume.

Developers came to a conclusion, that platform’s monitor requires larger memory volume as it is reading all data from the platform. This results in substantial time consumption, especially while loading all transactions of a wallet or a smart contract. We decided to use relational database to solve this problem , reading data from which is much faster than directly from a blockchain.

2) Smart contracts functionality expansion

For a smart contract to be executed simultaneously by several users a dynamical change in its state is required several times per round. For smart contracts state or mutating getter is a transaction with a variable, its change can happen once per round. An appropriate way to solve these kind of tasks is to use divided smart contract state. It is a change in the code of the same smart contract for multiple users. By the end of a round the smart contract state is combined and continues to function within that smart contract.

3) Transaction assembly implementation

To increase transaction processing speed it is planned to use so called transaction assembly, in which every node keeps collecting transactions constantly. This removes the necessity of  sending transactions to the main node for its processing by network consensus; otherwise we are limited by bandwidth of the main node at the time of generating unconfirmed transaction pool.

4) Electronic digital signature (EDS) update

Size of a transaction is a key factor to achieve required processing speed. Thus, EDS is a significant part of that size (64 bytes). In case of performance of 1 million transactions per seconds we have 64 MB of data to be sent to all network in a second and the matter of the size is a critical one for the platform as a whole. We’re considering the possibility to use Schnorr signature, provable cryptographic security of which has a signature length of 48 bytes. We’re also considering a possibility of using multi-signature.
 



 

Developers team decided that the next software update needs to meet the requirements of stable Candidate Release version which will not have serious bugs and which will be ready for full value testing from partners and independent developers side. Current version which Internal Load Test is going to be conducted on is an intermediate one and doesn't have problems described above. To solve issues mentioned in the article developers require approximately 3 weeks. We plan to publish new version in the second part of September. Follow our updates on social media and check first stage of testing process. Stay tuned, guys!