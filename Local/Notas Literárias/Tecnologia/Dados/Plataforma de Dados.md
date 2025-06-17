---
tags:
  - tecnologia/dados
revisões: 0
criado: 2024-12-04
título_alternativo:
---
Uma plataforma de dados é uma arquitetura de dados implementada e robusta que estabelece os princípios e componentes para trabalhar com dados em uma organização.

Uma arquitetura de dados consegue ajudar a construir uma plataforma de dados ao definir os componentes core, descrever como fluxo de dados é definido, definir os princípios que regem como será construído e operado, definindo a stack de tecnologia. 
## Componentes básicos

Os componentes básicos de uma plataforma de dados são compreendidos por:
- Origem dos dados: De onde vem os sistemas, sendo os dados, estruturados, semi ou não estruturados.  
- Ingestão: Os dados também podem vir de algumas formas diferentes como batch, stream ou near real time e a ingestão é o processo em que os dados são carregados. 
	- Batch:  Geralmente uma vez por dia, ou no começo do processo ou no final do dia.
	- NRT: Com frequência maior, com micro-batches, exemplo: a cada minuto.  Há gap de alguns minutos o que não pode ter problema a depender do SLA
	- Streaming: É a ingestão em tempo real para requisitos bem específicos. 
- Armazenamento: Local e forma de armazenamento, seja em um bucket, base de dados específicas ou recursos para esse fim na cloud.
	- Armazenamento geral: Armazenamento distribuído como o Hadoop (GCS, S3, ADLS) em que dados estruturados, não estruturados ou semi-estruturados são armazenados.
	-  Armazenamento uso específico: Datawarehouses,  Bases relacionais, bases em memória, bases em grafos
- Processamento e transformação: Todo e qualquer validação que permita que o dado esteja integro para ser usado.
	- Validação: Validações técnicas de formato de campos (formato de data), Validação de domínio de negócios, validação de schemas. 
	- Transformação: Ajuste de campos, como formato de data, complementação de dados (dados de cliente com base em um cpf), Agregação de dados (soma de transações). A transformação de dados é feita através de ETL, em que a transformação é feita antes da gravação ou ELT, em que a transformação é feita após a gravação do dado no destino. 
	- Curadoria e Disponibilização: Os dados são armazenados em um local em que os processos de negócios e requisitos sejam atendidos. Exemplo, deixar em um modelo de dados que seja simples para gerar insights em um relatório em BI


![[Pasted image 20241204143102.png]]

- Consumo e disponibilização: Componentes que permitem que os usuários possam consumir os dados. 
	- BI: Criação de relatórios e dashboards, Bancos relacionais ou em datawarehouses são bons para isso.
	-  Análise adhoc: Análise exploratória com comandos simples como python e sql.
	- APIs: Acesso controlado para desenvolvimento de aplicações
	- AI: Usar para ciclo de vida de ML com treinamento, deploy e analisando modelos. 
- Serviços comuns: Administração de dados e governança
	- Gestão de metadados: Conhecer e descobrir quais dados e seu fluxo de armazenamento existem. 
	- Governança e segurança: Qualidade do dado, Quem pode acessar, se atende a requisitos regulatórios, como o dado é compartilhado, proteção sobre remoção do ambiente. 
	- Operações: Gerenciam as operações em todo o ciclo de vida, qual é o pipeline, como e quando os processos estão schedulados, se há testes e se esses são automatizados, monitoramento da saúde de todo o ambiente. 

## Arquitetura Moderna
É esperado que em uma arquitetura moderna de dados se tenha os seguintes benefícios

![[Pasted image 20241205135430.png]]

# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch01.html#what_is_data_architecture