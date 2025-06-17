---
tags:
  - tecnologia/dados
revisões: -1
criado: 
título_alternativo:
---
- Apache Hive: Solução sob o HDFS permite uso de dados de BI.
- Apache Hadoop: Permite o uso de arquivos distribuídos em máquinas normais para carga de dados estrutuarados, não estruturado e semi estruturados.
## Plataforma em nuvem
- Cloud Data Lake
	- Amazon S3
	- ADLS
	- GCS
- Cloud Data Warehouse
	- Amazon Redshift 
	- Azure Synapse Analytics
	- Google BigQuery
## Arquivos de armazenamentos comuns
Formatos abertos ajudam a melhorar o armazenamento além de serem utilizados em inúmeros vendors, são eles:

- Apache Parquet
- Apache Avro
- Apache ORC
## Fornecedores de soluções Datalake
- Databricks
- Snowflake
- Dremio
- Onehouse

## Formato padrão de tabelas
Coração do lakehouse ao adicionar ACID na arquitetura datalake
- Apache Iceberg: Suporta parquet, avro e orc. Adiciona timetravel, evolução de schema e suporte sql.
- Apache Hudi: Traz transações ACID, processamento incremental e evolução de schemas
- Delta Lake: Começou como um projeto do databricks. Traz uma camada de metadados, ACID, time travel, schema, logs de auditoria. É a versão open souce pela linux foundation da databricks.
- Apache HIve: Foi o precursor desse tipo de característica. Foi inicialmente criado em cima do Hadoop. Mas, ainda sim têm limitações importantes, Veja[[Hadoop]].
## Fornecedores de processamento para lakehouse
Camada de processamento: Camada para acessar os dados e podem ser proprietárias como databricks, dremio ou snowflakes ou opensource, como Spark, presto, trino e hive
