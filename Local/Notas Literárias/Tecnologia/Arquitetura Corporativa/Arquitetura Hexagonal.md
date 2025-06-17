---
tags:
  - tecnologia/arquitetura
criado: 2024-08-01
revisões: 1
título_inglês:
---
 Isola a aplicação (domínio) com o uso de portas (interfaces) e adaptadores (camadas específicas de conexão)
 
Também chamada de Arquitetura de Portas e Adaptadores "Ports and Adapters Architecture"
Esse padrão arquitetural tem como objetivo isolar as regras de negócio da aplicação (chamados de domínio) e deixar a comunicação com o mundo exterior específica para cada tipos de conexão API, Arquivos e etc (chamados de conexões externas). O sistema fica agnóstico ao mundo externo.

Portanto, Esse tipo de arquitetura divide o sistema  sistema em grupos:
Domínios
	Representam a lógica de negócio do sistema, que é isolada e abstraída do mundo exterior
Portas
	São independentes de tecnologias, como interfaces, usadas para se conectar com o mundo exterior. Existem as de entrada, interfaces com código para se conectar com o sistema interior e de saída usadas para conectar com outras camadas no mundo interno.
Adaptadores
	Camadas de conexão com mundo exterior. Sendo os adaptadores primários aquelas na qual o mundo externo se conecta com o mundo interno (domínio) e os adaptadores secundários que são usados nas portas de saúda.
	São dependentes de tecnologia e se localizam na parte exterior do hexágono: Podem usar, por exemplo: JDBC, REST, gRPC, SQL e etc.


![[Pasted image 20240814173823.png]]

Outros exemplo: 
![[Pasted image 20240716141733.png]]

No exemplo abaixo, os casos de uso são construídos na camada de aplicação.![[Pasted image 20240716142635.png]]
![[Pasted image 20240716142824.png]]

Se utiliza do [[Princípio de Separação de Responsabilidades - SoC]].
# Fonte
- https://engsoftmoderna.info/artigos/arquitetura-hexagonal.html
- https://learning.oreilly.com/library/view/designing-hexagonal-architecture/9781837635115/B19777_01.xhtml#_idParaDest-31
- Vídeo Alura+: O que é arquitetura hexagonal
-
