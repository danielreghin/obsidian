---
tags:
  - tecnologia/dados
revisões: -1
criado: 
título_alternativo:
---
Um das primeiras soluções que permitiram a criação de uma solução de [[Arquitetura Data lake]] em que tipos diferentes de dados eram armazenados e sua estrutura era distribuída.
## HDFS - Hadoop Distributed File System
Tecnologia que permitiu armazenar de forma distribuída arquivos estruturados, não estruturados e semi estruturados.

Possibilitou o uso de soluções baratas de armazenamento ao usar hardwares não proprietários.
## Apache Hive
Foi o que possibilitou a camada de gerenciamento de arquivos/tabela para trazer organização através dos metadados. 
Os principais componentes são: HiveServer2, Hive Metastore e o Beeline (CLI)

![[Pasted image 20241206085701.png]]

Mesmo assim, há um suporte limitado a ACID o que pode gerar dados corrompidos e inconsistentes.

# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch03.html#cloud_object_storage