# Private RKE2 Kubernetes Platform with GitOps

## Overview

A hands-on project focused on building and operating a private three-node Kubernetes platform using RKE2, Cilium, Longhorn, GitOps, and progressive delivery.

The project explores Kubernetes infrastructure, container networking, persistent storage, automated application deployment, configuration management, and workload recovery.

The implementation emphasizes understanding the underlying technologies through practical deployment, validation, troubleshooting, and failure testing.

## Architecture

| Component | Technology |
|---|---|
| Kubernetes Distribution | RKE2 |
| Cluster | 3-node control-plane with embedded etcd |
| Container Networking | Cilium |
| Datapath | eBPF |
| Service Proxy | kube-proxy replacement |
| Traffic Management | Kubernetes Gateway API |
| Gateway Implementation | Cilium Gateway API / Envoy |
| Distributed Storage | Longhorn |
| GitOps | Argo CD |
| Progressive Delivery | Argo Rollouts |
| CI | GitHub Actions |
| Manifest Validation | Kustomize and Kubeconform |

## Implemented Components

### 1. Kubernetes Infrastructure
- Deployed a three-node RKE2 cluster.
- Configured the control-plane and embedded etcd.
- Validated node readiness and cluster operation.

### 2. Container Networking
- Installed Cilium as the Kubernetes CNI.
- Enabled eBPF-based networking and kube-proxy replacement.
- Deployed Kubernetes Gateway API resources with Envoy.
- Configured Gateway API listeners and HTTP routing.

### 3. Distributed Storage
- Deployed Longhorn distributed block storage.
- Configured persistent volumes and claims.
- Tested data persistence across Pod deletion and recreation.

### 4. GitOps with Argo CD
- Deployed applications from a Git repository.
- Configured automated synchronization and self-healing.
- Tested configuration drift correction.
- Validated automatic resource pruning after removing resources from Git.

### 5. Progressive Delivery with Argo Rollouts
- Implemented Canary deployment.
- Implemented Blue-Green deployment.
- Tested preview and active services.
- Verified application versions using HTTP requests.
- Tested GitOps-driven rollback by reverting the desired application image in Git.

### 6. CI Pipeline with GitHub Actions
- Created an automated GitHub Actions workflow.
- Triggered validation on pushes and pull requests targeting the main branch.
- Built Kubernetes application manifests using Kustomize.
- Validated available Kubernetes resource schemas using Kubeconform.
- Successfully executed the CI workflow on GitHub Actions.

## Validation and Testing

The following tests were performed:

| Test | Result |
|---|---|
| Three-node RKE2 cluster readiness | Passed |
| Cilium networking deployment | Passed |
| Gateway API resource programming | Passed |
| Gateway external IP reachability | Pending further troubleshooting |
| Longhorn PVC provisioning | Passed |
| Persistent data after Pod recreation | Passed |
| RKE2 server service failure and recovery | Passed |
| Argo CD automated synchronization | Passed |
| GitOps self-healing | Passed |
| GitOps resource pruning | Passed |
| Canary rollout | Passed |
| Blue-Green promotion | Passed |
| Blue-Green GitOps rollback | Passed |
| GitHub Actions CI validation | Passed |

## Known Limitations

- Gateway API resources are successfully programmed, and NodePort-based access was verified. However, direct access to the configured Gateway external IP remains unresolved.
- The RKE2 recovery test covered a server service failure and recovery, not a complete virtual machine or physical node failure.
- The cluster uses a configured control-plane endpoint rather than a dedicated highly available virtual IP or external load balancer.
- Kubeconform ignores missing schemas for custom resources whose CRD schemas are not included in its default schema catalog.

## Repository Structure

The repository contains Kubernetes application manifests, Argo CD application definitions, progressive delivery configurations, and CI workflow files.

## Environment

- Operating System: Ubuntu 24.04
- Kubernetes Distribution: RKE2
- Container Networking: Cilium
- Distributed Storage: Longhorn
- GitOps: Argo CD
- Progressive Delivery: Argo Rollouts
- CI: GitHub Actions

## Learning Outcomes

Through this project, I gained hands-on experience with:

- Kubernetes cluster administration.
- Container networking and eBPF fundamentals.
- Persistent storage and workload recovery.
- GitOps principles and automated reconciliation.
- Progressive delivery strategies.
- CI automation and Kubernetes manifest validation.
- Troubleshooting distributed infrastructure.

## Project Status

Core implementation and CI validation are completed. Final documentation, architecture visualization, and remaining Gateway external connectivity troubleshooting are ongoing.
