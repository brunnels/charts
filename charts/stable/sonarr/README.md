# sonarr

![Version: 15.2.1](https://img.shields.io/badge/Version-15.2.1-informational?style=flat-square) ![AppVersion: v3.0.6.1342](https://img.shields.io/badge/AppVersion-v3.0.6.1342-informational?style=flat-square)

Smart PVR for newsgroup and bittorrent users

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/Sonarr/Sonarr>
* <https://github.com/k8s-at-home/container-images>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.2.0 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install sonarr k8s-at-home/sonarr
```

## Installing the Chart

To install the chart with the release name `sonarr`

```console
helm install sonarr k8s-at-home/sonarr
```

## Uninstalling the Chart

To uninstall the `sonarr` deployment

```console
helm uninstall sonarr
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install sonarr \
  --set env.TZ="America/New York" \
    k8s-at-home/sonarr
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install sonarr k8s-at-home/sonarr -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/k8s-at-home/sonarr"` | image repository |
| image.tag | string | `"v3.0.6.1342"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| metrics.enabled | bool | See values.yaml | Enable and configure Exportarr sidecar and Prometheus serviceMonitor. |
| metrics.exporter.env.additionalMetrics | bool | `false` | Set to true to enable gathering of additional metrics (slow) |
| metrics.exporter.env.port | int | `9794` | metrics port |
| metrics.exporter.env.unknownQueueItems | bool | `false` | Set to true to enable gathering unknown queue items |
| metrics.exporter.image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| metrics.exporter.image.repository | string | `"ghcr.io/onedr0p/exportarr"` | image repository |
| metrics.exporter.image.tag | string | `"v0.6.2"` | image tag |
| metrics.prometheusRule | object | See values.yaml | Enable and configure Prometheus Rules for the chart under this key. |
| metrics.prometheusRule.rules | list | See prometheusrules.yaml | Configure additionial rules for the chart under this key. |
| metrics.serviceMonitor.interval | string | `"3m"` |  |
| metrics.serviceMonitor.labels | object | `{}` |  |
| metrics.serviceMonitor.scrapeTimeout | string | `"1m"` |  |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| probes | object | See values.yaml | Configures the probes for the main Pod. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

All notable changes to this application Helm chart will be documented in this file but does not include changes from our common library. To read those click [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common#changelog).

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

### [15.1.0]

#### Changed

- Uplifted Sonarr version to v3.0.6.1342

### [15.0.0]

#### Changed

- **BREAKING**: Refactored Prometheus metrics section to add rules. Enabling metrics automatically enables the serviceMonitor and exporter sidecar.

### [14.0.0]

#### Changed

- Refactoring of the Exportarr sidecar and Prometheus podMonitor. This is a breaking change if it was enabled previously.

### [13.0.0]

#### Changed

- Upgraded the common library dependency to version 4.0.0. This introduced (potentially) breaking changes to `initContainers` and `additionalContainers`. Be sure to check out the [library chart](https://github.com/k8s-at-home/library-charts/blob/common-4.0.0/charts/stable/common/) for the up-to-date values.

### [12.0.0]

#### Changed

- **BREAKING**: Upgraded the common library dependency to version 3.0.2. This introduces several breaking changes (`service`, `ingress` and `persistence` keys have been refactored).
  Be sure to check out the [library chart](https://github.com/k8s-at-home/library-charts/blob/common-3.0.2/charts/stable/common/) for the up-to-date values.

### [11.0.0]

#### Changed

- **Breaking**: swap linuxserver.io images for k8s@home image

### [1.0.0]

#### Added

- Initial version

[15.1.0]: #1510
[15.0.0]: #1500
[14.0.0]: #1400
[13.0.0]: #1300
[12.0.0]: #1200
[11.0.0]: #1100
[1.0.0]: #100

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
