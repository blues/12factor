---
title: 'Firmware'
description: 'Treat firmware as a cloud-managed aspect of your app.'
weight: 9
toc: false
titleIcon: "fa-solid fa-file-arrow-down"
---

In the context of a connected product, *firmware* is the collection of assets that make up the runtime of a device. This often includes:

- A core binary that represents the application running on the device, its dependent libraries, RTOSes, and the like.
- On-device ML models if the device includes edge intelligence capabilities.
- Any static assets (image files, localization files, audio files, etc) that the application uses in its normal operation.
- A software-based bootloader, if the processor that underpins the device does not include a ROM-based bootloader.

**A twelve-factor thing treats its firmware as a resource that can be updated or changed at any time and does not, in its normal operation, behave in a way that would prevent a remotely initiated firmware update.** Critically, a device’s firmware is delivered by the cloud management service asynchronously and applied to the device using a process that runs independent from the main application process. This could be through a soft bootloader or an isolated partition on the main processor, or through an external module running an independent process.

In the latter case, for processors with ROM-based bootloaders, connected products should be designed with a physical connection between the external module responsible for firmware updates and the “strapping pins” available on the processor for placing the device into bootloader mode so that the external module can apply the firmware update by streaming bytes to the device over a serial connection. This hardware-based firmware update process is superior to other approaches because it facilitates the remote rollback and/or recovery of “bricked” devices without necessitating physical access to the device.

![An image of the processing for using a ROM bootloader to update firmware](/images/firmware.png)


Furthermore, a cloud-based approach to firmware management allows for connected products that can be remotely flashed with temporary diagnostic images which change the behavior of the device for the purpose of data collection to aid troubleshooting, before returning ephemerally to normal operation with the original firmware.

Finally, as firmware is a collection of assets that can be versioned independently, the cloud management service of a twelve-factor thing should provide the facility to deliver assets, for instance and updated edge ML model file, independently of one another and for the external firmware delivery module to be able to update only the changed assets without disturbing the normal operation of the device.
