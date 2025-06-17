---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-05
título_inglês:
---
Podemos agrupar os Microserviços pelas funcionalidades que eles promover: data service, business service, translation Service e edge service.
## Data service
Microserviços que acessam algum tipo de base de dados sem fazer nenhuma regra de negócio. Veja "[[Etapas de modelagem de serviços de domínio]]".
## Business service
Microserviço que acessa uma ou mais bases de dados e que possuem regras de negócio programadas. Veja "[[Etapas de modelagem de serviços de negócio]]".
## Translation service
Microserviço que acessa funcionalidades internas ou externas ao sistemas e as traduz, reagrupa, redefine o resultado para uma linguagem que seja interpretável para o executor.
## Edge service
Microserviço que apresenta o resultado a depender do dispositivo que está chamando, mesmo que a regra de negócio dentro do mesmo seja igual. Por exemplo: o resultado de um serviço para um dispositivo móvel deve ser diferente de um resultado para o um dispositivo desktop para que a banda seja economizada. 

# Fonte
https://cursos.alura.com.br/extra/alura-mais/tipos-de-microservices-c698