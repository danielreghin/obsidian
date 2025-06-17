---
tags:
  - tecnologia
revisões: -1
criado: 
título_alternativo:
---
 Local para classificação para estudo sistematizado da stack de tecnologia do BV.
## Observabilidade
Veja [[Observabilidade]] para maiores informações sobre conceituação. 

| Tema            | Subcatoria       | Produto                          | Descrição                                                                                                                                          |
| --------------- | ---------------- | -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Observabilidade | Servidores       | Nimsoft                          | Monitoração e métricas de serviços e servidores, com alertas Monitora: Onprem ou virtuais (vmware ou IAAS cloud)                                   |
| Observabilidade | Broadcom         | DX APM                           | Solução de apm para a broadcom                                                                                                                     |
| Observabilidade | Broadcom         | DX OI                            | Operational Intelligence, solução de insights de uma operação.                                                                                     |
| Observabilidade | Broadcom         | DX NetOps Performance Management | Monitoramento de rede, invetário, topologia, performance, configuração de ativo, arquivos de logs                                                  |
| Observabilidade | Broadcom         | DX NetOps Network Flow Analysis  | Monitoramento de rede, invetário, topologia, performance, configuração de ativo, arquivos de logs                                                  |
| Observabilidade | Broadcom         | DX NetOps Spectrum               | Monitoramento de rede, invetário, topologia, performance, configuração de ativo, arquivos de logs                                                  |
| Observabilidade | GCP              | Cloud Logging                    | Processa dados em larga escala dentro e fora da GCP.                                                                                               |
| Observabilidade | APM - Mobile     | Firebase Analytics               | Análise de mobile                                                                                                                                  |
| Observabilidade | APM - Mobile     | Firebase Crashlytics             | Consolidação de erros de mobile                                                                                                                    |
| Observabilidade | APM - Mobile     | Firebase Performance Monitoring  | Performance. monitoramento                                                                                                                         |
| Observabilidade | Servidores Cloud | Grafana                          | Dashboards com exibição das métricas que vêm do Prometheus e outras fontes.                                                                        |
| Observabilidade | Servidores Cloud | Prometheus                       | Métricas das aplicações e infraestrutura dos clusters GKE, métricas e monitoração de continers e servidores. Eventos também é monitorado por aqui. |
| Observabilidade | APM              | ELK* - Kibana                    | Da empresa elastic é exclusivo para análise de logs de aplicações para busca de problemas e análise de erros. Usado também para log de auditoria.  |
| Observabilidade | APM              | ELK - Elasticsearch              | Ler, consulta grandes dados                                                                                                                        |
| Observabilidade | APM              | ELK - Logstash                   | Extração de grande quantidade de informações                                                                                                       |
| Observabilidade | APM              | Dynatrace                        | Traces de aplicação, erros, performance. Instrumenta a aplicação para coletar dados de navegação.                                                  |
| Observabilidade | APIs             | Salt Security                    | Coleta dados de APIs em tempo real, previne ataques, acelera resposta à incidentes, "shift left" segurança, ajuda inventário de compliance.        |
* ELK = [[Elastic Stack]]

A Google tem uma solução para o GCP:
- Cloud Logging: Armazenamento de Dados e registros para posterior análise
- Cloud Monitoring: Monitoramento de servidores / conexão com prometheus
- APM (Adiciona aos acima):
	- Cloud Trace: Rastreia o caminho que uma aplicação faz 
	- Cloud Profile: Mede e analisa o desempenho de uma aplicação, identificando gargalos e fazendo otimizações. Ferramentas para captura de métricas (Prometheus) e visualização (Grafana)

## Dados 
| Tema  | Subcatoria           | Produto                     | Adotar    |
| ----- | -------------------- | --------------------------- | --------- |
| Dados | Banco Relacional     | Cloud Spanner               | Restrito  |
| Dados | Banco Relacional     | Cloud Sql - MySql           | Padrão 🟢 |
| Dados | Banco Relacional     | Cloud Sql - PostgreSql      | Restrito  |
| Dados | Banco Não Relacional | Firestore                   | Padrão 🟢 |
| Dados | Banco Não Relacional | Cloud Big Table             | Restrito  |
| Dados | Banco Não Relacional | MongoDB                     | Restrito  |
| Dados | Banco Não Relacional | Firebase Real Time Database | Restrito  |
| Dados | Banco Não Relacional | InfluxDB                    | Restrito  |
| Dados | Banco Memória        | MemoryStore                 | Padrão 🟢 |
| Dados | Banco Memória        | Redis                       | Restrito  |
| Dados |                      | Analytics                   | Padrão 🟢 |
| Dados |                      | BIgquery                    | Restrito  |
| Dados | Lakehouse            | Databricks                  | Padrão 🟢 |
| Dados |                      | Dataplex                    | Restrito  |
| Dados |                      | Datastream                  | Restrito  |
| Dados |                      | Erwin Data Modeler          | Restrito  |
| Dados |                      | Google Search Console       | Restrito  |
| Dados |                      | Mova System                 | Restrito  |
| Dados |                      | OpenMetadata                | Restrito  |
| Dados |                      | Tag Manager                 | Padrão 🟢 |
| Dados | Visualização         | Power BI                    | Padrão 🟢 |
| Dados | ETL/ELT              | DataFlow                    | Padrão 🟢 |
| Dados | GenAI                | Vertex AI                   | Padrão 🟢 |
| Dados | Armazenamento Cloud  | Cloud Storage               | Padrão 🟢 |
## Scheduler - Batch

| Tema  | Subcatoria | Produto         | Adotar    |
| ----- | ---------- | --------------- | --------- |
| Batch |            | Apache Airflow  | Restrito  |
| Batch |            | Uc4             | Padrão 🟢 |
| Batch |            | Cloud Composer  | Restrito  |
| Batch |            | Cloud Scheduler | Padrão 🟢 |