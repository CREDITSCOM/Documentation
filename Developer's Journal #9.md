![Dev's Journal#9](https://c.radikal.ru/c16/1804/7d/d7d88b66f33c.jpg)
#Full readiness for private beta test of platform

“The main thing we did last week was preparing everything for a private beta test of the platform,” says Eugeniy Butyaev, CTO & Co-Founder, hardly shy about his joy. “If you want to join our private beta test, please send your request by email to support@credits.com. Describe in your letter why you’re engaged with blockchain, assess your knowledge of this technology, specify your testing experience. Don’t forget to mention what interests you about our project.”


Do you want to know how we were preparing for beta testing?
First, we revised storage architecture for faster access to information, plus we optimized data compression system Snappy.

Second, we finalized the run-time version of the network Consensus: data synchronization and dPoS+BFT. Full description of the consensus will be available through Github soon.

Third, we removed all restrictions on the number of transactions per pool. Previously, there was a restriction of 256 transactions per pool max. The aim was network load control.

Fourth, full-fledged API is now in place.

A few words about updates.
System kernel: we optimized the synchronization code for transaction pool and fixed in-storage transaction pools time synchronization.

Desktop wallet: we configured the logging of apps, got the wallet key file saving format fixed, debugged API method calls for more stable operation in multithreaded environments.

Summing it up, we would like to thank the most active community members who are already helping test our product, thus making it better. @mambrose @Xela101 @crypto_dipper @DeltaSA — thank you guys for being with CREDITS!
