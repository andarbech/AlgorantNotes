# AlgorantNotes
Learning Algorant 
## Things to explain 
Explain what Algorand is and how it solves the Blockchain Trilemma.
Explain Pure Proof of Stake.
Explain the types of Algorand Standard Assets and what they can be used for.
Explain smart contracts and smart signatures.
Explain what Atomic Transfers are and what they can be used for.
## What it's Algorant?
Algorand Smart Contracts (ASC1) are small programs that serve various functions on the blockchain and operate on layer-1.
 Smart contracts are separated into two main categories, smart contracts, and smart signatures.
  These types are also referred to as stateful and stateless contracts respectively. 
The type of contract that is written will determine when and how the logic of the program is evaluated.

## How solves the blockchain Trilema?

- In PPoS (pure proof of stake), any token holder can participate in consensus, 
    preventing the existence of powerful central authorities.This protocol is very fast and requires minimal
    computational power per node, giving it the ability to finalize transactions efficiently.
- To add a new block to the chain, the block must be proposed and verified by groups of users who are randomly and secretly selected using a verifiable random function (VRF).
    The VRF takes a secret key and a value and produces a pseudorandom output, with a proof that anyone can use to verify the result. 
    The VRF functions similar to a lottery and is used to choose leaders to propose a block and committee members to vote on a block.
- Even as the number of participating users increase, the number of users selected for each block proposal and validation do not increase
    allowing Algorand to preserve high speed and scalability.A user account must be online to participate in the consensus protocol. 
    To reduce exposure, online users do not use their spending keys (i.e., the keys they use to sign transactions) for consensus. 
    Instead, a user generates and registers a participation key for a certain number of rounds.

## Pure Proof of Stake Vs Proof of Work?

Proof-of-work (PoW) is an approach in which users race to solve very complex cryptographic puzzles, also known as mining. 
The first one to solve the puzzle has the right to append the next block to the chain and is rewarded for doing so.
 Bitcoin, Ethereum, and many other blockchains use this approach. PPoS has numerous advantages over PoW.

First, PoW is extremely expensive and wasteful. 
Mining often requires specialized hardware to be competitive and consumes an enormous amount of electricity. 
Only professional miners who have made the capital expenditure necessary to buy racks of hyper-specialized 
mining equipment can expect to make a profit. 