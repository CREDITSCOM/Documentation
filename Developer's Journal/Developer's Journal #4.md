![Dev's journal#4](https://cdn-images-1.medium.com/max/2000/1*uyJgy1rbgNX97F9hGkrHGA.jpeg)
# BFT and BLAKE2s algorithms implemented.
Our technical experts give the main news of the week about the development of the CREDITS platform:

We have moved away from the DPOS consensus algorithm, and implemented a stable version of the BFT algorithm (the so-called “Byzantine generals Algorithm”), which has been optimized for our platform, — says Eugeniy Butyaev CTO & Co-Founder. — The transition to the new algorithm with minimal loss of resources was made possible by the large-scale processing storage architectures and API platforms. I wrote about this in my Twitter, by the way.
There was a planned transition from MD5 (used in the very beginning) to a more robust hashing algorithm Blake2s. This is one of the variants of BLAKE2. It is first of all used in the node validation process to confirm the operation by checksum and the formation of chains of pools. It has the following advantages: improvement of the compression function; reduction in the number of constants; acceleration of data transmission.

We particularly want to mention the development of smart contracts, where we have developed the following features: tips for writing code in the integrated editor, EDS in transaction generation, and a Remote Procedure Call (RPC) for deployment and run. Our developers have amended and implemented website support, and have made changes to the wallet.

For the latest news from our developers, you can follow our CTO Eugeniy Butyaev on Twitter.