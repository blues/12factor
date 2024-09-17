---
title: 'Cloud-Proxied web RPC'
description: 'Rely on the cloud to map service names to addresses.'
date: 2024-09-11
weight: 6
---

Some embedded devices will require real-time synchronous calls to modern web services. They may fetch data that is essential to the operation of a connected product, for example, to retrieve predicted energy prices in the product’s location and change its operating mode based on the result. Or they may publish data that is mission-critical and requires a low-latency operation, for example, to send a time-sensitive alert when a machine is operating well beyond a safety threshold and requires immediate attention.

**A twelve-factor never stores URLs, addresses, or API keys for these services in its firmware or local storage.** Instead, embedded firmware should refer to remote endpoints by a name (for example, “energyService”) which maps to the remote endpoint and its configuration in a managed cloud solution service. The service operates as a low-latency, transparent proxy which keeps service endpoints and authentication information out of firmware, while allowing the endpoints themselves to change for the purposes of inspection, logging, or redirection, without necessitating a change in the firmware of devices.
