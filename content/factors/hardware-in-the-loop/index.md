---
title: 'Hardware-in-the-Loop'
description: 'Extend testing from the cloud to physical and virtual devices.'
weight: 13
toc: false
titleIcon: "fa-solid fa-check-double"
---

In the modern era, testing is not just a nice-to-have, but a must have for all forms of application and product development. And while web and cloud application developers have long embraced a number of testing approaches, both manual and automated, testing embedded applications has lagged behind due to the constraints and challenges of developing in this environment.

**The twelve-factor app, through an embrace of all of the factors above, unlocks all forms of testing including automated testing against physical devices, often called Hardware-in-the-loop (HiL).** Product builders should use the device-to-cloud connection between an embedded device and its management service to test firmware updates, cloud application updates, as well as to facilitate unit tests of a controller device, integration tests of a controller in its product at the point of manufacturing, and burn-in tests during deployment. All of these tests can be performed in an end-to-end manner during development, and replicated at scale.

The twelve-factor thing also embraces emulation and simulation as a companion to physical testing, or Simulated HiL (SHiL), either through open-source tools like [QEMU](https://www.qemu.org/) and [native_sim](https://docs.zephyrproject.org/latest/boards/native/native_sim/doc/index.html), as well as test runners, like [Twister](https://docs.zephyrproject.org/latest/develop/test/twister.html), which can execute against physical and virtual devices. Emulation and Simulation can be used to mock upcoming features and capabilities of a physical product while a hardware modification is in process, or operate alongside physical devices for scale testing, to simulate fleet behaviors, or rapidly prototype scale behaviors of application services early in the development cycle.

![An image of the processing for using a ROM bootloader to update firmware](/images/hil.png)
