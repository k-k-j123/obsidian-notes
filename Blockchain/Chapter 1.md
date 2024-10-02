It is an immutable, decentralized, digital ledger that is used to store transaction records securely on a distributed computer network

Blockchain is immutable meaning it cannot be updated once it is created. This makes it extremely secure and impossible to tamper

It completely transparent meaning everybody can see it. It does not need any central authority as it is managed in a peer-to-peer network.

Blockchain is a combination of cryptography and computer networking.

**Client Server System** - in this type of network all the node in a network are connected to a central server. The server is more powerful than client and its sole purpose is to server the client

**Peer-to-peer system** - in this type of network there no central server and each node is directly connected to each other. Each node has equal authority, and responsibility

## Evolution of Blockchain
1.  2008 -- 2013: blockchain 1.0 (bitcoin emergence)
	Satoshi Nakamoto published the Bitcoin whitepaper in 2008, introducing the first blockchain network. Bitcoin's blockchain enabled secure, decentralized, and transparent peer-to-peer transactions.
2. 2013 -- 2015: blockchain 2.0 (Ethereum development)
	Ethereum (2014) introduced smart contracts, expanding blockchain's capabilities beyond digital currency.
3. 2016 -- 2018 : the future
	Number of projects based on blockchain technology were developed. this include smart contract, Dapps and many more that leveraged features of blockchain.

## Blockchain vs Database

| Blockchain                             | Database                            |
| -------------------------------------- | ----------------------------------- |
| It is decentralized ledger             | It is collection of related records |
| Stores data in form of blocks          | Stores data in form of tables       |
| stored in a p2p network                | stored in a centralized server      |
| support only read and create operation | support CURD operations             |
| It is much secure                      | it is less secure                   |
| more complex                           | less complex                        |
| immutable                              | mutable                             |

## Concept of Blockchain
The blockchain consist of number of blocks that are linked together in a distributed network 
each node in the network has its own copy of the ledger. So whenever a new block is added to the network it is added to each node 

**Basic terms of blockchain** 
1. Block -- is a data structure that stores multiple records of transactions together 
2. chain -- is sequence of blocks one after other
3. transaction -- refers to smallest unit in blockchain that is a record of a transaction
4. hash function -- a function that takes and input and gives an encoded output 
5. consensus -- set of rules or protocols that manage the blockchain network
6. miner -- a special type of node that does the work of solving an advanced mathematical problem to validate a block
7. node -- a device that participates in the blockchain
8. distributed/shared ledger -- the shared blockchain that is accessible to everyone

## Structure of block in blockchain

|               |                                                                                               |
| ------------- | --------------------------------------------------------------------------------------------- |
| block header  | contains metadata                                                                             |
| hash          | is used for validation contains hash value                                                    |
| previous hash | hash of previous block in the chain                                                           |
| block height  | number of blocks preceding it in the blockchain                                               |
| nonce         | a random number that mines use to solve a mathematical puzzle in mining process . (PoW)       |
| difficulty    | degree of difficulty to find hash value for given target, represents the difficulty of mining |
| timestamp     | the date and time of creation and insertion of the block in blockchain                        |

## Working of blockchain
![[working of blockchain.png]]

## Types of blockchain

### Public Blockchain
Public blockchains are fully decentralized, open-source, and accessible to anyone. They prioritize transparency, security, and decentralization. Anyone can join, participate, and view transactions. Examples include Bitcoin and Ethereum.
- Permissionless access
- Transparent transactions
- Decentralized control
- Immutable transaction
eg -- bitcoin 

### Private Blockchain
Private blockchains are restricted to specific users or organizations. They offer secure, private, and centralized control. Access is controlled, and transactions are encrypted. Examples include enterprise-specific blockchains like JPMorgan's Quorum.

Private blockchains are ideal for internal accounting, supply chain management, and confidential business transactions.

### Consortium Blockchain
Consortium blockchain are managed by more than one organization or group of people. they are typically used by the government 
eg- Energy web foundation, R3 etc

### Hybrid blockchain
It is a combination of public and private blockchain. It provides the security of private blockchain and provide flexibility of public blockchain, thus providing best of both worlds
Data which is highly sensitive is stored in private blockchain and less sensitive data is stored in public part 


## Layered Architecture of Blockchain
Application Layer
	this layer consist of software and programs that allow us to interact with the block chain examples include DAPPS and various API's
Consensus Layer
	this layer is responsible for validating the blocks and has  set of protocols that help in the management of Blockchain example include PoW, PoS etc.
Network Layer
	this layer consist of various nodes and devices that are connected with each other through p2p network. allows different devices to synchronize and communicate with each other
Data Layer
	Data Structure of blockchain are represented as linked list includes two primary elements pointer and data. each block points to the next block 
Hardware Layer
	this layer comprises of all the hardware components of blockchain like computers, physical network components etc.