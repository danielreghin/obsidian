---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-05
título_inglês:
---
 É uma camada de infraestrutura que se adiciona às suas aplicações. Ele permite que de forma transparente se adicione capacidades como observabilidade, gestão de tráfego e segurança sem adicionar essas funcionalidades diretamente no seu código. 
 
Em português é traduzido para 'malha de serviços'.

É utilizado na comunicação de Leste a Oeste, ou seja, entre serviços de uma aplicação. É diferente de um [[API Gateway]] que se diz que controla a comunicação de Norte a Sul ou seja, entre o cliente e a sua aplicação.

Um Service Mesh cria um proxy para um serviço fazendo com que a comunicação entre serviços seja feita apenas por esse proxy.  Com isso ele adiciona funcionalidades como observabilidade, traces para entender o que está acontecendo, permitindo inclusive plugar ferramentas de debug.  

É possível monitorar a comunicação entre os serviços, promover canary release, testes a/b. Uma ferramenta de Service Mash de código aberto é o [[Istio]].

![[Pasted image 20240905091142.png]]
# Fonte
https://cursos.alura.com.br/extra/alura-mais/o-que-e-service-mesh--c1139