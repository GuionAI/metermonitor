# metermonitor

Flux CD GitOps repository for observability and monitoring tools.

## Components

| Component | Purpose | Namespace |
|-----------|---------|-----------|
| Headlamp | Kubernetes dashboard | headlamp |
| OpenMeter | Usage metering | openmeter |
| Grafana | Metrics visualization | grafana |

## Structure

```
flux/
├── clusters/dev/          # Entry point Kustomizations
├── infrastructure/
│   ├── sources/           # Helm repositories and OCI registries
│   └── namespace/dev/     # Namespace definitions
├── headlamp/base/         # Headlamp HelmRelease
├── openmeter/base/        # OpenMeter HelmRelease
└── grafana/base/          # Grafana HelmRelease
```

## Helm Charts

- **Headlamp**: `https://kubernetes-sigs.github.io/headlamp/` (v0.38.0)
- **OpenMeter**: `oci://ghcr.io/openmeterio/helm-charts/openmeter`
- **Grafana**: `https://grafana.github.io/helm-charts` (v10.2.0)

## Usage

Import this repo into your Flux-managed cluster by adding:

1. GitRepository source pointing to this repo
2. Kustomization referencing `./flux/clusters/dev`

See [flicknote-deploy](https://github.com/GuionAI/flicknote-deploy) for integration example.
