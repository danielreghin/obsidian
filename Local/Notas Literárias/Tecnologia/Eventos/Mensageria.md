---
tags:
  - tecnologia/arquitetura
revisões: 1
criado: 2024-08-15
título_inglês:
---
É um conceito utilizado por sistemas distribuídos em que a comunicação é feito através de troca de mensagens (ou eventos), sendo que as mensagens são gerenciados por um "Message Broker" ou módulo de mensagens. Um sistema desenvolvido para utilizar desse conceito começa com o uso da [[Modelagem de Eventos]].

O conceito é implementado por um modelo de Pub/Sub ou Publicação e Assinatura. 
Alguém publica uma mensagem e quem assina recebe a mensagem.

As mensagens podem ser configuradas para: serem lidas uma única vez, serem lidas por um determinado limite de tempo e outras. 

![[Pasted image 20240815084920.png]]

Existem várias implementações: RAbitMQ, Pub/Sub da GCP,  Kafka.
Em um código, se pode por exemplo ter uma tarefa agendada em um cron, ou em algum lugar para ficar capturando dados da fila e os processando periodicamente.

No RabbitMQ existe um conceito chamado de fanout que é o ato de receber a mensagem em uma fila e depois distribuir essa mensagem para outras filas. 

# Fonte
https://cursos.alura.com.br/extra/alura-mais/o-que-e-mensageria--c1136