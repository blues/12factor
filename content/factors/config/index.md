---
title: 'Config via Fleets'
description: 'Organize device by fleet & store config in the cloud.'
date: 2024-09-11
weight: 5
---

A device should never be treated as a group of one, even from the first Prototype. **The twelve-factor thing instead uses the “fleet” as the predominant organizational paradigm** and the way that a connected product manages the lifecycle, deployment location, and behavior of devices.

A fleet, in this context, is a non-exclusive grouping of devices that exhibit similar behaviors as dictated by the scope of the fleet’s purpose. For example, an “operational” fleet may represent devices that have been deployed in the field and operating normally, while a fleet named “quarantine” could be used for devices as they first come online if there’s a need for manual review before approval and migration into an operational fleet. “Repair” could be used for devices undergoing diagnosis or analysis of anomalous behavior, and “decommissioned” for devices that have been removed from operation, but whose data (and metadata) is useful for postmortem analysis and service improvement.

In this paradigm, a device can belong to multiple fleets if a need exists to further subdivide based on location, use case, or even the end customer of the product provider. Fleets can and should be polymorphic by their nature and the behavior of an individual device should be the sum of the behaviors dictated by the fleets to which it belongs.

With fleets as the organization paradigm, device configuration should be managed via the cloud and multicast to fleets (and thus devices) using collections of key-value pairs called *environment variables* (often shortened to *env vars* or even *env*).

A thing’s configuration, or config, is everything that is likely to vary from one fleet to the next, or from one device to the next depending on its state. This could be:

- Sensor sampling or data synchronization frequency
- The behavior of a managed actuator
- Logging behaviors like frequency, the types of logs collected, or when to deliver logs to the cloud management service
- General device behaviors as dictated by a service level agreement with a product manufacturer’s end customer
- Service endpoints for data routing

*Config*, which takes the shape of key-value pairs that are easily sent to and parsed by an embedded device, should be managed in the cloud and replicated to affected devices as they are changed or modified, or as new devices enter a fleet. Embedded device firmware reads config, and responds to config changes to update the behavior of a device.

By organizing around fleets, devices inherit the config, behavior, and intelligence of that fleet and all devices in it. As devices move between fleets, whether by design or by necessity, they benefit from a cloud-centric view of configuration, and automatically adapt their behaviors as the config of the fleets to which they belong changes.