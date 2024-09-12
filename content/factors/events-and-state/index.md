---
title: 'Events & State'
description: 'Synchronize state and event flow between the device & cloud.'
date: 2024-09-11
weight: 4
---

In an embedded device, events are the artifacts created by the operating behavior of a device (such as reading from a sensor or actuation) while state represents the condition of the device (for example it’s voltage and location) at a point in time.

The twelve-factor thing is connected from birth, and its events and state should always be synchronized and harmonized with its cloud service. Events should never be stored on a device permanently, merely cached until the next point of synchronization and purged. State can and should be stored on a device, but should always be replicated to the device’s management service so that the cloud service and downstream consumers have an accurate view of the device’s condition and behavior. State, and even event data when template-driven, should share a common and predictable schema across device and cloud so that data on the wire can be compressed for the sake of speed and efficiency.

For storage, either on a device or cloud service, there are four dominant patterns that a developer may consider when representing events or state:

- Bi-directional queues, or buckets of event data that is stored on a source until the next opportunity for delivery to a target.
- Replicated Key-Value pairs, which are always reconciled between device and service upon connection. These can take the form of shared “database” files or cloud-like key-value pairs.
- Proxied, real-time RPC, where the cloud service performs a remote request on behalf of a device and delivers the result to the device at the earliest opportunity.
- Flexible datatypes driven by templates or data formatters.

The twelve-factor thing assumes that events and state will be synchronized to and replicated with a cloud service, but it does not store or send data in a way that prevents any form of downstream storage, whether they are “hot” time-series and relational databases used to drive apps and their user interface, “hot” and “warm” databases used for analytics, or “cold” data warehouses.