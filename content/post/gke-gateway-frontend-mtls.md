---
title: "Frontend mTLS Validation with GKE Gateway"
date: 2026-07-07T17:58:00-07:00
draft: false
author: "Greg Bray"
description: "A guide and example configurations for enforcing frontend mutual TLS (mTLS) validation on GKE Gateways with Global and Regional Cloud Load Balancers."
tags: ["kubernetes", "gke", "gateway"]
---

Configuring [frontend mutual TLS (mTLS)](https://docs.cloud.google.com/kubernetes-engine/docs/how-to/secure-gateway#configure-frontend-mtls) on the [GKE Gateway controller](https://cloud.google.com/kubernetes-engine/docs/concepts/gateway-api) enables zero-trust client authentication directly at the Google Cloud Load Balancing (GCLB) edge before traffic reaches backend workloads. By referencing a ConfigMap containing your trusted client-issuing CA certificates, you can enforce strict client certificate validation across Global External ALBs, Regional External ALBs, and Regional Internal ALBs. Furthermore, GCLB can forward verified client certificate metadata—such as SPIFFE IDs, Subject Alternative Names (SANs), SHA-256 fingerprints, and certificate chains—directly to downstream pods via custom HTTP headers. This guide provides deployment manifests and verification commands using `curl`, `jq`, and `openssl` to test and validate frontend mTLS connections.

See the full guide and example manifests for [GKE Gateway Frontend mTLS](https://github.com/gbrayut/cloud-examples/tree/main/gke-gclb-misc/frontend-mtls) on GitHub.
