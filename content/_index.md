---
weight: 0
title: "The Twelve-Factor Thing"
description: "A framework for building modern connected products"
titleIcon: "fa-solid fa-list-ul"
---

The App of the future is a connected thing, and much as the Twelve-Factor App methodology addressed the inherent complexity of building robust, secure, scalable cloud apps and services in a straightforward manner, this methodology, the Twelve-Factor Thing, intends to do the same for the managed, intelligent edge device and products based upon them.

![An image of a twelve-factor thing communicating through management and solution services](/images/device.png)

## Background
Connected devices present unique challenges that pure software applications do not face. These devices operate at the intersection of software and hardware, often in remote environments, and under constraints like limited computational resources and power availability. They must be secure, and remain operational over long periods (and distances) without human intervention.

The absence of broadly-accepted standards and the inconsistent implementation approaches dictated by Radio Access Technologies (RATs) has led to a fragmented ecosystem, with deployed devices varying widely in their quality, security, interoperability, and maintainability. And while standards bodies and industry groups exist and continue to work to pave common ground for connected products, we believe a practical, principled approach is needed to complement these efforts. Drawing from lessons learned in the early days of cloud-native software development, many of which were captured brilliantly in the [Twelve-Factor App methodology](https://12factor.net), we’ve set out to codify principles to guide builders of connected solutions.

Drawing from the real-world experience of developers, system architects, and operations professionals, the **Twelve-Factor Thing** methodology is a roadmap for the next generation of managed, intelligent edge devices. These principles prioritize simplicity, resilience, and a strong affinity between device and cloud, ensuring that connected devices will function, remain secure, and evolve long after deployment.

## Introduction
We’ve entered the era of data and AI. An era where the value of any business process or application is measured by insights unlocked, business models enabled, and decisions accelerated. There’s more need than ever to connect the unconnected: to bring the physical world online so that the data in our machines, factories, cities, and vehicles can unlock those insights, business models, and decisions. In this data and AI era, embracing an architecture of cloud-connected devices has never been more imperative. And yet, engineers and builders are locked into Radio Access Technologies (RATs), forever at the mercy of network sunsets, scrambling to maintain systems insecurely attachable from the internet, and building systems that either do not scale, or can not scale economically.

The enemy of hyper-scale systems that are reliable, secure, and economical is a Do-It-Yourself (DIY) approach: piecemeal chip-down design that connects an off-the-shelf low-cost modem to a bespoke cloud application or packaged IoT platform.

The modem is dead. The IoT Platform is dead. This document explains why.

The twelve-factor thing is a methodology for building managed, intelligent edge devices. They are:

- **Managed** because connected devices should never be completely isolated from service infrastructure that can update, interoperate with, and “heal” devices as needed.
- **Intelligent** because they provide the ability to offload key algorithms, decision-making, and inference from the cloud to the edge. More than simple gateway devices for cloud backhaul, these devices have embedded sensors, compute and serve a specific purpose.
- **Edge Devices** because they operate at the nexus between the cloud and the physical world.

This methodology describes an approach for building products that:

- Use **API-first approaches** to abstract away the unique constraints and implementation details of common RATs.
- Are **cloud-connected yet edge-centric**, allowing devices to function as true clients with a secure pipe to dependent services and capabilities, with the intelligence to operate and make decisions at the edge, when needed.
- Are suitable for **deployment** on modern **cloud platforms**, obviating the need for bespoke or packaged IoT platforms;
- And can **scale up** without significant changes to hardware, firmware, tooling, architecture, or development practices.

The twelve-factor methodology can be applied to apps written in any programming language, for any embedded target (whether MCU or SBC), to target any modern RAT, and which use any combination of cloud services (cloud-edge service, database, queue, memory cache, etc).

## Who Should Read This Document?
Any developer building connected applications which bring physical objects “online.” Product managers who plan and design such applications. Ops and deployment engineers that manage such applications.

{{< treeview
  display="tree"
/>}}