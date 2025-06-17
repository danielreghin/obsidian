---
tags:
  - tecnologia/arquitetura
revisões: 0
criado: 2024-07-26
título_inglês:
---
Uma forma de representar um sistema através de diagramas hierárquicos que permitem ter níveis diferentes de abstrações a depender do público alvo. Foi criado por Simon Brown.

É formado por quadro níveis de abstração: Contexto de sistema, Containers, Componentes e Código.  Um sistema é feito de um ou mais containers (aplicações e base de dados), cada um tem um mais componentes que por sua vez são implementados por um ou mais códigos. 

![[Pasted image 20240726164836.png]]

Nem todos os níveis precisam ser criados. 

## Nível 1 - Contexto ou Sistema de Software
É o maior nível de abstração e é algo que entrega valor ao usuário, sendo ele humano ou não. Inclui o software que está desenvolvendo ou aqueles na qual você comunica. 
## Nível 2 - Container
Não é um docker, representa parte de um sistema, uma aplicação e/ou uma base de dados. Exemplos
- Aplicação Backend. Aplicação Front Web, Aplicação Client Server, Aplicativo Mobile
- Funções Servless
- Base de dados, Blob, File System
- Shell Script
## Nível 3 - Componente
São grupos de funcionalidades encapsuladas em um lugar bem definido através de uma interface.  Não é um JAR, DLL, também não é um unidade de deploy.

## Nível 4 - Código
É também uma etapa opcional que descreve como um componente é implementado no código. Pode-se usar UML ou outra notação, inclusive ser automaticamente gerada.
# Fonte
https://c4model.com/