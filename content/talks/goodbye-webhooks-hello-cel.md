---
title: "Goodbye Webhooks, Hello CEL: Using Native Validating and Mutating Admission Policies in Kubernetes"
date: 2026-11-01T16:10:00-07:00
draft: false
pin: true
author: "Greg Bray"
summary: "A presentation at KubeCon 2026 on replacing admission webhooks with native in-tree Common Expression Language (CEL) policies."
tags: ["kubernetes", "platform engineering", "security"]
---

**Conference:** [KubeCon + CloudNativeCon North America 2026](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)  
**Date & Time:** November 11, 2026 • 4:10 PM – 4:40 PM MST  
**Location:** Salt Palace Convention Center | Level 2 | Room 255 EF (Salt Lake City, UT)  
**Track:** Platform Engineering  
**Session Link:** [Schedule & Session Details](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/program/schedule/?id=1248888)  
**Slides:** [Download Presentation Slides](https://sessionize.com/download/ictagvew~PvejDLBbmh7K928cm3Qcer.pdf~goodbye-webhooks-hello-cel-greg-bray-kubecon-na-2026.pdf)

---

### Abstract

Admission Controllers and Mutating Webhooks have long been fundamental building blocks for Kubernetes platform extensibility. While powerful, relying on out-of-process requests can introduce significant pain points like increased network latency, complex TLS and cluster bootstrapping steps, and the risk of a failing webhook taking down your entire control plane.

This session highlights the evolution of admission plugins for Kubernetes and demonstrates practical, production-ready examples of the webhook-free world using Common Expression Language (CEL) policies evaluated inside the API Server. The session also explores the architectural tradeoffs of the native ValidatingAdmissionPolicy and MutatingAdmissionPolicy resources, contrasting the simplicity of CEL with full-featured policy engines like OPA Gatekeeper using Rego and Kyverno using CEL.
