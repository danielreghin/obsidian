---
tags:
  - tecnologia/dados
revisões: -1
criado: 2024-12-05
título_alternativo:
---
Uma das evoluções e o que possibilitou a criação de um [[Arquitetura Lakehouse]] foi a existência de ferramentas que administram as tabelas em uma estrutura de [[Camada de arquivos em um lake]]. 

Essa camada adiciona a característica transacional para os arquivos de armazenamento de dados.

![[Pasted image 20241206085920.png]]

As soluções mais usadas são:
- Iceberg: Começou na netflix e usada por plataformas como Dremio, Snowflake e Tabular.
- Hudi: Criado no Uber e hoje é Opensource. É uma stack e tem mais funcionalidades do que só o formato de tabelas.
- Delta Lake: Criado na databricks, usado por Spark, PrestoDB e Trino. 

## Funcionalidades
As soluções possuem algumas funcionalidades comuns, que merecem ser explicadas

- Suporte ACID: Garantem a consistência de uma transação.
- Viagem no tempo/time travel: Armazenamento de versões antigas dos dados com possibilidade de restaurar. 
- Schema evolution: Permite modificar colunas (adicionar, remover), sem regravar os dados novamente.
- Processamento incremental: Adiciona, remove dados, com ajuste de índices.
- Particionamento e cluster: Técnica para melhorar a performance. 
- Suportar padrões de arquivos: Suportar padrões diferentes como AVRO, Parquet e ORC. 
- Validação de dados: Valida características de dados e rejeita caso não atenda a certas características, como: Null, produtos > 10, 

## Resumo de funcionalidades

| Formato    | Funcionalidades                                                                                                                                                                                                                                                                                                                                                                      |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Iceberg    | - **File format support**: Parquet, ORC, Avro<br>- **Suitable use cases**: Workloads that need changing partitions, support for multiple file formats, non-Spark compute engines<br>- **Key features**: ACID compliant, time travel, partition evolution<br>- **Limitations**: No data quality constraints<br>- **Has deep integrations with**: AWS, GCP, Dremio, Tabular, Snowflake |
| Hudi       | - **File format support**: Parquet, ORC<br>- **Suitable use cases**: Incremental processing, AWS implementations, multiple file formats<br>- **Key features**: ACID compliance, time travel, incremental processing, indexes<br>- **Limitations**: No partition evolution, no support for Avro<br>- **Has deep integrations with**: AWS, Onehouse                                    |
| Delta Lake | - **File format support**: Parquet<br>- **Suitable use cases**: Workloads using Spark engines, Azure implementations<br>- **Key features**: ACID compliance, time travel, cloning, Z-ordering, sharing<br>- **Limitations**: Works only with Parquet<br>- **Has deep integrations with**: Azure, Databricks, Microsoft Fabri                                                         |
# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch03.html#sharing_features