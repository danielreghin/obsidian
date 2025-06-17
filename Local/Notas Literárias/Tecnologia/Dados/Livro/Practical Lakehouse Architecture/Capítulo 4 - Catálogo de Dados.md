---
tags:
  - tecnologia/dados
  - livro
revisões: 0
criado: 2024-12-30
título_alternativo:
---
O capítulo 4 do documento aborda o papel essencial dos catálogos de dados e da gestão de metadados na arquitetura Lakehouse, explicando conceitos fundamentais e discutindo tecnologias disponíveis para implementação. Aqui está um resumo em português:
### 1. **Conceitos Fundamentais**
- **Metadados**: São "dados sobre dados", divididos em metadados técnicos (ex.: nome de atributos, tipos de dados) e de negócios (ex.: significados e contextos comerciais dos dados).
- **Gestão de Metadados**: Inclui atividades como criação, organização, atualização e aplicação de políticas de governança e segurança.
### 2. **Catálogos de Dados**
- Um catálogo de dados é uma ferramenta que permite explorar e acessar os metadados armazenados em um repositório central (metastore). Ele facilita a busca, classificação, segurança, governança e rastreamento de linhagem de dados.
### 3. **Catálogo Unificado**
- Na arquitetura Lakehouse, um catálogo unificado centraliza os metadados de todos os ativos, desde tabelas até modelos de IA. Isso simplifica a descoberta de dados, a aplicação de controles de acesso consistentes, a governança unificada e o rastreamento completo da linhagem dos dados.
### 4. **Benefícios de um Catálogo Unificado**
- Busca unificada e eficiente.
- Controle de acesso consistente para diferentes perfis de usuários.
- Políticas de governança de dados aplicáveis a todos os ativos.
- Linhagem completa, permitindo auditorias e análises de impacto.
### 5. **Ferramentas e Opções por Provedor**
- **AWS**: Glue Data Catalog, Lake Formation, e DataZone.
- **Azure**: Synapse Analytics com Microsoft Purview.
- **Google Cloud (GCP)**: BigLake com Dataplex.
- **Databricks**: Unity Catalog, oferecendo governança centralizada e suporte a múltiplos provedores de nuvem.
### 6. **Desafios e Considerações**
- Manter metadados separados em arquiteturas combinadas (lago de dados e data warehouse) gera desafios de manutenção, descoberta, e governança.
- Catálogos modernos, como Unity Catalog e ferramentas empresariais como Collibra e Alation, ajudam a superar esses problemas ao fornecer integração centralizada.
### 7. **Considerações de Design**
- Escolher ferramentas baseadas nos requisitos técnicos e comerciais do ambiente.
- Implementar políticas de segurança e governança adequadas para dados sensíveis, como PII (informações de identificação pessoal).
# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch04.html#technical_metadata

Resumo por ChatGPT