---
tags:
  - tecnologia/arquitetura
revisões: -1
criado: ""
título_alternativo: Processamento em Lote
---
É um quando um processamento precisa ser executado em um intervalo periódico com ou sem ativação por um operador humano. 

![[Pasted image 20241125144827.png]]

## Ferramentas de processamento Cloud
Existem algumas ferramentas de processamento em log para núvem, são elas:
- Apache Airflow
- Azkaban
- Oozie
- Agro Workflow
- Google Dataflow
- Spring Cloud Dataflow
- Camunda

Todas elas com pontos positivos e negativos para os seguintes critérios: Cloud Native, Execução (vm, servless, container), Trigger para filas, Trigger para banco de dados, trigger para diretórios, trigger para bucket, integração via api/cli, gestão de pipelines, auto-reload de pipelines, agendamento de jobs, controle de alerta de sla, linguagens com suporte, alertas de monitoramento, dashboard e ui, Opensource e suporte.

No BV se usa o Google Dataflow
## Ferramentas de processamento OnPrem
Pode-se usar a solução Uc4, acessando soluções SpringBatch.

Utiliza como apoio (Pastar do projeto DockerPara)
	Docker
	Infra as code
	metrics (Prometheus e Grafana)
	MySql para subir localmente
	RabbitMQ geração de imagem mensageria
	Configuração Lombok
	

# Fonte
https://www.zipy.ai/blog/the-big-data-big-debate-batch-processing-vs-stream-processing