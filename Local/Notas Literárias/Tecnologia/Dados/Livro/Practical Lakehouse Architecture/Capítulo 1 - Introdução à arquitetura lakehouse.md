---
tags:
  - tecnologia/dados
revisões: 0
criado: 2024-12-30
título_alternativo:
---
### **1. Introdução à Arquitetura Lakehouse**
- **Desafios no mundo dos dados**: Profissionais de dados, de engenheiros a cientistas de dados, precisam constantemente fazer as perguntas certas e encontrar respostas a partir dos dados. Para isso, é necessário uma plataforma robusta e bem projetada.
- **Evolução das arquiteturas**: Tradicionalmente, eram usadas arquiteturas de armazéns de dados (data warehouses) ou lagos de dados (data lakes), mas cada uma tem limitações significativas.
- **Lakehouse como solução**: A arquitetura lakehouse combina os benefícios de ambas, resolvendo problemas como custos altos, dificuldade de integração e suporte limitado a diferentes tipos de dados e workloads.
### **2. Fundamentos da Arquitetura de Dados**
- **Definição**: A arquitetura de dados é um plano estratégico que define componentes essenciais e suas interdependências, ajudando a construir plataformas robustas e escaláveis.
- **Principais componentes**:
    - **Sistemas de origem**: Fornecem dados (de sistemas internos ou externos, em formatos estruturados, semiestruturados ou não estruturados).
    - **Ingestão de dados**: Processos para carregar dados em batch, quase em tempo real ou streaming.
    - **Armazenamento**: Dados podem ser armazenados em soluções genéricas (como Amazon S3 ou Azure Data Lake) ou específicas (data warehouses, bancos em memória, etc.).
    - **Processamento e transformação**: Inclui limpeza, validação, integração e transformação de dados brutos em dados utilizáveis.
    - **Consumo e entrega**: Inclui ferramentas de BI, análises interativas, APIs para sistemas downstream e suporte a IA/ML.
    - **Serviços comuns**: Gestão de metadados, governança de dados, segurança, operações e observabilidade.
### **3. Características da Arquitetura Lakehouse**
- **Combinação de vantagens**:
    - Oferece a escalabilidade, flexibilidade e baixo custo dos data lakes.
    - Adiciona capacidades de armazéns de dados, como transações ACID e governança refinada.
- **Armazenamento único**:
    - Todos os dados residem em uma camada única, eliminando a necessidade de separar lagos de dados e armazéns de dados.
- **Arquitetura desacoplada**:
    - O armazenamento e o processamento são independentes, permitindo escalabilidade isolada.
- **Tecnologias abertas**:
    - Uso de formatos de dados abertos (Parquet, Delta Lake, etc.) e motores de processamento abertos (Spark, Presto, Trino), evitando dependência de fornecedores.
- **Suporte a diferentes tipos de dados**:
    - Dados estruturados (tabelas), semiestruturados (JSON) e não estruturados (imagens, vídeos, logs).
### **4. Benefícios da Arquitetura Lakehouse**
- **Simplicidade**:
    - Reduz complexidade, eliminando pipelines ETL adicionais para mover dados entre lagos e armazéns.
- **Flexibilidade e custo-benefício**:
    - Suporte a workloads variados (BI, IA/ML, streaming) sem necessidade de plataformas separadas.
    - Uso de armazenamento em nuvem escalável e mais barato.
- **Melhor governança**:
    - Controle centralizado de acesso, enforcement e evolução de esquemas, e recursos como "time travel" (rastrear versões anteriores dos dados).
- **Sem dependência de fornecedor**:
    - Formatos abertos permitem usar qualquer motor de processamento compatível, facilitando integração e migração.
- **Facilidade no compartilhamento de dados**:
    - Consumidores podem acessar dados diretamente na nuvem, usando permissões configuradas.
### **5. Por que o Lakehouse é Necessário?**
- **Limitações das arquiteturas tradicionais**:
    - Armazéns de dados (data warehouses) possuem ótimo desempenho para dados estruturados, mas são caros e têm dificuldade em lidar com dados semiestruturados ou não estruturados.
    - Lagos de dados (data lakes) oferecem armazenamento barato e escalável, mas carecem de governança, qualidade de dados e capacidades transacionais.
- **Avanços tecnológicos recentes**:
    - O crescimento de tecnologias open-source e a evolução da computação em nuvem abriram caminho para uma abordagem unificada.
    - O lakehouse surgiu como uma solução moderna que une o melhor dos dois mundos, eliminando a necessidade de arquiteturas em camadas (como o uso simultâneo de data lakes e data warehouses).
### **6. Características Específicas do Lakehouse**
- **Transações ACID e "time travel"**:
    - A camada transacional do lakehouse permite garantir consistência nos dados e rastrear versões antigas, algo difícil em arquiteturas tradicionais.
- **Suporte a workloads diversos**:
    - BI, ETL, IA/ML e até processamento em tempo real são suportados em uma única plataforma.
- **Tecnologias e ferramentas associadas**:
    - Usa formatos abertos (Parquet, Avro, ORC) e frameworks transacionais (Delta Lake, Apache Hudi, Apache Iceberg).
    - Motores de processamento podem ser open-source (como Spark e Presto) ou comerciais (como Snowflake e Databricks).

### **7. Benefícios Detalhados**
- **Simplificação do ecossistema de dados**:
    - Um único local para armazenar e processar todos os tipos de dados, reduzindo esforço de integração e sincronização.
- **Economia de custos**:
    - Uso de armazenamento em nuvem barato e eficiente, com políticas de arquivamento e armazenamento frio para reduzir custos.
- **Governança robusta**:
    - Centralização do controle de acesso e facilidade para organizar dados com metadados bem geridos, evitando "data swamps" (lagos de dados desorganizados).
- **Interoperabilidade**:
    - Dados podem ser compartilhados com consumidores externos sem depender de ferramentas ou softwares específicos.
- **Adaptação a mudanças nos dados**:
    - Recursos de evolução e enforcement de esquemas permitem flexibilidade sem comprometer a qualidade dos dados.
### **8. Conclusão e Futuro do Lakehouse**

- **Adaptação crescente**:
    - O lakehouse está rapidamente se tornando a escolha preferida para arquiteturas de dados modernas devido à sua flexibilidade, escalabilidade e custo-benefício.
- **Próximos passos**:
    - O capítulo enfatiza a importância de entender as limitações das arquiteturas tradicionais para valorizar as vantagens do lakehouse.
# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch01.html#references

Resumido pelo ChatGPT