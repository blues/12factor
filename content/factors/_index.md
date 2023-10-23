---
title: 'The Twelve-Factor Connected Device'
date: 2023-10-23T15:14:39+10:00
weight: 1
---

## Introduction
We’ve entered the era of data and AI. An era where the value of any business process or application is measured by insights unlocked, business models enabled, and decisions accelerated. In this era, there’s more need than ever to connect the unconnected: to bring the physical world online so that the data in our machines, factories, cities, and vehicles can unlock those insights, business models, and decisions. In this data and AI era, embracing an architecture of cloud-connected devices has never been more imperative. And yet, engineers and builders are locked into Radio Access Technologies (RATs), perpetually subject to network sunsets, scrambling to maintain systems insecurely attachable from the internet, and building systems that either do not scale, or can not scale economically.

The enemy of hyper-scale systems that are reliable, secure, and economical is a Do-It-Yourself (DIY) approach: piecemeal chip-down design that connects an off-the-shelf low-cost modem to a bespoke or packaged IoT platform.

The modem is dead. The IoT Platform is dead.

It’s the era of standardized cloud toolchains, standard cloud app talent, hardware security, myriad cloud data stores, and myriad wireless transports. It’s an era of harmonization and driving interoperability across RATs, cloud stores, and physical device services through API-driven approaches.

The twelve-factor connected device is a methodology for building connected apps that:

- Use API-first approaches to abstract away the unique constraints and implementation details of common RATs.
- Are cloud-centric, allowing devices to function as true clients with a secure pipe to dependent services and capabilities.
- Are suitable for deployment on modern cloud platforms, obviating the need for bespoke or packaged IoT platforms;
- And can scale up without significant changes to hardware, firmware, tooling, architecture, or development practices.

The twelve-factor methodology can be applied to apps written in any programming language, for any embedded target (whether MCU or SBC), to target any modern RAT, and which use any combination of cloud services (cloud-edge service, database, queue, memory cache, etc).

## Background
Connected devices present unique challenges that pure software applications do not face. These devices operate at the intersection of software and hardware, often in remote environments, and under constraints like limited computational resources, and power availability. They must be secure, and remain operational over long periods (and distances) without human intervention.

The absence of broadly-accepted standards and the inconsistent implementation approaches dictated by Radio Access Technologies (RATs) has led to a fragmented ecosystem, with deployed devices varying widely in their quality, security, interoperability, and maintainability. And while standards bodies and industry groups exist and continue to work to pave common ground for connected solutions, we believe a practical, principled approach is needed to complement these efforts. Drawing from lessons learned in the early days of cloud-native software development, many of which were captured brilliantly in the 12-Factor App methodology, we’ve set out to codify principles to guide builders of connected solutions.

Drawing from the real-world experience of developers, system architects, and operations professionals, the Twelve-Factor Connected Device methodology is a roadmap for the next generation of connected devices. These principles prioritize simplicity, resilience, and a strong affinity between device and cloud, ensuring that connected devices will function, remain secure, and evolve long after deployment.

## Who Should Read This Document?
Any developer building connected applications which bring physical objects “online.” Product managers who plan and design such applications. Ops and deployment engineers that manage such applications.
