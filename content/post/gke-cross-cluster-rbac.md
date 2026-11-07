---
title: "Cross-Cluster RBAC on GKE using Workload Identity Federation"
date: 2026-06-22T18:00:00-07:00
draft: false
pin: true
author: "Greg Bray"
description: "A guide and practical examples for configuring cross-cluster Kubernetes RBAC using Workload Identity Federation (WIF) on GKE."
tags: ["kubernetes", "security", "gke"]
---

[Workload Identity Federation (WIF) for GKE](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/workload-identity) allows teams to grant fine-grained IAM and Kubernetes RBAC permissions directly to a pod's Kubernetes Service Account (KSA) across separate GKE clusters, GCP projects, and organizations without managing static, long-lived credentials. By combining projected service account tokens, Application Default Credentials (ADC), and GKE DNS-based control plane endpoints, workloads can seamlessly authenticate to remote Kubernetes API servers using their federated identity (`serviceAccount:PROJECT.svc.id.goog[NAMESPACE/KSA]`). This guide demonstrates complete configurations and verification commands, covering local and remote RoleBindings, token inspection with `kubectl auth whoami`, and cross-cluster API calls.

Check out the full guide and example manifests in the [cloud-examples repository on GitHub](https://github.com/gbrayut/cloud-examples/tree/main/gke-cross-cluster-rbac).
