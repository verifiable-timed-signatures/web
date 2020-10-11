---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Verifiable Timed Signatures
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

## Resources

- [Full Paper](/assets/paper.pdf)
- [Linearly Homomorphic Time Lock Puzzle C library](https://github.com/verifiable-timed-signatures/liblhtlp)
