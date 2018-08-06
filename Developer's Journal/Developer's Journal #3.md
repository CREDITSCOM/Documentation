![Dev's journal#3](https://cdn-images-1.medium.com/max/2000/1*Xd_SEYKMxpQQL1GpXzSkQw.jpeg)
# Alpha testing by the “Transaction Generator” has now ended.
“Here are the main news of the week: we’ve published a part of our platform source code on Github. This proves that CREDITS blockchain platform is decentralized and peer-to-peer. In a week or two we’ll post another part of the code,” informs Team leader Valentin Antonov. “We are continuing with the alpha testing. To test its capacity we created a “Transaction Generator” and loaded the network to the maximum.”

The generator was waiting for an answer from the network connector on package sending time. We decided to abandon the need for this answer. But to reduce the risk of losing the data during synchronization due to this, the developers have limited the size of the pool to the possible maximum, with datagrams protocol UDP. This has reduced losses of data during transmission and increased processing speed. We implemented a queue of transaction pools on the platform’s kernel.

“Here we got into serious trouble. When the generator started to create an unlimited flow of transactions, a queue of read/write data trough API formed. The transmission streams were jammed, and the monitor did not show up-to-date information for the same data streams.” says CTO Eugeniy Butyaev. — To understand the issue, we changed the storage architecture. Implementation will around three weeks. The entire system, the API and the monitor in particular are going to be updated regularly. We will replace MD5 to BLAKE2s, add EDS, increase the stability of the monitor and expand the functionality of the Web-wallet.

We have done many things for smart-contracts. We have debugged java-apps, and added the ability to save and load the current state of the smart contract when the application restarts. We have added protection to prevent re-saving a smart-contract with an identical address. Additionally, we have improved the built-in code editor in the desktop application and the API for working with transactions.

You can also read fresh news from the developer’s team in Eugeniy Butyaev’s Twitter feed.
