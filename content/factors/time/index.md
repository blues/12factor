---
title: 'Time'
description: 'Ensure devices always keep time.'
weight: 8
toc: false
titleIcon: "fa-solid fa-clock"
---

### Ensure devices always keep time

Connected products should keep time and append time to every captured sensor reading or log, even when a connection to an underlying transport is not present. When a device is powered and is still offline, or a connection has been lost, an internal counter should be used as a stand-in for captured time until a transport or cloud-based connection is made and time is obtained. When time is obtained, the captured time of offline readings should be reconciled by subtracting the internal counter from the time obtained from a transport or service.

There is no time-series without time, and **a twelve-factor thing ensures that the time a reading is taken, an action is performed, a log is captured, a state changes, a connection is made, and events are uploaded to the cloud include an accurate and reliable time that management and application services can rely on.**

![An image of a twelve-factor thing managing time locally and reconciling with a cloud service](/images/time.png)

