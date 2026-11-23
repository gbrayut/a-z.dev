---
title: "Running OSS Istio on GKE Sandbox and Agent Sandbox"
date: 2026-11-19T15:38:00-07:00
draft: false
pin: true
author: "Greg Bray"
summary: "Examples for running OSS Istio sidecars in GKE Sandbox or GKE Agent Sandbox (gVisor and microVM)."
tags: ["kubernetes", "gke", "sandbox"]
keywords: ["kubernetes","gke","istio","istio-cni","gvisor","microvm","kata","sandbox","SandboxTemplate","SandboxWarmPool"]
external_url: "https://github.com/gbrayut/cloud-examples/blob/main/istio-misc/sandbox-istio.md"
---

Running upstream Istio on [GKE Sandbox](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/sandbox-pods) (`gvisor`) node pools requires installing the [Istio CNI node agent](https://istio.io/latest/docs/setup/additional-setup/cni/#installing-with-helm) via Helm so pods inject the unprivileged `istio-validation` init container rather than `istio-init`. When pairing Istio sidecars with [GKE Agent Sandbox](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/machine-learning/agent-sandbox) (`SandboxTemplate`, `SandboxWarmPool`, and `SandboxClaim`), the default-deny `networkPolicyManagement: Managed` posture also requires setting `dnsPolicy: ClusterFirst` and allowing egress to `kube-dns` and `istiod` so `istio-proxy` can initialize. For clusters that also run Kata Containers (`microvm`), which cannot use CNI-based network setup, the guide demonstrates configuring a custom `kata-init` sidecar injection template to inject the in-pod privileged `istio-init` container.

See the full guide and example manifests for [OSS Istio on GKE Sandbox](https://github.com/gbrayut/cloud-examples/blob/main/istio-misc/sandbox-istio.md) on GitHub.
