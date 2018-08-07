![Dev's journal#15](https://cdn-images-1.medium.com/max/1000/1*bKzx8nsI1dbOryeDeuDpHQ.jpeg)
The change in the principle of (de)serialization of network packages helped reduce the processing time and improved performance, says Credits CTO Eugeniy Butyaev. A multithread transport module architecture that will enable to refine the network traffic processing and increase the node capacity is being elaborated.

We have devoted considerable time to the platform reworking recently. Firstly, with the node itself. The structure of the array of the next round trusted nodes, including parallel processing modes, has been upgraded. The Main Node fail problem was solved; a new technology to update the network activity at a preset interval, in case of the Main Node fail, has also been added. The pool format has been reworked; the control field containing the list of trusted nodes signed by the previous round writing node has been added. This solution helps prevent the fork creation by a random network node.

There have been significant changes in the transport module of the network. The transport module data structure has been reworked; ring buffers in the data nodes and packages have been implemented for the data redirect hash. The tool for correct packaging, without excessive copying, has been introduced. The package resending function if a problem arises in the network has been implemented. All data packages have been converted into the binary format. The Teredo network protocol for the transfer of IPv6 packages via IPv4 networks using NAT technology is being elaborated and tested as well. Work on smart contracts is comprehensive. The SmartContractGet() method has been remediated as it contained a stub that returned one and the same text to any inquiry. The code for new methods, SmartContractsListGet() and SmartContractAddressesListGet, has been written. Saving of smart contract status has been implemented. New Thrift methods have been integrated to receive and fulfill smart contracts.

The platform’s monitor has been changed drastically. The page-by-page view of units has been implemented in the Home Page. The smart contract history page and display of different networks on the node page have been added. To make the monitor more user-friendly, data on the Home Page are updated automatically.

The full list of bug fixes is as follows:
## Smart Contracts
* SmartContractGet() method was сorrected;
as it contained a stub that returned one and the same text to any inquiry.

* The code for new methods, SmartContractsListGet() and SmartContractAddressesListGet, was written;

for a new Thrift API

* Saving of smart contract status was implemented;

* New Thrift methods were integrated to receive and fulfill smart contracts;

## Node
* Linux portability was implemented;

* CMake was rewritten to simplify the build

* Transition to the binary format of all packages;

* The data structure of the transport module was reworked;

ring buffers in the data nodes and packages were implemented for the redirect hash

* The tool for correct packaging, without excessive copying, was introduced;

* csnode proxy that controls package (de)serialization was introduced;

* Creation of a wrapper around csbd, with a single mutex for the database;

this would ensure thread safety

* Implementation of the package resending function if a problem arises in the network;

* Balance calculation enhancement;

* Changes in the monitor node operation;

* Development of large package transmission/receipt;

* Teredo network protocol was set to transfer IPv6 packages via IPv4 networks using NAT technology;

* The unit format was reworked;

the control field with the list of trusted nodes signed by the previous round writing node and preventing the fork by a random network node was added.

* Upgrading and coordination of the structure of the array of the next round trusted nodes;

including parallel processing modes

* The Main Node fail problem was solved;

* The new semantics of the network activity update at a preset interval, in case of the Main Node fail, was also added.

* The parser operation was improved;

* The parser was fully refactored towards higher performance and updating for the new data structure.

## Monitor
* The page-by-page view of units was implemented in the Home Page;

* The smart contract history page was added;

* The display of different networks on the node page was added;

* Regular automatic data update on the Home Page was added;

* Debugging of pool time display;

## General Improvement
* Improved code;

* Remediated bugs and deficiencies;

* The server logic when responding to redirect was modified;

* Asynchronous multithreading was adapted for incoming connection;

* A supplementary data transfer socket was added;

* The data transfer package was modified and enhanced; line handling was minimized;

* Multithreading problems were solved