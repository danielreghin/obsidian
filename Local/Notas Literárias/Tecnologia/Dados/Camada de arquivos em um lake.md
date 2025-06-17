---
tags:
  - tecnologia/dados
revisões: -1
criado: 2024-12-05
título_alternativo:
---
A depender da solução utiliza o formato de armazenamento de arquivos podem mudar, considerando Apache Parquet, ORC e Avro.
## Apache Parquet
Criado em 2013 é um arquivo utilizado em [[Plataforma de Dados]]. Utiliza uma modelagem colunar e pode armazenar dados estruturados, semi e não estruturados.

![[Pasted image 20241205153311.png]]
Consiste em um header, com informações do arquivo e os dados agrupados por colunas. Cada valor é armazenado em páginas, o dado mais granular. 
Como é colunar consegue capturar os dados de forma simples para consolidação.

É o formato utilizado no Databricks, (Delta lake) e Microsoft Fabric (OneLake)
## Apache ORC
É um formato de arquivo colunar, sucesso do formato original do Hive. Suporta ACID, possui índices e tem dados complexos como mapas, lista e estruturas. 

![[Pasted image 20241205153820.png]]

Possui três níveis de índices. 

## Apache Avro
É uma estrutura de dados OpenSource colunar, preferida de quem utiliza Hadoop. É bom para uso de grandes volumes de dados que posteriormente farão ETL.

![[Pasted image 20241205154019.png]]

## Comparação de funcionalidades

| Formato | Características                                                                                                                                                                                                                                                                                                                                                                                               |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Parquet | - **Storage type**: Columnar storage<br>- **Best suited for**: Analytical queries, Spark workloads<br>- **Compression**: Better compression than Avro, CSV files<br>- **Data scanned**: Much less, only related to column selected<br>- **Adoption**: Widely adopted, used as default file format for Spark                                                                                                   |
| ORC     | - **Storage type**: Columnar storage<br>- **Best suited for**: Analytical queries, enables ACID features in Hive<br>- **Compression**: Better compression than Avro, CSV files<br>- **Data scanned**: Much less, only related to column selected<br>- **Adoption****:** Popular among HDP users                                                                                                               |
| Avro    | - **Storage type**: Row-based storage<br>- **Best suited for**: Row-level transactions, frequent inserts/updates, write-intensive workloads<br>- **Compression**: Better compression than CSV files, not as good as Parquet and ORC<br>- **Data scanned**: Much more as compared to Parquet and ORC<br>- **Adoption:** Widely used for Kafka messages due to its compact format and schema-evolution features |
# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch03.html#cloud_object_storage