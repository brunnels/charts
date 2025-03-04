# cryptpad

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![AppVersion: v4.12.0-nginx](https://img.shields.io/badge/AppVersion-v4.12.0--nginx-informational?style=flat-square)

cryptpad helm package

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/xwiki-labs/cryptpad-docker>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.0.1 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install cryptpad k8s-at-home/cryptpad
```

## Installing the Chart

To install the chart with the release name `cryptpad`

```console
helm install cryptpad k8s-at-home/cryptpad
```

## Uninstalling the Chart

To uninstall the `cryptpad` deployment

```console
helm uninstall cryptpad
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install cryptpad \
  --set env.TZ="America/New York" \
    k8s-at-home/cryptpad
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install cryptpad k8s-at-home/cryptpad -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config.installMethod | string | `"helm"` |  |
| config.logFeedback | bool | `false` |  |
| config.logLevel | string | `"info"` |  |
| config.logToStdout | bool | `true` |  |
| config.verbose | bool | `false` |  |
| env | object | See below | environment variables. See more environment variables in the [cryptpad documentation](https://cryptpad.org/docs). |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"promasu/cryptpad"` | image repository |
| image.tag | string | `""` | image tag (overrides appVersion) |
| ingress.main.enabled | bool | `false` |  |
| ingress.main.hosts[0].host | string | `"cryptpad.local"` |  |
| ingress.main.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.main.hosts[1].host | string | `"sec.cryptpad.local"` |  |
| ingress.main.hosts[1].paths[0].path | string | `"/"` |  |
| ingress.main.ingressClassName | string | `""` |  |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

All notable changes to this application Helm chart will be documented in this file but does not include changes from our common library. To read those click [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common#changelog).

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

### [1.0.0]

#### Added

- Initial version

#### Changed

- N/A

#### Removed

- N/A

[1.0.0]: #100

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
