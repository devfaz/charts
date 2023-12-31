# speedtest

![Version: 3.0.1](https://img.shields.io/badge/Version-3.0.1-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

periodic speedtest and save the results to InfluxDB

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/k8s-at-home/Speedtest-for-InfluxDB-and-Grafana>
* <https://github.com/k8s-at-home/charts>

## Requirements

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | influxdb | 1.1.9 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install speedtest k8s-at-home/speedtest
```

## Installing the Chart

To install the chart with the release name `speedtest`

```console
helm install speedtest k8s-at-home/speedtest
```

## Uninstalling the Chart

To uninstall the `speedtest` deployment

```console
helm uninstall speedtest
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](../common/values.yaml) from the [common library](../common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install speedtest \
  --set env.TZ="America/New York" \
    k8s-at-home/speedtest
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install speedtest k8s-at-home/speedtest -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/charts/tree/master/charts/common/)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config.delay | int | `3600` | how many seconds to wait between checks |
| config.influxdb.database | string | `"speedtests"` | InfluxDB database |
| config.influxdb.host | string | `nil` | InfluxDB host @default - internal influxDB chart if not set |
| config.influxdb.password | string | `nil` | InfluxDB password |
| config.influxdb.port | int | `8086` | InfluxDB port |
| config.influxdb.ssl | bool | `false` | enable TLS |
| config.influxdb.username | string | `nil` | InfluxDB username |
| config.speedtest.server | string | `nil` | server to use for speedtest - leave blank to auto-pick |
| debug | bool | `false` | Display debugging output |
| image.pullPolicy | string | `"IfNotPresent"` | speedtest image pull policy |
| image.repository | string | `"atribe/speedtest-for-influxdb-and-grafana"` | speedtest image |
| image.tag | string | `"latest"` | speedtest image tag |
| influxdb.architecture | string | `"standalone"` |  |
| influxdb.authEnabled | bool | `false` |  |
| influxdb.database | string | `"speedtests"` |  |
| influxdb.enabled | bool | `true` |  |
| influxdb.persistence.enabled | bool | `false` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` | Key-value pairs to add as pod annotations |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |

## Changelog

All notable changes to this application Helm chart will be documented in this file but does not include changes from our common library. To read those click [here](https://github.com/k8s-at-home/charts/tree/master/charts/common/README.md#Changelog).

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

### [3.0.1]

#### Added

- N/A

#### Changed

- USe helm-docs

#### Removed

- N/A

[3.0.1]: #3.0.1

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)