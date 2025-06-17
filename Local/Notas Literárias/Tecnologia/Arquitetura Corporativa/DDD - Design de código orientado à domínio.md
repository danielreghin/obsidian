---
tags:
  - tecnologia/arquitetura
revisões: 0
criado: 2024-08-15
título_inglês: Domain-Drive Design (DDD)
---
É um conceito de que a estrutura e o idioma do seu código devem corresponder ao domínio comercial. Divide entre Padrões estratégicos vs Padrões práticos. Também pode se estudar o [[Arquitetura em Camadas do DDD]].

Padrões estratégicos:
- Linguagem Ubíqua (onipresente)
	A linguagem dos objetos do código representam claramente o contexto da aplicação: Entidade Aluno ao invés de Cliente (para uma aula). Pode-se também usar arquivos em Inglês.
- Contextos delimitados
	Visões maiores da aplicação: local de assistir cursos, local de gamificação. Separa contextos da aplicação.
- Domínio e subdomínio
	Domínio principal da aplicação vs sub domínios. Domínio principal da aplicação. Parte acadêmica ou gamificação? Qual seria mais impactado se saísse do ar?

Padrões táticos (Blocos de Construção):
- Entidades
	É uma classe que tem uma identidade. 
- Repositórios
	Traduz entidades para camada de persistência. 
- Eventos	
- Módulos
	Módulo do aluno vs Módulo do instrutor
- Serviços
	É uma classe que representa uma ação. 

Em uma arquitetura DDD se tem o que se chamada de [[Screaming Architecture]] onde só de olhar se sabe o que está acontecendo, como abaixo:
![[Pasted image 20240909132940.png]]

# Fonte
https://cursos.alura.com.br/extra/alura-mais/domain-driven-design-ddd-o-que-e--c283