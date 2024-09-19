---
title: 'Identity'
description: 'Build for a single identity that can fan out when needed.'
weight: 12
toc: false
titleIcon: "fa-solid fa-circle-user"
---

### Build for a single identity that can "fan out" when needed.

The twelve-factor thing is a device that is designed to turn a machine, container, or otherwise disconnected thing into a connected product. When connected, the product needs to be identifiable as a single unit to management services, solution services and cloud applications, while enabling the embedded part of the product to be ephemeral so that it can be serviced and replaced, as needed.

A connected product is commonly made of of multiple "units" that each have their own identity. For example:

- The main asset has a product **serial number** that the customer uses to identify the device.
- The embedded electronics that are placed in a product has its own **device identifier** used by the product maker to identify the embedded component. If this modular unit is replaced, the serial number must be re-bound to a new device identifier in the process.
- Depending on the RATs in use, the device includes multiple **transport identifiers** like a cellular SIM, a different satellite SIM, LoRaWAN DeviceEUI, the serial number, or distinguished name in a TLS X.509 certificate.

Each layer of a product requires some form of identity, but the only identity that matters in a connected product is the customer’s product serial number, and that everything must be able to be derived from that.

**The twelve-factor thing harmonizes device identity by enabling the embedded device to be associated to a product in the process of bringing it online**. One way to accomplish this is by ensuring that every connected product includes a barcode, or better yet, a QR code for easy association. When using these approaches, during the installation process, an installer can scan the code, which has the embedded device identifier included, and enter (or scan) the Serial Number of the end product that the embedded device is being associated to. This association is then replicated to cloud management and application services so that fleet managers are always able to identify the device and the product that it is connected to.

One final advantage of this approach is that it allows for a connected product to retain its identity, even if the underlying embedded device needs to change. While it should be rare, some number of devices across a fleet of connected products will need to be decommissioned and replaced over the lifetime of a deployment. By using the approach above, when a device is replaced, the device id to product serial number association is updated and replicated to the management service without impacting the end customer view of the connected product.
