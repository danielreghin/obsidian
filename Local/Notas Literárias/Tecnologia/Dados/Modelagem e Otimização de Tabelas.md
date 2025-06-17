---
tags:
  - tecnologia/dados
revisões: -1
criado: 2024-12-05
título_alternativo:
---
A fim de ser eficiente na consulta de dados de uma tabela é necessário modelar de forma a ser mais rápido o retorno dos dados.

## Modelagem
### Modelagem por linha
As tabelas são modeladas de forma que toda linha de uma tabela são armazenadas sequencialmente. Ao retornar uma campo, geralmente se tem todos os outros campos de uma tabela de forma próxima
### Modelagem colunar
Diferente da modelagem por linha, o armazenamento é feito sequencialmente coluna a coluna, sendo mais simples para capturar um grupo de colunas específicos. Modelagem geralmente feita para sistemas de BI, onde se quer um consolidado de dados.
## Outras técnicas
A fim de otimizar a consulta de informações em uma tabela é possível aplicar algumas técnicas:
- Particionar o disco para consultar o volume frequente carregado de uma tabela
- Indexar os campos para rápida descoberta
- Atualizar as estatísticas das tabelas com os ranges existentes de cada coluna. 

# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch03.html#row_versus_columnar_storage