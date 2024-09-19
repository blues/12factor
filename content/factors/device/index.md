---
title: 'Device'
description: 'Build Edge Devices to serve exactly two cloud services - a Management Service and a Solution Service - not to be general internet clients or servers for cloud-based apps.'
weight: 2
toc: false
titleIcon: "fa-solid fa-microchip"
---

### Build Edge Devices to serve exactly two cloud services: a Management Service and a Solution Service

The twelve-factor thing is not an internet-connected device. A large part of the power of the modern internet comes from that fact that any node can talk to any other node. Every browser endpoint reaches out to an immense number of apps and servers. Every modern server federates myriad service components, from auth to commerce to CDN. The modern internet far more often resembles a mesh than a client-server architecture.

By contrast, most embedded devices:

- Run a single app that is rarely self-updated
- Connect to and authenticate with a single management service
- Use that management service as a proxy for anything else that needs to be done
- Are fearful of intrusion or attack from unknown actors, services and clients

All too often, connected products are built with the mindset, intentional or otherwise, that devices operate as mini “servers” of sensor data and device metadata to internet “clients” that receive and forward that data.

The twelve-factor thing is built expressly to be a client that may come and go and which communicates with a small number of known services. They are not servers of internet clients and should not expose themselves or their data as endpoints or sockets on the internet. Embedded devices come and go depending on their need to conserve power or state while in motion, and no direct access (and thus attack) by unknown actors should ever be possible from the internet.

**The twelve-factor thing is an embedded, connected device that is expressly *off the internet***. To the device, this connection is a point-to-point secure channel with exactly two cloud services using non-public networks and VPN tunnels. To these services, this represents a hub-and-spoke secure channel, with each spoke being completely isolated from all others.

The first service is the **management service**, which exists to deliver firmware updates to the device, when needed, update the configuration of the device, monitor the device’s health and connection, and receive metadata about the device, its state, and behavior.

The second service is the **solution service**, which exists to receive application data from the device, and forward that data to authorized receivers, such as cloud application stores, or archival services. The solution service is also the secure proxy for device access to other third party APIs and cloud services.

![An image of a twelve-factor thing communicating through management and solution services](/images/device.png)

Together, these two services represent the only access that a connected product has to the outside world. This device is an embedded networked device, not an internet-connected device.
