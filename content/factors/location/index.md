---
title: 'Location'
description: 'Build for "best" location, regardless of underlying methodology.'
weight: 7
toc: false
titleIcon: "fa-solid fa-location-dot"
---

### Build for "best" location, regardless of underlying methodology

Connected products inherit their “location” from the underlying Radio Access Technologies (RATs) they have access to. Devices with a GPS/GNSS module, the appropriate antenna, and a clear view of the sky have access to satellite-based positioning. Obtaining this information, however, is a power-intensive operation meaning that this data is inherently stale depending on how the device is powered, its frequency of polling, and the speed at which it is moving. Devices without GPS/GNSS or devices operating indoors or inside of a Faraday cage do not have access to this information and must take other approaches if location is needed.

Embedded devices rarely have the ability to determine their own location, regardless of underlying RAT, or to harmonize that location when multiple location-based approaches are available. A connected product should always defer the calculation of a “best” location for this device to a cloud service.

Outside of GPS/GNSS, the calculation of location requires a coordination between device and cloud. For example, a cellular device can provide identifying details about the cell tower through which it is transmitting data, which a cloud service can use to determine tower location as an approximation of device location. Better still, a device can scan for all of the cell towers nearby and send an array of tower information, including the device’s signal strength relative to each tower, which the cloud service can use to multilaterate the location of the device.

Similarly, a Wi-Fi device can perform a scan of nearby access points, send an array containing a collection of visible access points and signal strength of each relative to the device, and the cloud service can multilaterate a device’s location, even in indoor settings.

Likewise, a LoRaWAN gateway may have access to the same cell tower or Wi-Fi AP information, depending on its own backhaul, and a cloud service can approximate the location of LoRa nodes based on gateway location, or combine gateway location with packet-level TDOA/RSS to triangulate the location of a note in the network.

**The twelve-factor thing utilizes multiple RATs, for example, GPS/GNSS, cellular, and Wi-Fi, and relies on its cloud service to deliver a “best” location to service consumers.** This allows devices in the field to operate in a power-conscious way, and defer calculation of location to the service, which can perform multiple levels of multilateration across RATs and select the most accurate location based on the fidelity of the calculation (for example, the number of multilateration points) and its recency.

As an end result, consumers can rely on the service to deliver a harmonized sense of device location, without taking on the cost and burden of performing these calculations themselves.