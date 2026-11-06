# Private RKE2 Kubernetes Platform with GitOps

## Overview

A hands-on project to build and operate a private Kubernetes platform using RKE2, Cilium, distributed storage, GitOps, and progressive delivery.

The project focuses on understanding Kubernetes infrastructure, networking, storage, application deployment, automation, and failure recovery.

## Architecture

- Kubernetes Distribution: RKE2
- Cluster: 3-node control-plane and embedded etcd
- CNI: Cilium
- Datapath: eBPF
- Service Proxy: kube-proxy replacement
- Ingress and Traffic Management: Kubernetes Gateway API
- Storage: Longhorn
- GitOps: Argo CD
- Progressive Delivery: Argo Rollouts
- CI/CD: Planned

## Implemented Components

- Three-node RKE2 cluster.
- Cilium installation and kube-proxy replacement.
- Gateway API with Envoy.
- Longhorn distributed storage.
- Persistent Volume testing.
- Node service failure and workload recovery testing.
- Argo CD installation and CLI access.

## Project Structure

- `docs/`: Architecture and implementation documentation.
- `infrastructure/`: Infrastructure configuration.
- `applications/`: Kubernetes application manifests.
- `argocd/`: Argo CD applications and configuration.
- `rollouts/`: Progressive delivery manifests.
- `ci-cd/`: CI/CD pipeline configuration.

## Upcoming Work

- GitOps application deployment and synchronization.
- Automated drift correction and pruning tests.
- Canary and Blue-Green deployments with Argo Rollouts.
- CI/CD pipeline implementation.
- Final validation and documentation.

## Environment

Ubuntu 24.04, RKE2, Cilium, Longhorn, and Argo CD.
