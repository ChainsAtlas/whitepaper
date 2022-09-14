## ChainsAtlas: Multi-Chain Interoperability Network / New Blockchain technology

> **Note**: this README contains only excerpts, please have a look at the PDF version https://raw.githubusercontent.com/ChainsAtlas/whitepaper/main/whitepaper.pdf

> **Note**: If you like the whitepaper, please consider adding a star to the repository

ChainsAtlas is a new blockchain technology that leverages virtualization and multiple distributed ledger technologies with a smart contract feature to create a cross-chain decentralized homogeneous network for distributed software and data processing.

ChainsAtlas use a dual consensus protocol, *Proof-of-Stake* (PoS) and a novel class of useful *Proof-of-Work* (PoW), called **Proof-of-Strategy** (PoSg). In the context of PoSg, strategists provide the optimal execution strategy for a given bytecode under a variable set of constraints, and they operate nodes called Pythians that validate those strategies. With PoS, Pythians enable cross-chains communication and provide constant updates on the supported blockchains state.

<p align="center">
  <img src="https://miro.medium.com/max/2400/1*gu_cgcbMm5QM5Ri7S2kAsg.jpeg" alt="Distributed Decentralized Processing Network" width="85%"/>
</p>

Distributed Decentralized Processing Network
============================================

The Distributed Decentralized Processing Network (**DDPN**) leverages the best features of each blockchain implementation to execute software through management and virtualization units. These units are smart contracts deployed on multiple blockchains. The management units are responsible for managing transactions, wallets, and communication with virtualization units to guarantee the proper execution of the client software with an optimal strategy. The virtualization units create a distributed Runtime for software, including those not designed to run on a blockchain, by deploying smart contracts that simulate a specific machine instruction set. Further, as explained in more detail in the following sections, the **DDPN** allows users to (1) run code that surpasses the transaction size limit and (2) asynchronously execute bytecode via segmentation and execution transfer.

Proof of Strategy
=================

The network enables transactions between entities that include clients and strategists. The client provides the bytecode and a set of constraints, such as cost range and privacy. The strategist provides the optimal execution strategy that minimizes the execution time and cost while respecting the constraints set by the client.

#### Chained submission: 

If a given offer size surpasses the transaction size limit, the bytecode can then be supplied in chunks as long as the size of each chunk, except for the last one, is equal to the transaction size limit. This approach minimizes the number of necessary submissions to the management units.

<p align="center">
  <img src="https://miro.medium.com/max/2400/1*LHvkODVasVX8oODH_gX9Nw.png" alt="Distributed Decentralized Processing Network" width="75%"/>
</p>


Management units
================
The management units are smart contracts deployed on all the supported blockchains, each holding the same state information. In order to maintain synchronization of state and the strategy order book, management units verify consensus among Pythians before validating requests to update its state or submit a valid strategy.\ As the core management component of the network, management units hold multiple responsibilities.

Virtualization units
====================

The virtualization units are smart contracts composed of three
components:

-   **Virtualization manager**: manages the execution flow of the unit
    and receives/transmits data as indicated in the joined metadata
    supplied by the management units;

-   **Logger**: documents the transaction by computing hashes of the
    variable parts of the transaction and storing the results in the
    immutable memory of the underlying blockchain;

-   **Simulator**: interprets and executes the bytecode.

The simulator is a 32bit machine simulator based on a modified version of the DLX instruction set, a RISC processor architecture.


Chains characteristics
===========================
Each blockchain used in the network must have a smart contract feature and a “chain profile” and be Turing complete. The chain profile is a set of characteristics that define it from the point of view of the management units. These profiles serve as standardizing structure that allows for a unified approach to comparing the different blockchains of the network and validating the compatibility of a given strategy with a given underlying blockchain.

<p align="center">
  <img src="https://miro.medium.com/max/2400/1*y2ta_PWO12_5VZ1RTh-hBQ.png" alt="Chains profiles" width="75%"/>
</p>


#### Bytecode segmentation

The transaction size limit is one of the possible diverging characteristics among smart contract implementations. Considering virtualization units, this translates to a limitation of the size of the client’s bytecode to be run on the blockchain. The DDPN addresses this limitation by segmenting the bytecode to run it within the limits of each virtualization unit’s underlying blockchain.

#### Execution transfer

The execution transfer process handles the bytecode segmentation. Each bytecode is considered a transaction, and splitting occurs when a given transaction size exceeds the underlying Blockchain limit.

#### Synchronous and asynchronous execution


The execution of a bytecode that uses multiple transactions can occur in two manners, Synchronous or Asynchronous. The advantage of the latter, when possible, is that it requires less time for completion.

When the execution is synchronous, the bytecode segmentation is subject to:

<p align="center">
  <img src="https://miro.medium.com/max/2400/1*-HYo417q-tdBFFvIVmdqiw.png" alt="independent segmentation" width="50%"/>
</p>

Network components overview
===========================

-   **Athena**: The governance token that gives voting rights and
    staking rewards in Hermes (utility token).

-   **Hermes**: The utility token generated by the staking of Athena and
    used to pay for smart contract execution on the network.

-   **Client**: The user who wants to execute software under a set of
    preferences and conditions in exchange for an amount of Hermes.

-   **Strategist**: The entity that supplies the management unit with an
    execution strategy that matches the clients' settings while
    minimizing the processing cost in exchange for Hermes.

-   **Pythia**: A node operated by a strategist. It enables cross-chain
    communication between various units and evaluates and oversees
    strategy execution. To run a Pythia node, one must stake Athena.

    **Note**: The term \"Pythians\" refers to a collection of Pythia.

-   **Management unit**: The smart contract that manages Hermes and
    Athena balances, verifies consensus over the optimal strategy,
    oversees elections and controls the virtualization units.

-   **Virtualization unit**: Smart contracts that handle the execution
    of the client's bytecode. They are deployed on various blockchains.

-   **Proof-of-Strategy** : A novel useful *Proof-of-Work* where the
    strategist (the Proof-of-Strategy equivalent of the miner) earns
    Hermes by providing the optimal strategy for executing the client's
    software under a set of constraints.

-   **Chain profile**: A set of characteristics that define each of the
    supported blockchains in the network in a standardized manner.

-   **Election cycle**: A time-limited event for Pythians to vote and
    update the chain profiles of supported blockchains. All
    non-measurable characteristics of a given chain profile can be
    updated (such as the decentralization score). Pythians can also vote
    to exclude existing blockchains or to include new ones in the
    network.

-   **Agora DAO**: A decentralized autonomous organization that
    regulates the ChainsAtlas ecosystem based on the voting of its
    members. Every Athena staker, e.g., Pythia, is a member of the Agora
    DAO and has a right to vote.

-   **OLYMPUS treasury**: A reward pool that collects part of the Hermes
    paid by the client to distribute among Pythians and the grant fund
    at the end of a 28 days period. Each Pythia's reliability score
    dictates its share of the OLYMPUS treasury. The use of the grant
    fund is decided through the Agora DAO, in which all Pythians have a
    vote.

-   **Gerousia**: An assembly of developers that decides over final
    approval of changes to the code base under strategic goals set by
    the Agora DAO. The Gerousia is elected in regular intervals.

