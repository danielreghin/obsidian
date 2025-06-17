---
tags:
  - tecnologia/arquitetura
revisões: 0
criado: 2024-08-16
título_inglês: Event-Drive Architecture
---
É uma arquitetura que modela a aplicação para que se comuniquem através de eventos. 

Quebra uma aplicação em partes menores e promove a comunicação entre elas através de eventos assíncronos. Promove desacoplamento, escalabilidade e principalmente responsividade entre as aplicações

Utiliza o conceito de [[Mensageria]]. Também recomendado utilizar uma [[Modelagem de Eventos]] para que ela seja implementada.
### Fluxo de transações
Ela diferente do modelo tradicional que é o de requisições. Nesse modelo, cada componente se conecta sequencialmente de forma assíncrona. Portanto, se um erro acontece em um último componente, todo o fluxo é comprometido. Veja abaixo:

![[Pasted image 20240904143331.png]]

### Fluxo de eventos
Em uma arquitetura orientada a eventos, um sistema, por exemplo, envia para um carrinho/basket que orquestra cada uma das etapas da execução. Ex: Vai para o catálogo, se tem, coloca um outro serviço para o pagamento, se pagou, coloca um outro serviço para um consolidador que devolve para o carrinho.

A complexidade aumenta porém, se ganha em [[Escalabilidade vertical]], [[Escalabilidade horizontal]] e em profundidade.-
    
Se der algum erro, o serviço de carrinho pode ser inteligente para agendar para que o processamento seja feito depois (estoque capturado e pagamento pendente para mais tarde). O sistema acaba sendo mais responsivo e cenários de falha.

O centralizador de evento é chamado de **Event Bus.** Existe uma formação de Kafka na Alura para ajudar nisso.

[[Event Sourcing]] é uma técnica que se utiliza de uma arquitetura orientada a eventos.
# Fonte
https://cursos.alura.com.br/extra/alura-mais/o-que-e-uma-arquitetura-orientada-a-eventos--c1135