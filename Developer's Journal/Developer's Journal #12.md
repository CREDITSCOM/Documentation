![Dev's journal#12](https://cdn-images-1.medium.com/max/1000/1*wq2Dgv1WmcFxRQKtIqkVpA.jpeg)
# How do we calculate the transaction fee?
“The development team has reduced the volume of a pool-recorded transaction from 808 bytes to 150 bytes. It will allow us to avoid problems with storage oversizing associated with network replication and to increase its productivity,” Eugeniy Butyaev, CTO at CREDITS, has shared.

As for the most important and anticipated news, we have implemented the system’s fee calculation algorithm. The amount of payment directly depends on the number of transactions and the number of trusted nodes in a round, the sender’s transaction activity, and the physical transaction size. The fees for every component are limited to the minimum and maximum values. In other words, even if the sender’s transaction activity is extremely high, the sender will never pay more than the maximum limit — and vice versa: in the case of low activity, the sender will never pay less than the minimum limit. We will publish a detailed description of the algorithm in a separate article on Medium next week.

In addition, we have updated our GitHub page.