---
layout: page
title: /Error Correction/
permalink: /error-correction/
---
___
___
In **digital communications** and **information storage**, *error correction* is the task of
restoring an information message's original content -- typically, a sequence of <u>classical</u>
[bits](https://en.wikipedia.org/wiki/Bit) -- whenever errors occurred during reception or retrieval.

In **quantum information and computation**, the analogous task is to construct a set of reliable
*logical* <u>quantum</u> bits ([qubits](https://en.wikipedia.org/wiki/Qubit)) from an ensemble of
unreliable *physical* qubits in order to enable fault-tolerant quantum information processing.

*error correction* aims at providing a set of
reliable *logical* <u>quantum bits (qubits)</u> from a set of unreliable <u>physical qubits</u>.

The *classical* and *quantum* information domains fundamentally differ by the nature of the
information elements they rely on: while a classical bit is an abstract representation of a
two-state classical system, the qubit is a representation of the state of an elementary
quantum system that can be, at any given time instant, in one of two classical states or 
in a complex superposition of the two classical states simultaneously.

A discussion about which elementary classical and quantum systems are being used in order to
carry the information would be outside the scope of this document.
Suffice it to say that, unlike the digital electronic circuits that are typically used for
classical information processing, there is a variety of very different quantum systems used to
process and store qubits, and all those systems turn out to be unreliable, meaning that they
are unable to preserve their status with small deviations for a sufficiently long time so as to
allow processing.


___

[*Error correction*](https://en.wikipedia.org/wiki/Error_correction_code) encompasses a broad
family of methods used to detect and correct errors in data transmission and storage, thereby
ensuring data integrity and reliability.

Error correction aims at restoring an information message’s original content after it has been
corrupted. Here, an information message is typically a sequence of (classical)
[bits](https://en.wikipedia.org/wiki/Bit).

In **digital communications**, a received message may be corrupted as an effect of receiver
noise, radio wave propagation phenomena, interference by other signals, or imperfections in
the transmission and reception devices.
Likewise, in **information storage** a retrieved message may be corrupted by noise,
intersymbol interference, imperfections in the storage and retrieval devices.

In **quantum information**, the analogous task is to construct a set of reliable <u>logical quantum
bits (qubits)</u> from an ensemble of unreliable <u>physical qubits</u>, thereby enabling
fault-tolerant quantum information processing.

The distinction between classical and quantum error correction arises from the nature of the
underlying information carriers.
A classical bit represents one of two discrete states of a classical system, whereas a qubit
corresponds to the state of a quantum system. Unlike a bit, a qubit may exist not only in one of two
basis states but also in a coherent superposition of these states, with amplitudes described by
complex values.

A detailed discussion of the physical substrates used to encode information lies beyond the scope of
this document. It is sufficient to note that, while classical information processing is typically
realized using reliable digital electronic circuits, quantum information processing relies on a
variety of distinct physical platforms (e.g., trapped ions, superconducting circuits, photonic
systems).
All current implementations suffer from significant noise and decoherence, limiting the ability of
physical qubits to retain their states with high fidelity for durations sufficient to perform
computation.
This intrinsic unreliability necessitates the development of quantum error correction techniques.

___




In a large family of embodiments, error correction is done by appending to each information message
a **redundancy** sequence so as to form a *codeword*.
The redundancy sequence is determined based on the message content according to a predefined *rule*.
At the receiver side, a decoder checks the received message and the received redundancy sequence by
applying the abovementioned *rule*, and in that way determines whether any errors occurred and where
and how the messages was transformed by those errors.
The decoder then produces a decoded message which is supposed to faithfully reproduce the original
message with high probability.

In another family of embodiments, error correction is done by mapping each information message to a
corresponding **codeword** according to an injective (invertible) map.


### The maths

For a given message $\mathbf{m} \in\{0,1,\ldots \}^K$, 
