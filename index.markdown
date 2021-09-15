---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Verifiable Timed Signatures
usemathjax: true
---

## About

Verifiable Timed Signature (VTS) scheme allows one to time-lock a signature on a
known message for a given amount of time *T* such that after performing a sequential
computation for time *T* anyone can extract the signature from the time-lock.
*Verifiability* ensures that anyone can publicly check if a time-lock contains
a valid signature on the message without solving it first, and that the signature
can be obtained by solving the same for time *T*. This work formalizes VTS, presents
efficient constructions compatible with BLS, Schnorr, and ECDSA signatures, and
experimentally demonstrates that these constructions can be employed
in practice. On a technical level, we design an efficient cut-and-choose protocol
based on the homomorphic time-lock puzzles to prove the validity of a signature
encapsulated in a time-lock puzzle. We also present a new efficient range
proof protocol that significantly improves upon existing proposals in terms of
the proof size, and is also of independent interest. While VTS is a versatile tool
with numerous existing applications, we demonstrate VTS’s applicability to
resolve three novel challenging issues in the space of cryptocurrencies.
Specifically, we show how VTS is the cryptographic cornerstone to construct: 
1. Payment channel networks with improved on-chain unlinkability of users involved
in a transaction 
2. Multi-party signing of transactions for cryptocurrencies without any on-chain notion of time 
3. Cryptocurrency-enabled fair multi-party computation protocol.

## OpenSquare: Decentralized Puzzle Solving

Repeated Modular Squaring is a versatile computational operation that has led to practical constructions of timed-cryptographic primitives like time-lock puzzles (TLP) and verifiable delay functions (VDF) that have a fast growing list of applications. While there is a huge interest for timed-cryptographic primitives in the blockchains area, we find two real-world concerns that need immediate attention towards their large-scale practical adoption: Firstly, the requirement to constantly perform computations seems unrealistic for most of the users. Secondly, choosing the parameters for the bound $$\mathbf{T}$$ seems complicated due to the lack of heuristics and experience.

We present OpenSquare, a decentralized repeated modular squaring service, 
that overcomes the above concerns.
OpenSquare lets clients outsource their repeated modular squaring computation via smart contracts to any computationally powerful servers that offer computational services for rewards in an unlinkable manner. 

OpenSquare naturally gives us publicly computable heuristics about a pre-specified number ($$\mathbf{T}$$) and the corresponding reward amounts of repeated squarings necessary for a time period. 
Moreover, OpenSquare rewards multiple servers for a single request, in a sybil resistant manner to incentivise maximum server participation and is therefore resistant to censorship and single-points-of failures.
We give game-theoretic analysis to support the mechanism design of OpenSquare: (1) incentivises servers to stay available with their services, (2) minimizes the cost of outsourcing for the client, and (3) ensures the client receives the valid computational result with high probability.
To demonstrate practicality, we also implement OpenSquare's smart contract in Solidity and report the gas costs for all of its functions. 
Our results show that the on-chain computational costs for both the clients and the servers are quite low, and therefore feasible for practical deployments and usage.


## Resources

- [VTS Paper](https://eprint.iacr.org/2020/1563.pdf)
- [OpenSquare Paper](/assets/opensquare.pdf)
- [Linearly Homomorphic Time Lock Puzzle C library](https://github.com/verifiable-timed-signatures/liblhtlp)
