---
tags:
  - tecnologia/dados
revisões: -1
criado: 2024-12-09
título_alternativo:
---
É gerenciada pela Tribo de Dados com o objetivo de democratizar o uso dos dados do BV para análise e tomada de decisão.
## Tribo de Dados
Composta por 5 Squads:
- Motor de Ingestão (Chameleon): Facilita a ingestão e disponibilização dos dados em um lugar único no BV.
- MLOps: Democratizar o uso de IA no BV com uma esteira simplificada de Machine Learning.
- Catálogo de Dados: Promove descoberta e compreensão dos dados para gerar ideias para o BV.
- Governança: Dar autonomia para usuários avançados poderem usar os dados do BV.
- Framework de Engenharia: Acompanhar a esteira e entrega de dados.

## Plataforma de Dados no BV           
O Datalake utiliza as soluções BigQuery (BQ) e Google Cloud Storage(GCS) tendo as seguintes camadas como parte da solução:

![[Pasted image 20241226164428.png]]
### Camadas
- RAW 
	- Armazenados no GCS
	- Dados Brutos de diversas fontes: Transações, logs, arquivos texto, banco de dados.
	- Cada ingestão é armazenada em um subdiretório (por data, por exemplo)
		srv_servidor_1/tbTabela/DT_INGESTION=2024-01-01/tbTabela.txt
		srv_servidor_1/tbTabela/DT_INGESTION=2024-01-02/tbTabela.txt
- Work
	- Armazenados no BigQuery
	- Dados brutos. Exerce função de External Table dos dados raw do GCS. Ou seja, os dados aqui referencial os dados da camada Raw. 
	- Como a camada Raw tem um arquivo para cada data de ingestão, já na camada work ele consolida todos os arquivos em uma única tabela do BigQuery. 
	- São criadas partições do Hive Partition na external table, da forma que juntam todos os arquivos em um só lugar.
- Trusted
	- Armazena os dados mais recentes.
	- Dados de-duplicados a partir da chave primária do Json. Os dados duplicados da camada work são removidos e armazenados apenas os dados únicos. 
	- Mesma tabela dos bancos origens, com o nome Trusted como prefixo. 
- Delivery
	- Dados tratados e enriquecidos prontos para serem consumidos.
	- O time  Ciência de Dados utilizam o DataBricks para gerar dados agregados e enriquecidos nessa camada. Podem ser feitos via notebooks com execução de códigos em Python ou SQL. 
	- O time de Ciência de Dados também utiliza o DataBricks para treinar modelos de IA. 
- Lab
	- Dados do GCS para uso de cientistas

### Ferramentas
- Chameleon
	- É uma ferramenta composta pelo Dataflow e Composer para tratamentos de dados.
	- Sabe ler diversas fontes e jogá-las na camada Raw
	- Tranfere também para outras camadas como Work e Trusted, deduplicando os dados.
- CDC
	- Transfere dados das bases relacionais, seja On Prem ou GCP para camadas Trusted.
- Databricks
	- Permite que cientistas de dados trabalhem com notebooks a fim de gerarem dados na cada Delivery ou também trabalhem de forma exploratória. Permite o uso de códigos Python ou SQL. 
	- Permite treinar modelos de IA.
	- Possui três ambientes (DES, DAS e PRD), sendo que o DASC é efêmero, perene para testes. 
- Kraken / MLOps
	- Leva modelos de IA ou ML para um ambiente produtivo com qualidade, governança, monitoramento e treinamento contínuo. 
	- Utiliza  Jenkins, Jira, Spinnaker para permitir que datasets na camada Trusted sejam treinados e posteriormente armazenados na camada delivery para leitura no PowerBI
- DBT (Data Build Tool)
	- Utilizado para transformar os dados de camadas Trusted para camadas delivery a fim de serem usadas para inúmeros fins.
	- Ferramenta [OpenSource](www.getdbt.com) para fazer a transformação de dados T do (ETL/ELT) para que isso se possa ser configurado de forma simples em uma ferramenta de CI/CD
	- Permite colaboração, testes, monitoramento de modelo de dados
- Dataflow 
	- Também é uma ferramenta de ETL para processamento de dados em lote ou streaming. 
	- Pode-se criar pipelines utilizando as capacidades do GCP.
-   PowerBI
	- Ferramenta para visualizar os dados disponíveis na camada delivery.
		
O sistema Chameleon apoia no envio das informações da camada Raw até a camada Trusted. 

### Ambientes de experimentação
Existem dois ambientes de experimentação no BV

- Datalab
	- É um projeto no GCP para análise e experimentação de dados produtivos, para que se tenha um espaço para pilotos e protótipos temporários de dados. 
	- Pode-se carregar dados adicionais para experimentação. 
	- Não deve ser utilizado para executar processos de forma definitiva, ou criação de relatórios. 
	- Quando não se precisa de dados produtivos para estudo, se pode utilizar um sandbox ao invés do Datalab.
- Sandbox
	- Ambientes criados de forma apartada e com produtos habilitados na gcp para fins de estudo e experimentação.
	- Possuem custos
	- São removidos após 30 dias. 
### Governança de Dados
- OpenMetadata
	- O Open Metadata foi criado para ajudar empresas e equipes a **organizar, rastrear e governar dados** de forma eficiente. Com uma arquitetura flexível, ele se integra a ferramentas populares como **Spark**, **Kafka** e **Airflow**. E o melhor: é **open source**!
	- Ferramenta de gestão de metadados para saber o detalhe de cada tabela, campo, seu dono, se está bem utilizada.
	- Utilizada para gerenciar os ativos de dados de uma organização. possui dashboards, pesquisa indexada, criação de tags.
	- Exibe amostras de dados e gera rastreabilidade de informações. 
	- Gera versões dos metadados.
	- Utilizado pela área de governança de dados
- Data Catalog
	- Ferramenta da GCP SAAS
	- Também gerencia metadados de tópicos, bancos de dados,, storage e outros

# Fontes
https://medium.com/@edilsonathaydejunior/explorando-o-open-metadata-no-projeto-lakehouse-open-source-cf92ef39e70e
