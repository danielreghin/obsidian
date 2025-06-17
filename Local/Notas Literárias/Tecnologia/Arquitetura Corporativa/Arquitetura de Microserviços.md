---
tags:
  - tecnologia/microserviço
  - tecnologia/arquitetura
revisões: 0
criado: 2024-08-04
título_inglês:
---
É uma forma arquitetural de organização de uma aplicação através pedaços menores e acessadas através de APIs bem definidas. 
- Como vantagens podem ser construídas com tecnologias diferentes e por equipes independentes, as falhas quando acontecem estão isoladas, o deploy é mais rápido e permite uma mais escalabilidade. 
- Como desvantagens temos uma maior complexidade de infra, debug mais complexo, comunicação entre os serviços deve ser bem pensada, muitas tecnologias pode ser um problema e monitoramento é crucial e mais complexo.

![[Pasted image 20240909143918.png]]

Uma modelagem de um ou mais microserviços podem ser simples ao ponto de ser uma aplicação web respondendo via http no modelo rest ou complexo o bastante para ter um:
- [[API Gateway]]
- Tarefas agendadas em background
- Serem publicados em nuvem
- Estarem replicados em diversas máquinas
- Utilizarem de [[Mensageria]].
- Terem replicação de bancos de dados.

A complexidade de um serviço depende de seu escopo e volume de trabalho. 

![[Pasted image 20240906150153.png]]

Se utiliza do [[Princípio de Separação de Responsabilidades - SoC]].
Alguns padrões podem ser utilizados:
 - [[SAGA Patterns]]
# Fonte
https://cursos.alura.com.br/extra/alura-mais/o-que-sao-microsservicos--c699
https://www.alura.com.br/artigos/rest-conceito-e-fundamentos
https://cursos.alura.com.br/course/microsservicos-padroes-projeto/task/90636
https://learn.microsoft.com/pt-br/dotnet/architecture/cloud-native/introduce-eshoponcontainers-reference-app
https://cursos.alura.com.br/course/fundamentos-microsservicos-aprofundando-conceitos/task/95006
https://cursos.alura.com.br/course/fundamentos-microsservicos-aprofundando-conceitos/task/95007
https://cursos.alura.com.br/course/fundamentos-microsservicos-aprofundando-conceitos/task/95008
https://cursos.alura.com.br/course/fundamentos-microsservicos-aprofundando-conceitos/task/95016