---
title: 'Transport'
description: 'Target a harmonized API that operates across transport protocols.'
date: 2024-09-11
weight: 3
---

Radio Access Technologies (RATs) like cellular, Wi-Fi, LoRa, and Satellite have long required engineers to intimately understand and design for the features and constraints of the transport in order to bring a product online. These features and constraints impact both hardware (antenna selection, matching network design) and firmware (AT Commands, IP or NIDD communication) in such a way that product builders have historically designed for and locked themselves into a single RAT.

**The twelve-factor thing, however, can and should be RAT-agnostic and target harmonized transport with a unified developer experience, while allowing transport-specific protocols, whether IP-based or otherwise, to operate transparently at the network layer.** And rather than requiring firmware engineers to embed RAT-specific AT Commands, MQTT, or CoAP messages into firmware, developers should be able to target a standards-based, harmonized API that operates across major RATs and allows connected product builders to seamlessly transition between RATs without the need for the underlying firmware to change.

To be sure, a Harmonized API does not mean that there is parity between all transports, or that the API operates at the lowest common denominator between transports. Rather, a harmonized API unifies the commonalities across transports, while embracing that differences need to be surfaced to the developer. Firmware applications operating across transports need “hints” from the API that inform the app of the capabilities of its current transport. For example:

- An app communicating via NIDD, UDP, over satellite or LoRaWAN will want to ramp down its synchronization frequency and use “packet abstraction” aspects of the API.
- A webcam or real-time voice endpoint will want to use an “asynchronous stream abstraction” via the API and maintain a continuous connection to its service.
- Most other apps will simply use asynchronous “enqueue object”, “dequeue object”, “get named object” or “put named object” forms of API.

At the transport level, devices should never be on the internet, regardless of RAT, and should communicate only with its management and solution cloud services using secure synchronous or asynchronous tunnels.

All of the above requires a module with a harmonized API that operates across RATs and translates common API requests into RAT-specific protocols and commands. The end result is a connected product that can be built once, deployed anywhere, and connected using the RAT most appropriate for the product’s deployment location.