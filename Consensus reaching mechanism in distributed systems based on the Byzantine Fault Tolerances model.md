**#Consensus reaching mechanism in distributed systems based on the Byzantine Fault Tolerances model**

*Selection of head node and trusted nodes*
++Phase 1++ Procedure for selecting the head node and trusted nodes to participate in the consensus mechanism.
The key requirements for the head node and trusted nodes is the availability of an updated ledger and adequate capacity. This is achieved through the following actions.
Each node of the network sends the last block hash available at this node to the previous round node by which the last block is recorded on a blockchain (see the chart below). A certain amount of time is spared for this process, and all nodes from which no hash is received in this time interval drop out of the competition for eligibility to participate in the consensus procedure (being filtered out by node capacity). The node receiving these hashes compares them with the hash of the block recorded by the receiving node during the previous round. This is followed by cutting off all nodes sending an unmatched hash. Accordingly, any node with an outdated ledger is unable to become the head node or a trusted node for the next round.



![Tab1](https://b.radikal.ru/b13/1805/64/3fea64a9d228.jpg)

++Phase 2++ There can be *m* number of nodes participating in the transaction voting procedure in every round (trusted nodes and the head node). The node writing the last block generates the length list *n* of nodes with an updated ledger (outcome of Phase 1). The nodes *3m* are randomly selected from the nodes *n*. Then *m* number of nodes is randomly selected from these nodes *3m* , the first one is appointed as head node for the next round, and the remaining as trusted nodes for the next round.
*Transaction voting procedure*
++Phase 3++ The transactions generated in the system while the head node and trusted nodes are being selected (during Phases 1 and 2) are sent from all nodes to the head node *(to be revised since an integrated transaction acceptance pool should be in place for the process synchronization purposes).* The head node generates a vector of transactions eligible to be included in the ledger. This vector is sent by the head node to all trusted nodes. // e.g., std::vector <transaction>
  
  
![Tab2](https://d.radikal.ru/d32/1805/f7/db7b7ad1249d.jpg)

++Phase 4++  Once this vector is received, each trusted node verifies every transaction in respect of its ledger within this vector and generates, for example, std::map<transaction, bool>. After that each trusted node forwards this container to the remaining trusted nodes.
++Phase 5++ Accordingly, the first round of exchange between trusted nodes is followed by the generation of, e.g., std::map<node_id, std::map<transaction, bool> > at each trusted node. After that each trusted node forwards this container to all remaining trusted nodes, which constitutes the second round of exchange.
++Phase 6++ The second round of exchange is followed by the generation of the final decision tree at each trusted node. E.g., std::map<node_id, std::map<node_id, std::map<transaction, bool> > >. Each trusted node goes through this tree and determines the majority in respect of each transaction.


![Tab3](https://d.radikal.ru/d02/1805/b3/2b3217cab617.jpg)

++Phase 7++ The previous phase is followed by the generation of an approved only transaction vector at each trusted node, with the vector coinciding at each honest node. It is, in fact, a finished block to be recorded onto a ledger with trustworthy transactions only.


![Tab4](https://b.radikal.ru/b38/1805/9e/cff16c8d6161.jpg)

*Protection against ledger recording by a malicious node*
++Phase 8++ A new block will be recorded onto a ledger by one of the trusted nodes which makes a decision on the block that is identical with most of other nodes (reliably honest node). The procedure for intercepting betrayers from among trusted nodes is performed by verifying the outcome of decision-making during Phase 6. All nodes whose decisions are mismatched with the majority decision are removed from the list of trusted nodes which can potentially record a new block onto a ledger. The remaining list will be identical at all honest nodes. Any node is randomly selected from the remaining nodes.
++Phase 9++ The node selected during the previous phase generates a hash of the new block, records the new block onto a ledger, and sends the new block to all nodes system-wide. Then a new round begins.
