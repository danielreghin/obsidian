---
tags:
  - tecnologia/devops
revisões: -1
criado: 2024-11-27
título_alternativo:
---
Usando como base o estudo de [[Observabilidade]], temos algumas ferramentas que podem ajudar na sua implementação.

## Coleta e Ingestão

É o ato de coletar dados de diversas fontes e colocar em uma base de dados.

![[Pasted image 20241127193702.png]]
### Coleta
#### Prometheus
É uma aplicação OpenSource que tem a capacidade de coletar, armazenar, analisar e apresentar métricas. 
Funciona bem onde métricas estão disponíveis via API rest, como clouds publicas. 
https://prometheus.io/
#### OpenMetrics
É uma abstração de como o Prometheus expõe métricas e é uma potencial solução de padronização. 
https://openmetrics.io/
#### Telegraf
É Opensource e é um agente para coleta de métricas que podem ser armazenadas posteriormente em uma base "time series", Apache IoTDB, por exemplo.  É um serviço parecido como collectd
https://www.influxdata.com/time-series-platform/telegraf/
#### collectd
É um daemon de coleta de dados e suporta diversos sistemas, principalmente em sistemas linux. 
https://www.collectd.org/
#### OpenTelemetry
Está se tornando um protocolo comum para coleta de dados de forma padronizada. OpenTelemetry, also known as OTel, is a vendor-neutral open source [Observability](https://opentelemetry.io/docs/concepts/observability-primer/#what-is-observability) framework for instrumenting, generating, collecting, and exporting telemetry data such as [traces](https://opentelemetry.io/docs/concepts/signals/traces/), [metrics](https://opentelemetry.io/docs/concepts/signals/metrics/), and [logs](https://opentelemetry.io/docs/concepts/signals/logs/).
https://opentelemetry.io/

### Ingestão
Se a solução não fizer a ingestão, uma base de dados de série temporal, pode ser usada. 
Algumas: 

| Vendedor                                                                                                                                | Comentário                                                                                                      |
| --------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Amazon Web Services (AWS):  [Amazon Timestream](https://aws.amazon.com/timestream/)                                                     | AWS-based time-series database. Became available in 2018. A commercial, cloud-hosted product.                   |
| [Grafana Mimir](https://grafana.com/oss/mimir/)                                                                                         | Open-source, multitenant, scalable, Prometheus-based store. Available commercially in Grafana Labs products.    |
| InfluxData:  [InfluxDB](https://www.influxdata.com/products/influxdb-overview/)                                                         | Open-source, modern time-series platform (TICK Stack) with commercial and SaaS editions.                        |
| [M3DB](https://www.m3db.io/)                                                                                                            | Open-source option, originally developed at Uber. Made into a SaaS product by Chronosphere.                     |
| [OpenTSDB](http://opentsdb.net/)                                                                                                        | Open-source option from StumbleUpon. Uses Apache HBase for storage.                                             |
| [Prometheus](https://prometheus.io/)                                                                                                    | Open-source option from SoundCloud.                                                                             |
| [Timescale Analytics](https://www.timescale.com/blog/time-series-analytics-for-postgresql-introducing-the-timescale-analytics-project/) | Open-source extension to PostgreSQL that supports time-series data. Commercial and SaaS editions are available. |

Existem também ferramentas SaaS de armazenamento e análise. 

| Vendedor                                                                           | Comentário                                                                                                                                                                             |
| ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Broadcom:  [VMware Tanzu (Wavefront)](https://www.wavefront.com/)                  | There are a variety of ways to get data into VMware Tanzu (Wavefront), including collectd, APM integration, cloud provider integration and Telegraf; also supports the collector model |
| [Datadog](https://www.datadoghq.com/)                                              | Broad monitoring capabilities beyond metrics management; has a custom agent                                                                                                            |
| [Dynatrace](https://www.dynatrace.com/)                                            | A commercial observability platform powered by AI, with an available OTel collector and exporters, in addition to proprietary agents.                                                  |
| InfluxData:  [InfluxDB Cloud](https://www.influxdata.com/products/influxdb-cloud/) | Time-series database as a service (DBaaS) platform hosted in multiple cloud platforms                                                                                                  |
| [LogicMonitor](https://www.logicmonitor.com/)                                      | Collector software that can pull from multiple nodes and forward to the platform                                                                                                       |
| [OpsRamp](https://www.opsramp.com/)                                                | Advanced analytics and increasingly broad capabilities                                                                                                                                 |
| [Splunk](https://www.splunk.com/)                                                  | Streaming analytics and good support for cloud-native platforms                                                                                                                        |
| [Sysdig](https://sysdig.com/)                                                      | Prometheus-compatible, eBPF-based container monitoring and security solution                                                                                                           |
| [Zenoss](https://www.zenoss.com/)                                                  | Analytics-centric monitoring with broad platform coverage                                                                                                                              |
## Métricas

- Visualização de métricas (**Grafana**)
	https://grafana.com/

![[Pasted image 20240911173432.png]]
Tela do grafana

## Logs

Algumas ferramentas de log que conseguem gerar visualizações inclusivo com as informações de rastreamento.
- https://www.elastic.co/pt/kibana
- https://graylog.org/

![[Pasted image 20240911173908.png]]
Tela do Kibana

## Ferramentas proprietárias
Algumas ferramentas proprietárias que fazem o que as opensource fazem são:
- Elastic Stack
- New Relic
- Dynatrace
- Netdata