---
tags:
  - tecnologia/arquitetura
revisões: -1
criado: ""
título_alternativo: Data Processing
---
Segundo Carl French, o processamento de dados é a coleta e manipulação de dados como forma de produzir um conjunto de informações significativas para um contexto operacional. 
- Entrada: Dados que o processo irá atuar
- Processamento: Dados serão processador para gera um determinado resultado
- Saída: Resultado do processamento para análise ou alguma ação.
## Funções Possíveis
Algumas funcionalidades comuns podem ser contempladas em um processamento de informações. 
- Validação: Verifica se o dado é relevante ou correto para análise ou processamento
- Ordenação: Organiza os dados em uma sequência específica ou em conjuntos ideais para a análise. 
- Sumarização: Reduz os dados em pontos chaves.
- Agregação: Combina um ou mais dados em um único conjunto.
- Análise: Interpretação dos dados coletados
- Classificação: Segregação dos dados em categorias
- Relatório: Resumo, lista do resultado do processamento

Existem processamentos [[Processamento Batch]] e [[Processamento via Stream]]
## Fluxo de Decisão
Para se processar dados, pode se ter um fluxo de decisão que direciona como um processamento é feito.
	Não
		- É fluxo contínuo: 
			- Sim: [[Processamento via Stream]]
			- Não: [[Arquitetura de Microserviços]]
	Sim
		- Têm lógica complexa
			- Sim: [[Processamento Batch]]
			- Não: ETL			
# Fonte
https://www.zipy.ai/blog/the-big-data-big-debate-batch-processing-vs-stream-processing
