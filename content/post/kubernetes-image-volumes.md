---
title: "Mounting OCI Images with Kubernetes Image Volumes"
date: 2026-06-04T10:51:00-07:00
draft: false
author: "Greg Bray"
description: "A look at Kubernetes native Image Volumes (KEP-4639) for mounting OCI container images directly as read-only volumes in Pods."
tags: ["kubernetes", "storage", "gke"]
---

[Kubernetes Image Volumes](https://kubernetes.io/docs/concepts/storage/volumes/#image) were introduced as Beta in Kubernetes 1.35 via [KEP-4639](https://github.com/kubernetes/enhancements/issues/4639) and allow pods to mount OCI container images directly as read-only volumes without requiring init container copy workarounds or custom volume plugins. This native volume source makes it easy to inject shared binaries, debugging utilities, static configurations, or OCI-packaged artifacts directly into workload filesystems. The example manifest demonstrates mounting a utility container image into a workload on GKE, including runtime compatibility notes for `subPath` support across containerd versions.

Check out the full manifest and testing commands in the [cloud-examples repository on GitHub](https://github.com/gbrayut/cloud-examples/blob/main/gke-storage-misc/imagevolume.yaml).

See the full example manifest for [GKE Image Volumes](https://github.com/gbrayut/cloud-examples/blob/main/gke-storage-misc/imagevolume.yaml) on GitHub.
