---
title: 'Authentication'
description: 'Apply a cloud-centric security model.'
weight: 10
toc: false
titleIcon: "fa-solid fa-lock"
---

### Apply a cloud-centric security model

**A twelve-factor thing never stores keys, certs or secrets in flash or removable media, and never relies on the cloud management service for key creation or rotation.** Instead, a connected product should always ensure the presence of a secure enclave or Hardware Security Module (HSM) integrated into the part of the product responsible for communication with the cloud management service over one or more RATs. The HSM is responsible for device authentication to the cloud service and never delivers its keys to the edge device.

Cloud-based certs on the device management service should never be shared with devices and should be rotated if and when root certificates change. Even though the twelve-factor thing is a client device, the security model should be thought of as an inverse of how PC desktop security is managed relative to cloud services. It is essential to first protect the service against client spoofing, then to protect an individual device against cloud-based Man-in-the-Middle attacks.
