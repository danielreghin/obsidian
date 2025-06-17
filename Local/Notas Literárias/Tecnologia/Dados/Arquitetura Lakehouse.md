---
tags:
  - tecnologia/dados
  - tecnologia/arquitetura
revisões: 0
criado: 2024-12-04
título_alternativo:
---
É uma arquitetura que retira as limitações do [[Arquitetura Data lake]] e da [[Arquitetura Data warehouse]] e que foi permitida com o uso de novas tecnologias.

![[Pasted image 20241205111546.png]]

Há uma camada adicional transacional ou camada de metadados além de uma camada computacional. 
- Armazenamento: No armazenamento se utiliza arquivos de padrões abertos Apache parque, avro e orc. A
- ACID: A camada adicional transacional permite as operações ACID além de melhor controle de acesso às informações com permissão de dados mais granular. 

Veja abaixo a camada de cloud e veja [[Camada de arquivos em um lake]], [[Camada de tabelas em um lake]].
## Aprofundamento
Ao abrirmos mais a visão, temos uma quadro detalhado de soluções

![[Pasted image 20241205112438.png]]

Começando de baixo para cima. 
- Camada de armazenamento: Oferece disponibilidade, durabilidade e escalabilidade como: S3, ADSL e GCS. Possível também implementar on premisses usando HDFS
- Padrão aberto de arquivos: Existem os padrões XML, JSON e CSV, bem como os parquet, avro e orc.
- Padrão aberto de tabelas: Coração do lakehouse, trazem a capacidade de adicionar transações (ACID). Algumas tecnologias: Apache Iceberg, Apache Hudi e Delta Lake. Ver [[Ferramentas e tecnologia de dados]]
- Camada de processamento: Camada para acessar os dados e podem ser proprietárias como databricks, dremio ou snowflakes ou opensource, como Spark, presto, trino e hive

## Características
- Base única: Não há base dedicada para cada workload como a [[Arquitetura Data lake e Data warehouse unificadas]]. 
- Performance para BI: Por mais que os arquivos não sejam específicos para BI há a camada que faz a tradução para que seja performático para BI. 
- Arquitetura separada para cada resposabilidade, veja abaixo:![[Pasted image 20241205114616.png]]
- Arquitetura aberta: Não há nenhuma amarração com fornecedor e as tecnologias podem ser trocadas quando necessário.
- Suporta múltiplos tipos de workloads: Seja BI, AI, ML, exploratório. 

## Benefícios
- Arquitetura simplificada: Tudo fica em uma base única, não há ETL envolvidos. Há controle de acesso e governança é mais simples. Vários workloads são possíveis.
- Suporta dados não estruturados
- Não tem lock-in de fornecedores
- Compartilhamento de informações: Há um protocolo chamado Data Sharing Protocol que facilita o acesso direto aos dados armazenados. O consumidor e produtor de dados podem ser de fornecedores diferentes.
	![[Pasted image 20241205134644.png]]
- Escalável e eficiente em custo: Como se usa soluções em nuvem os benefícios são tirados daí.
- Não há bagunça de dados: Os dados são facilmente governados e não ficam jogados nas bases sem utilidade. Data Swamps.
- Schema: É orientado a schema e ele pode evoluir com o tempo. Portanto dados que não se enquandram em um determinado metadado não é armazenado. 
- Uma plataforma para diferentes workloads: Seja, ELT/ELT, BI, AI/ML, Real Time. 
- Time travel: Possível manter várias versões do dado baseado em alguma data. Isso é possível pela camada de transação. Ex: select * from X as of version X

## Camada Cloud Storage
A camada de armazenamento em cloud pode ser atingida com as seguintes soluções: 
	- Amazon S3
	- ADLS
	- GCS
# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch01.html