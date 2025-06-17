---
tags:
  - tecnologia/arquitetura
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-05
título_inglês:
---
Pegamos  um pequeno domínio (e não um contexto inteiro de uma aplicação) e separamos em um microserviço. Para entender o que é um domínio, pode-se utilizar o [[DDD - Design de código orientado à domínio]]. 

Um serviço de domínio é um [[Tipos de microserviços]] de Data Service.

Algumas etapas para isso: 
1. Entende qual é o domínio que estamos desenvolvendo.
	Aluno
2. Depois entendemos quais ações deverão ser disponibilizadas. 
	Matricular o aluno? ou Inserir o aluno?
	Depois como eu irei fazer isso PUT ou Patch para atualizar um aluno? 
3. Construa o contrato do serviço. Contract First.
4. Construa o serviço, pode-se ter uma serviço REST e RPC, por exemplo. 
# Fonte
https://cursos.alura.com.br/course/microsservicos-padroes-projeto/task/90628