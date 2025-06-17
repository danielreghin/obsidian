---
tags:
  - tecnologia/teste
revisões: 0
criado: 2024-10-03
título_alternativo:
---
São duas abordagens de testes que têm fins diferentes
## Testes de caixa branca
Uma abordagem de testes onde se conhece no detalhe sobre uma aplicação. Se conhece os módulos, a infraestrutura e etc. Geralmente é um teste baseado na arquitetura e portanto, os testes são feitos por pessoas mais técnicas.

Algumas técnicas são:
- Testes unitários: Feitos por desenvolvedores. 
	Se testa a menor quantidade possível de testes. Pode-se usar os dubles de testes (mocks e outros). 
- Testes de integração de componentes:
	Se testa com um módulo interage com outros módulos. 
- Testes de serviços de API 
	Se um serviço funciona ao chamar para outro serviço.
- Testes de contrato
	Se valida se o contrato funciona corretamente, se a estrutura, os tipos, as contraints e headers. Se adicionar uma nova funcionalidade não irá quebrar o contrato de uma aplicação. 
	Uma ferramenta boa para esse teste: Pact, Joi e Postman Newman.
## Testes de caixa preta
São testes feitos por pessoas que não conhecem a aplicação no seu detalhe técnico. É como se a aplicação fosse uma caixa preta onde não se vê o detalhe de como ela funciona.

Alguns testes são:
- [[Testes de aceitação]]
- Testes de sistemas
- Testes de usabilidade

![[Pasted image 20241003115425.png]]

# Fonte
Curso Alura de QA
