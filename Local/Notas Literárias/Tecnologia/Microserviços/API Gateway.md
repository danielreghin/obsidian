---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-05
título_inglês:
---
Esse conceito, padrão ou componente permite centralizar a chamada de seus microserviços em um único ponto, como se fosse uma fachada, um proxy ou [[Design Patterns]] Facade. Se tem um único domínio e porta para acessar os inúmeros microserviços. A mudança para outro domínio se torna simples e fácil ser replicável.

A desvantagem é que o 'portão de entrada' se torna um ponto único central de falha.  
![[Pasted image 20240905084457.png]]
Um gateway de api pode ter uma ou mais funções:
- Roteamento
	Ponto único de acesso e roteamento para o microserviço específico
- Logging
	Registro de logging das execuções
- Response Caching
	Armazenamento de caching para mais rapidez de retorno de dados não modificados.
- Autenticação
	Autenticação para validar se o acesso é permitido
- SSL
	Segurança de criptografia entre as comunicações sobre HTTP

![[Pasted image 20240905085216.png]]

Além disso, um gateway pode ter alguns comportamentos e funcionalidades: 
- Decorator
	Pode adicionar informações nos requests como dados do cliente de origem.
	Pode no retorno adicionar quanto tempo o serviço demorou a responder, qual ip, serviço
- Limitar 
	Limitar o retorno de informações ou o conteúdo trafegado na requisição.

Um contraponto ao se adicionar um único Gateway é o de utilizar [[Edge Pattern ou Edge Service]] ou Edge Services em que existe um serviço de acesso com necessidades específicas para cada um dos clientes que o acessarão.
# Fonte
https://cursos.alura.com.br/extra/alura-mais/o-que-e-um-api-gateway--c1138
https://medium.com/@jonesroberto/desing-patterns-parte-12-facade-ff66c68f5784