---
title: 'Logs'
description: 'Treat logs as event streams.'
weight: 11
toc: false
titleIcon: "fa-solid fa-clipboard-list"
---

Logs provide visibility into the behavior, state, and environment of a running device. Embedded devices commonly write logs to local flash or to removable media like an SD card; but this is only an output format.

Logs are the stream of aggregated, time-ordered events collected from a connected product and which are delivered to a product’s management service either in real-time or on a schedule as dictated by the device’s config. Logs are delivered in a text format, and have no discrete beginning or end, but are intended to flow continuously from the device to cloud as long as the app is operating.

**A twelve-factor thing never concerns itself with the routing or storage of its output stream,** and should not be dependent on the presence of flash or removable media in order to collect or deliver logs. Logs should be delivered to a device’s cloud-based management service and only stored on an edge device when dictated by upload or synchronization policies.

Furthermore, the logging behavior of a device (frequency, type of logs collected, and the granularity of logging) should be driven by the config of a device and managed as environment variables on one or more associated fleets. A twelve-factor device should never embed logging behaviors in firmware unless as default behaviors that can be remotely overridden and managed by the environment.

In a deployment, the event stream for each device will be captured by the cloud management service and routed to one of more final destinations for viewing, processing, or long-term archival. These destinations are not visible to or configurable by the end device, and instead are completely controlled by the management service.

The event stream for a product can be delivered in raw form to an archival service, sent to indexing and analysis services, used in concert with device metadata in a time-series database, or stored in a general-purpose data warehousing system. Regardless of destination, a cloud-managed view of logs as event streams allows device data to “fan out” to any and all destinations as dictated by the changing needs of the product and its users.
