---
tags:
  - tecnologia/microserviço
  - tecnologia/arquitetura
revisões: 0
criado: ""
título_inglês:
---
Existem momentos em que as operações de negócio precisam manipular mais de um domínio de uma aplicação. Proveem funcionalidades de mais alto nível orquestrando múltiplos domínios. 

Como fazer isso? 
1. Identifique o processo de negócio associado.
	Inserir um aluno não é um processo. Mas matricular um aluno, sim, é um processo.
2. Identifique os domínios associados
	É necessário um aluno, o financeiro e processo de gamificação.	
3. Defina a API, API First. 
	Foque no domínio e não no detalhe do aluno (cpf ao invés de uuid).
4. Crie o serviço de negócio chamando os domínios.

# Fonte
https://cursos.alura.com.br/course/microsservicos-padroes-projeto/task/90629