# Istio Service Mesh Lab

A hands-on learning project: deploying and studying Istio from scratch on a
self-hosted k3s cluster, managed via GitOps (ArgoCD). Covers traffic
management, resilience, mTLS security, and observability — with real
incidents encountered and resolved along the way.

## Architecture

See [docs/architecture.md](docs/architecture.md) for the full request flow
and component breakdown.

## Stack

- **Virtualization:** VirtualBox VM (Ubuntu Server 24.04 ARM64), Host-only + NAT networking
- **Kubernetes:** k3s (single-node)
- **Service Mesh:** Istio (ingress gateway, sidecar injection, traffic management, mTLS, authorization)
- **GitOps:** ArgoCD
- **Observability:** Prometheus, Grafana, Kiali, Jaeger, Loki

## What's implemented

| Area | Details |
|---|---|
| Traffic management | Gateway + VirtualService, weighted canary routing (v1/v2), fault injection |
| Security | STRICT mTLS (PeerAuthentication), zero-trust access control (AuthorizationPolicy) |
| Observability | Full addon stack via ArgoCD; mesh graph, metrics, tracing |
| GitOps | ArgoCD-managed Istio control plane, gateway, security policies, and demo app |


## Future improvements

- Refactor Application manifests to the "App of Apps" pattern (single root Application)
- Dedicated AppProject instead of `default`
- TLS termination on the Gateway (currently HTTP only)
- Resource requests/limits on all workloads

## Why this project

I work with Istio/Envoy/Kubernetes in production (troubleshooting SNI
mismatches, Envoy SDS/TLS race conditions), but wanted to build a systematic
understanding from the ground up — rather than only reacting to incidents.