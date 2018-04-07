# P2P Storage of Verifiable Credentials/Claims

# Motivation

The motivation for such a network is explained in the paper on RWoT
2018 Spring. [TODO: Add link to published version]

# Goals

1. Store DIDs on a p2p network.
1. Store verifiable credentials on the same network.
1. Nodes expose an HTTP api to accept data to store and to returm data
   sought.
1. Before storing any verifiable credentials nodes first check if the
   data can be verified according to the declared protocol being
   used. Node must be supporting that protocol, else the data is not
   stored.
1. Once the data is stored at a node, the p2p network replicates the
   data on all nodes in the network using a gossip protocol.
   
# Components

1. Gossip Protocol: use the (gossip layer developed by hyperledger)[https://github.com/hyperledger/fabric/blob/master/docs/source/gossip.rst]
1. Data store: (LevelDB)[https://github.com/golang/leveldb]
1. HTTP gateway: Most probably use (Gorilla)[http://www.gorillatoolkit.org/] here
1. Loadable validation plugins: Provide means to load Go packages

# Development effort

I want to reuse existing code as much as possible. I don't want to
have us building a new p2p layer for example or an API framework or a
new Data Store. The challenge is to reach out and convince the
decentralisation community that such a simple data store for
verifiable credentials is worth using.
