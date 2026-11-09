---
title: "Isolated AI Workloads with GKE Agent Sandbox"
date: 2026-09-20T17:20:00-07:00
draft: false
author: "Greg Bray"
description: "An overview of running isolated, disposable AI agent runtimes on GKE using Agent Sandbox, gVisor, and Managed Workload Identity."
tags: ["kubernetes", "gke", "ai", "sandbox"]
keywords: ["kubernetes","gke","gvisor","sandbox","SandboxWarmPool","SandboxClaim"]
external_url: "https://github.com/gbrayut/cloud-examples/tree/main/gke-agent-sandbox"
---

[GKE Agent Sandbox](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/machine-learning/agent-sandbox) is built on the open-source [Kubernetes SIGs Agent Sandbox](https://agent-sandbox.sigs.k8s.io/) project and provides secure, disposable execution environments designed for AI agents that generate and run untrusted code on Kubernetes. By pairing gVisor or microkvm kernel-level isolation with warm pools (`SandboxWarmPool` and `SandboxClaim`) for low-latency startup, it offers a hardened runtime platform for single-replica agent workloads. The example demonstrates end-to-end setup, managing secrets with Secret Manager CSI and Projected Volumes, and configuring SPIFFE-based mTLS using Managed Workload Identity (MWLID).

See the full guide and example manifests for [GKE Agent Sandbox](https://github.com/gbrayut/cloud-examples/tree/main/gke-agent-sandbox) on GitHub.
