---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-12
título_alternativo: Sem servidor
---
É um paradigma de se executar código sem se preocupar com os servidores, por mais que eles ainda existirem. Ele  veio para democratizar o deploy de sistemas em nuvem, simplificando temas como VPC, firewall, load balancer, múltiplas regiões e outras configurações e outras preocupações que vêm junto de uma solução. 

Alguns provedores:
- AWS (Lambda, API Gateway, SQS, DynamoDB, SNS, S3)
- Azure (Azure Functions)
- GCP (Google Functions)

As vantagens:
- Se paga pelo que se usa
- As funções podem ser criadas em linguagens diferentes
- Eventos pré-configurados para se criar arquiteturas orientadas a eventos
- Auto-escalável e altamente disponível por natureza.

As desvantagens:
- Existem limitadores de tempo de execução. Cada rotina pode durar 15 minutos.
- Lock-in do provedor.
- Difícil de debugar. Não tem como 'entrar na máquina' para debugar o código. Tem que se ter uma estratégia de logs bem claras. 
- Pode se ter configurações adicionais para controlar o ambiente como Lambda layers para adicionar bibliotecas de terceiros. 

## Custos
Os custos de Serverless são mais altos em um primeiro momento, mas se comparar com os custos adicionais e 'escondidos' dos custos de gerenciamento de servidores, eles podem se equiparar ou serem maiores.

![[Pasted image 20240912084410.png]]
# Fonte
https://cursos.alura.com.br/extra/alura-mais/o-que-e-serverless--c829