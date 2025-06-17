---
tags:
  - tecnologia/arquitetura
revisões: 0
criado: 2024-08-15
título_inglês:
---
Se pega esses conceitos e se aplica em um padrão arquitetural como o [[Arquitetura Limpa - Clean Architecture]]

São as seguintes camadas:
- Camada de Interface
	Onde o usuário ou o mundo externo se conecta. Endpoint Http. 
- Camada de Aplicação
	Ou camada de Use cases do [[Arquitetura Limpa - Clean Architecture]]
- Camada de Domínio
	Camada que contém os padrões táticos do também do [[DDD - Design de código orientado à domínio]]
- Camada de Infraestrutura
	É o que apoia o domínio. Log, envio de e-mails, conexão com o banco de dados. 

![[Pasted image 20240815083006.png]]

Foram sugeridos alguns livros: 
- Livro da capa vermelha
	https://learning.oreilly.com/library/view/implementing-domain-driven-design/9780133039900/
- Livro da capa azul
	https://learning.oreilly.com/library/view/domain-driven-design-tackling/0321125215/
# Fonte
https://cursos.alura.com.br/extra/alura-mais/domain-driven-design-ddd-o-que-e--c283