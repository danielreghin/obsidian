---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-09
título_alternativo:
---
É quando se fez uma requisição e não se espera uma resposta. Se envia uma chamada e se tiver tudo bem você me avisa ou se tiver algum problema, você me avisa que eu venho consertar.

Os microserviços podem responder de forma assíncrona através de [[Arquitetura Orientada a Eventos]]. Isso acontece quando não há a possibilidade de responder de forma imediata algum problema que aconteça.

Pode ser usar:
- [[CQRS (Command Query Responsibility Segregation)]]
	Diz que se aceita um pedido no momento da execução da transação. Mas, não retorna se deu certo ou não. Retorna que aceita o pedido. Depois outro serviço pode ser chamado para saber a resposta. 
- [[Arquitetura Orientada a Eventos]] / [[Mensageria]]
	Aceita o pedido e envia um gerenciador de mensagens que ao concluir um pedido notifica a resposta para quem quiser ouvir. Para verificar se foi fraude, processar pagamento, registrar o log. 

Para se lidar com falhas nas comunicações síncronas se têm duas estratégias. Não faz sentido circuit breaker ou cache até porque o serviço pode demorar a responder. As tratativas abaixo já estão implementados em um Kafka, Rabbit MQ e outros. 
## Lidando com falhas
#### Retry / Nova tentativa
Se faz uma nova tentativa. O serviço simplesmente estaria fora do ar, por exemplo. 
#### Retry com back-off
Se faz uma nova tentativa aumentando gradativamente o tempo entre as tentativas até que se interrompa essas novas tentativas. 
#### Fila de mensagens mortas
Se depois de várias tentativas não se tenha o retorno se coloca a mensagem que gerou erro em uma fila de mensagens mortas. 
#### Processamento de mensagens fora de ordem
É necessário que o sistema consiga validar os pré-requisitos de um processamento de mensagem, porque as mensagens não serão recebidas e executas na ordem certa. Então, por exemplo, só se pode enviar um produto depois do pagamento e depois de ter baixado o estoque. Essa ordem deve ser validada antes da execução do código. Caso não tenha sido feito, pode ser aplicado um retry com back-off. 
#### Processamento de mensagens duplicadas (idempotência)
Deve-se tratar mensagens duplicadas também. Uma mensagem por de sido executada até um momento e depois ter dado erro. Pode, por algum motivo, ser enviada mais de uma vez. Se uma mensagem for executada mais de uma vez, o resultado sempre deve ser o mesmo.
# Fonte
https://cursos.alura.com.br/course/fundamentos-microsservicos-aprofundando-conceitos/task/95006