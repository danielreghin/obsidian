---
tags:
  - tecnologia/devops
revisões: 0
criado: 2024-09-11
título_alternativo: 4 sinais chaves
---
São quatro métricas importantes para se adicionar [[Observabilidade]] no escopo do SRE e que foram propostos no livro Site Reliability Engineering do Google e que está disponível pela O'Reilly.
## Latência
Tempo de resposta de uma transação![[Pasted image 20240911174427.png]]

## Tráfego
Número de transações que ocorrem em um espaço de tempo.
![[Pasted image 20240911174518.png]]

## Erros
Taxa de erro para uma determinada transação.
![[Pasted image 20240911174457.png]]

## Saturação:
Encontra qualquer indicador que traz uma visão de que a aplicação está saturada.  Exemplo: 
Consumo de CPU, memória e espaço em disco que ultrapasse um limite ideal. Volume de uma determinada transação por minuto. Logins por segundo e outras. Depende muito da aplicação.

# Fonte
https://cursos.alura.com.br/extra/alura-mais/monitorando-aplicacoes-4-golden-signals-c1104