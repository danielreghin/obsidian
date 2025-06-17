---
tags:
  - tecnologia/devops
revisões: 0
criado: 2024-09-11
título_alternativo: Observability
---
A observabilidade é a capacidade de um ativo tecnológico poder ser monitorado e com isso permitir que se tenha uma ação pró-ativa caso algo aconteça além do esperado. É possível monitorar ativos como, infraestrutura e aplicações. Cada uma com uma abordagem diferente. 

Para cada uma dessas disciplinas há um conceito específico e acrônimo:
- APM: Application Performance Monitoring
- DEM: Digital Experience Monitoring
- NPM: Network Performance Monitoring
- ITIM: IT Infrastructure monitoring
## Perspectiva de Monitoramento
O monitoramento pode ser feito em um conceito de "**black box**" ou caixa preta em que não se têm o detalhe do que se está acontecendo, como saber que deu um erro em uma aplicação. Ou pode se ter um monitoramento "white box" em que todos os detalhes são apresentados, como log de navegação, log de execução de transações. 
## Monitoramento vs Observabilidade
Os termos são comumente usados como sinônimos, mas o conceito é que monitoramento é quando se sabe o que se precisa analisar, portanto, se está monitorando um determinado ativo. Já observabilidade tem a ver com a capacidade de olhar aquilo que não se sabe. Ou seja, escutar o ambiente e deixar ele avisar caso haja algum problema. 

![[Pasted image 20241127190949.png|500]]

## Abordagem sugerida pelo Gartner
Como os ambientes são muito complexos e difíceis de serem testados em toda a sua extensão é importante ter uma abordagem diferente para tratar do tema de monitoramento.
1. Introduzir os golden signals do [[SRE - Site Reliability Engineer]] para melhorar a identificação das falhas
2. Estabelecer um SLI e SLO para quantificar o impacto e priorizar a remediação
3. Selecionar uma solução para consolidar os dados da telemetria. 
4. Incorporar elementos de outros domínios como notificação.

É possível identificar através de análises de dados históricos e telemetria de performance com AIOps.

![[Pasted image 20241127185006.png|500]] 

### Estabelecer os sinais principais (golden signals)
O SRE define quatro sinais com que se poderia identificar o que está quebrado:
- Latência: Tempo que levou para começar a executar uma determinada ação.
- Tráfego: Nível de demanda que está em jogo.
- Erros: O percentual de erros de uma determinada ação.
- Saturação: O quão cheio algo está, ou seja, existem restrições claras sobre algo (memória cheia)
Geralmente esses sinais trazem uma visão "black box" é necessário se identificar o que se quer monitorar para identificar os sinais necessários.
### Estabelecer os níveis de serviços (SLI / SLO)
Os termos SLI e SLO são parte das terminologias de [[SRE - Site Reliability Engineer]]. 
- SLI:  É a disponibilidade ou performance quantificada de algo. 
- SLO: É o objetivo de um SLI para um determinado período.

Um SLI é sempre calculado em um percentual (número de eventos com sucesso / por total de eventos).

Exemplo:
![[Pasted image 20241127191251.png|500]]

### Soluções para consolidar dados
Para todas as soluções se coleta dados em uma base para posterior extração e análise. Não há uma solução definitiva e cada tipo de solução que se quer monitorar, uma stack de armazenamento é possível. 

![[Pasted image 20241127182256.png]]

O termo telemetria é usado como forma de capturar os dados para a análise. 
- Métricas: Dados gerais como acessos, volume de dados, cpu, clientes
- Logs: Registros de execução de alguma atividade, como auditoria de transações ou registro de detalhe de erros de aplicação.
- Traces: Registros sequenciais de execução de algum processo técnico como serviço ou navegação de tela
- Eventos: Registro de qualquer evento, sequencial ou não que possa ter ocorrido.

#### Métricas
São informações que trazem alguma informação útil para análise, como: Quantidade de acessos, Quantidade de CPUs, Memória, Disco.
Geralmente vêm em formato de: Nome da métrica, valor, e quando ocorreu.

As métricas têm um ciclo de vida claro e finito.
![[Pasted image 20241127192303.png]]

#### Geração
Existem frameworks e vendedores que já instrumentam as aplicações de forma automática e coletam esses dados para serem utilizados. 
#### Ingestão
Como a agregação de métricas é difícil porque cada sistema possui uma API para exposição, por isso, existem aplicações que fazem a coleta desses dados para posterior armazenamento. 

Ver [[Ferramentas de Observabilidade]] para mais detalhes.



### Logs
Captura de informações de dentro de uma aplicação. Podem ser Tanto erros, debug, info a depender da solução. Os logs são gerados pela aplicação e armazenados em algum lugar e depois coletados com: Sidecar, logging agent instalado no Host ou com algum Shell script. Isso é feito de forma assícrona.  Pode-se enviar depois para um servidor de logs para posterior visualização. 

### Traces

## Ciclo de Vida 

O ciclo de vida de uma métrica começa pela sua geração ou captura, sua ingestão e posterior consumo. 
![[Pasted image 20241127182937.png]]

## Rastreamento distribuído
Acompanha o fluxo de informações entre diferentes sistemas ou serviços.Ter uma mesma identificação em um processo inicial e também em um serviço mais profundo no fluxo.

Algumas ferramentas OpenSource
- Permite instrumentação manual e automatizada, com um [[Sidecar Pattern]] de sua aplicação (**Jaeger**)
	https://www.jaegertracing.io/

Ter soluções que suportam o Jaeger automaticamente
- Usar um Service Mesh como o **Istio**
- Utilizar proxy (**Envoy,traefik, Kong**)

![[Pasted image 20240911173416.png]]

## APM - Monitoramento de Aplicação
Acrônimo para Application Performance Monitoring. Utiliza ferramentas  e metodologias para monitorar o desempenho de uma aplicação, monitorando e rastreando as transações. A Observabilidade de forma geral  há uma instrumentação da aplicação. 
Dentre as funcionalidades, pode-se destacar:
- Desempenho de site ou aplicação
- Dependências de aplicações ou serviços
- Traces para visibilidade de ponta a ponta
- Monitoramento se usuários em tempo real
- Associar desempenho da aplicação aos objetivos de negócio
# Fonte
https://cursos.alura.com.br/extra/alura-mais/o-que-e-observabilidade--c854
Boa parte desse material é uma tradução resumo da leitura do seguinte artigo da Gartner.
https://www.gartner.com/document/5486695?ref=solrAll&refval=441164009&