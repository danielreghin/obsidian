---
tags:
  - tecnologia/dados
revisões: -1
criado: ""
título_alternativo:
---
Primeira arquitetura que surgiu como Big Data por volta dos anos 2000. Buscou resolver o problema de não existir uma visão centralizada quando se tinha inúmeras aplicações. O foco era criar aplicações com ETL para ao final conseguir gerar relatórios em BI. Ter dado centralizado significava ter uma Data Warehouse. Os dados eram geralmente estruturados com as suas origens bem definidas. 

Resolve o problema de múltiplas bases de sistemas diferentes na qual ao centralizar se pode tomar decisões consolidadas. Os dados podem ser organizados em [[Data mart]]. 

![[Pasted image 20241204151137.png]]
## Características
- Dados estruturados: Os dados já são estruturados da fonte
- Orientado a domínio, integrado e limpo: Os dados são validados, organizados e limpos e carregados em domínios específicos, (produtos, clientes). De o dado estiver incorreto ele é devolvido para a fonte para posterior correção. 
- Dependência de tempo, não volátil e dados históricos: Data warehouses são feitos para armazenar grandes volumes de dados com diferença temporal, para isso timestamp dos dados são armazenados, retém várias versões dos dados, apagando quando necessário. 

Possui suporte a operações ACID, sql e workloads de BI
## Vantagens
- Decisão de negócio: Como integra dados em um único local, permite insights e tomada de decisões
- Performance de BI: Tem tecnologias que ajudam a criação de relatórios como indexação, particionamento e tabelas temporárias. 
- [[ACID]]: Não precisa se preocupar com dados incompletos ao atualizar dados na base. Você não vai bagunçar os dados.
- Dados modelados: Os dados são modelados e organizados em uma entidade relacionamento ou modelagem dimensional/estrela. Há reuso de dados, evitando redundância. 
- Controle de acesso: Como os dados estão em tabelas e colunas é fácil liberar acessos específicos.
- Ponto único de verdade: Como os dados estão em um único lugar, um único local contém os dados para análise. 

## Desvantagem
- Acoplamento entre software e hardware: Para permitir um produto eficiente, se tem um acoplamento entre sistemas e hardware.
- Lock-in: Se usa formatos proprietários para armazenamento de dados e por isso, se impede de mudança de fornecedor ou uso de soluções opensource. 
- Não suporte AI/ML: Como não há dados não estruturados, como vídeos, logs, midias sociais, não se pode fazer análise preditiva. 
- Sem suporte a Stream: São construídos para carga via batch ou micro bath, portanto, dados real time não são possíveis de serem encontrados. 
- Alto custo: Ao considerar fornecedores e mão de obra. 

Algumas das desvantagens podem ser atendidas com soluções em nuvem, porém, ao considerar dados não estruturados ou stream, é necessário uma nova abordagem arquitetural.  

## Soluções em Cloud

Cloud Data Warehouse
	- Amazon Redshift 
	- Azure Synapse Analytics
	- Google BigQuery
# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch02.html