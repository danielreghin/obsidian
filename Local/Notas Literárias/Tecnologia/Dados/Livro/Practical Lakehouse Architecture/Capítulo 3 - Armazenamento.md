---
tags:
  - tecnologia/dados
  - livro
revisões: -1
criado: ""
título_alternativo:
---
O capítulo 3 do documento aborda a camada de armazenamento em arquiteturas de data lakehouse, destacando seu papel essencial no armazenamento eficiente de dados e na melhoria do desempenho de consultas. Segue um resumo dos principais tópicos:
### 1. **Conceitos-Chave do Armazenamento no Lakehouse**
- **Armazenamento baseado em linhas versus colunas**: Dados podem ser armazenados em formato row-based (mais útil para consultas completas) ou colunar (mais eficiente para consultas analíticas que acessam apenas algumas colunas).
- **Otimização baseada em armazenamento**: Técnicas como particionamento, indexação e estatísticas de colunas reduzem o volume de dados escaneados, acelerando as consultas.
### 2. **Componentes do Armazenamento no Lakehouse**
- **Armazenamento em nuvem**: Usado para grandes volumes de dados. Exemplos incluem Amazon S3, ADLS, e GCS.
- **Formatos de arquivo**: Incluem Parquet, ORC e Avro, cada um com características específicas para compressão, consulta e suporte a processamento distribuído.
- **Formatos de tabela**: Tecnologias como Iceberg, Hudi e Delta Lake adicionam suporte a transações ACID, versionamento de dados (time travel), e schema evolution.

### 3. **Comparação de Formatos de Arquivo**
- **Parquet**: Ideal para consultas analíticas, com compressão superior e menor volume de dados escaneados.
- **ORC**: Também columnar, suporta ACID e é integrado ao Hive.
- **Avro**: Baseado em linhas, ótimo para workloads de ETL com mudanças frequentes no esquema.

### 4. **Comparação de Formatos de Tabela**
- **Iceberg**: Suporta múltiplos formatos de arquivo (Parquet, ORC, Avro), evoluções de partição e consultas em engines diversas.
- **Hudi**: Focado em processamento incremental, com forte integração no AWS.
- **Delta Lake**: Integrado ao Spark e Azure, oferece recursos como Z-ordering, compartilhamento de dados e validação de qualidade.
### 5. **Considerações de Design**
- Decisões devem considerar suporte no ecossistema, engines de computação compatíveis e a evolução futura dos formatos.
- Iceberg é ideal para cenários com múltiplos formatos de arquivo e necessidades de flexibilidade.
- Hudi é excelente para cenários AWS e processamento incremental.
- Delta Lake é amplamente adotado para workloads Spark em Azure.

O capítulo conclui destacando que nenhum formato ou tecnologia oferece todas as melhores funcionalidades, sendo necessário escolher com base nos casos de uso e realizar provas de conceito para validar as decisões.
# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch03.html#row_versus_columnar_storage

Resumo ChatGPT