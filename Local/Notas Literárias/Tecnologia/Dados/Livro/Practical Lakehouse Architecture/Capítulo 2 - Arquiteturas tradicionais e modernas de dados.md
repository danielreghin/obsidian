---
tags: 
revisões: -1
criado: ""
título_alternativo:
---
### 1. ARQUITETURAS TRADICIONAIS

Data Warehouse:

- Armazena dados estruturados em formato proprietário
- Oferece excelente performance para BI e análises
- Suporta ACID e controle granular de acesso
- Limitações: alto custo, sem suporte para dados não estruturados, vendor lock-in
- Produtos populares: Teradata, IBM Netezza, Oracle Exadata

Data Lake:

- Armazena dados estruturados, semi-estruturados e não estruturados
- Usa HDFS (Hadoop) ou armazenamento em nuvem
- Mais barato, suporta IA/ML e casos de uso em tempo real
- Limitações: performance moderada para BI, falta de governança, sem suporte ACID
- Produtos populares: Cloudera, Hortonworks

### 2. PLATAFORMAS MODERNAS EM NUVEM
Benefícios principais:
- Provisionamento sob demanda e escalabilidade
- Serviços gerenciados/serverless
- Otimização de custos (hot/cold storage, spot instances)
- Inovação rápida e menor time-to-market

### 3. ABORDAGENS MODERNAS

A) Standalone:

- Cloud Data Warehouse ou Cloud Data Lake isoladamente
- Exemplos: Amazon Redshift, Google BigQuery (DW) / Amazon S3, ADLS (Lake)
- Herdam benefícios da nuvem mas mantêm limitações arquiteturais básicas

B) Combinada (Two-tier):

- Usa Data Lake + Data Warehouse
- Benefícios:
    - Suporta todos tipos de dados e workloads
    - Melhor performance para BI (via DW)
    - Suporte para ML/AI (via Lake)
- Limitações:
    - Duplicação de dados entre camadas
    - Complexidade de sincronização
    - Desafios de governança
    - Experiência fragmentada para usuários

C) Lakehouse:

- Arquitetura unificada e aberta
- Características:
    - Storage único para todos tipos de dados
    - Suporte ACID e schema enforcement
    - Boa performance para BI e ML
    - Time travel e versionamento
    - Menor custo total (storage aberto)
    - Simplifica desenvolvimento e manutenção

### 4. EXPECTATIVAS PARA PLATAFORMAS MODERNAS

- Suporte completo:
    - Todos formatos de dados
    - Diversos casos de uso (BI, ML, streaming)
    - Workloads batch e real-time
- Características técnicas:
    - Escalável e flexível
    - Tecnologias abertas
    - Performance otimizada
    - Governança robusta
- Aspectos de negócio:
    - Custo-benefício otimizado
    - Fácil adoção pelos usuários
    - Agilidade na implementação
    - Preparada para demandas futuras

### 5. CONCLUSÕES

- Lakehouse emerge como arquitetura promissora por:
    - Combinar benefícios de DW e Data Lake
    - Eliminar duplicação e complexidade da abordagem two-tier
    - Usar tecnologias abertas reduzindo custos
    - Simplificar desenvolvimento e operação
    - Suportar diversos casos de uso em plataforma única
- Públicos que podem se beneficiar:
    - Organizações sem plataforma centralizada
    - Migrando de on-premise para nuvem
    - Usando DW ou Lake isoladamente
    - Buscando simplificar arquitetura two-tier atual

O capítulo sugere que a arquitetura Lakehouse pode se tornar a escolha padrão para plataformas modernas de dados, evidenciado pelo crescente suporte de vendors como Microsoft, AWS e Databricks.

Esta arquitetura oferece um bom equilíbrio entre funcionalidade, simplicidade e custo, endereçando as principais limitações das abordagens anteriores enquanto mantém seus benefícios chave.
# Fonte
Resumido com Claude AI