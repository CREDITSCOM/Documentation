![Dev's Journal](https://a.radikal.ru/a35/1804/38/2691aa470b6d.jpg)
# Node optimisation

“Last week, our efforts were mainly focused on Nodes,” says Eugeniy Butyaev, CTO & Co-Founder at CREDITS. “We fixed the node shutdown. Now all connections and sockets shut down correctly. Previously, the database used to shut down properly only by text command. In contrast, pushing an X icon in the node window was likely to be followed by a database error.”
The next fix is the processing of a query about the number of returning nodes on the network. From now on, the Monitor requests the amount network nodes being run and receives information about their quantity and the length of stay in the network for each node.

The third fix is a new node network connection. We’ve removed lengthy time-outs, thus making this process significantly faster.

The fourth fix is the processing of lost nodes. Whenever a node loses connection to the Internet, the network removes it from the list of active and available nodes, thus preventing speed loss, and then attempts to get reconnected by pinging this node until it replies. Furthermore, the current node version is now available for viewing in the app window title.

We’ve updated the functionality of the desktop wallet version. Transaction details now include hash and time of each transaction.

Find all the latest news from our developers on Eugeniy Butyaev’s Twitter.
