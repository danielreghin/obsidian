---
tags:
  - tecnologia/dados
revisões: 0
criado: 2024-12-09
título_alternativo:
---
A [[Plataforma de Dados]] no BV é composta por uma visão analítica e outra transacional. Ambas têm função e organização diferente.

A [[Plataforma Transacional no BV]] é utilizada para ser usada no escopo do desenvolvimento de aplicações, mesmo sendo bancos SQL ou NoSQL.

Já a [[Plataforma Analítica no BV]] é usada para se ter uma visão de [[Arquitetura Lakehouse]] dentro do BV para suportar:
- ML
- Análise de BI
Em GenAI, o BV está explorando o uso do VertexAI e Gemini Code Assist. 
## Divisão por camadas 
As responsabilidades foram divididas por camadas a fim de se dar responsabilidade por cada uma delas.

![[Pasted image 20241227180741.png]]

Camada Transacional
- Usada pelos sistemas para executarem as suas transações
- Geralmente se usam banco de dados SQL, porém, pode-se usar no NoSql para dados de experiência de usuário e/ou armazenamento de logs

Camada Operacional
- Base de dados batch para processamento de volumes de dados, por exemplo, valorização de parcelas de um contrato.
- Sistemas diferentes não podem acessar os seus ambientes operacionais um dos outros.

Camada Informacional
- Base de dados enriquecida (delivery) com um subproduto da camada analítica, necessária para consultas e processamentos de sistemas.
- Foi criada com base no livro, "Big Data: Princípios e melhores práticas de sistemas de dados em tempo real escaláveis.
- Tem um conceito de: Hot, Warm e Cold
	- Hot (Camada informacional)
		- Consumido por apis e armazenamento NoSql 
		- Consumo por fila e tópicos. Armazenamento em Kakfa, noSql (Memória) e Disco
		- Acesso NRT(síncrono ou Assíncrono)
	- Warm (Camada informacional)
		- Acesso D0
		- Consumo por fila e tópicos. Armazenamento em Kakfa, noSql (Memória) e Disco
	- Cold (Camada analítica)
		- Acesso D+N
		- Consumo Batch
		- Armazenamento em disco

Camada Analítica / [[Plataforma Analítica no BV]]
- Camada que contém as estruturas Raw, work, trusted e delivery, necessária para fazer a análise via PowerBi, ML, e Notebooks.



