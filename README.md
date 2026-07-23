# Istio Service Mesh Lab

A hands-on learning project: deploying and studying Istio from scratch on a
self-hosted k3s cluster, managed via GitOps (ArgoCD). The goal is to build
a solid foundation in service mesh concepts — traffic management, resilience
patterns, mTLS security — and document real-world incidents encountered
along the way.

## Stack

- **Virtualization:** VirtualBox VM (Ubuntu Server 24.04 ARM64), network: Host-only + NAT
- **Kubernetes:** k3s (single-node)
- **Service Mesh:** Istio
- **GitOps:** ArgoCD
- **Observability:** Prometheus, Grafana, Kiali

## Repository structure
docs/
incidents/ # incident write-ups — root cause, diagnostics, fix
manifests/
00-cluster-setup/ # base cluster setup
01-argocd/ # ArgoCD installation and configuration
02-istio-install/ # Istio control plane installation
03-traffic-management/ # Gateway, VirtualService, DestinationRule
04-resilience/ # retries, circuit breaking, fault injection
05-security-mtls/ # PeerAuthentication, AuthorizationPolicy
06-observability/ # Prometheus/Grafana/Kiali
scripts/ # helper scripts


## Why this project

I work with Istio/Envoy/Kubernetes in production (troubleshooting SNI
mismatches, Envoy SDS/TLS race conditions), but wanted to build a systematic
understanding from the ground up — rather than only reacting to incidents.
