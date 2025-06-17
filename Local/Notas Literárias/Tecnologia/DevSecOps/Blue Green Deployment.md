---
tags:
  - tecnologia/devops
revisões: 0
criado: 2024-07-17
título_inglês: Implantação Azul Verde
---
Uma forma de implantação de software em produção em que existem dois ambientes diferentes de produção mas o mais parecidos possíveis. A estratégia é chavear os dois ambientes para serem produção e teste pré-produção de forma intercalada.  Uma vez que o ambiente escolhido para testes está validado, o roteador de clientes é direcionado para esse ambiente, o outro ficará sem acesso e pronto para uma nova rodada de testes.

Exemplo:
Imaginemos que o ambiente verde é o produção no momento. Se coloca uma nova aplicação para testes no ambiente azul, uma vez que ela é validada, o roteador é chaveado para que o ambiente azul vire o de produção e o verde passará a ser o de testes. 
![[Pasted image 20240717100131.png]]

## Problemas com a estratégia
Um dos problemas é perder transações durante o chaveamento dos ambientes. Para isso, pode-se escolher algumas estratégias como manter o ambiente sem permissão de escrita por um momento e/ou fazer uma estratégia de troca de mensagens entre eles. 

# Fonte
https://martinfowler.com/bliki/BlueGreenDeployment.html
