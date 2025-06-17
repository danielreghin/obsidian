---
tags:
  - tecnologia/arquitetura
revisões: 1
criado: 2024-08-01
título_inglês: Clean Architecture
---
Divisão sequencial e clara entre camadas da aplicação. Cada camada só acessa ela mesma ou camadas mais internas. Cada círculo representa diferentes camadas de software.  Eles seguem a **regra da dependência**. 

> [!NOTE] Regra da dependência
> 
Cada círculo só conhece suas camadas inferiores. Nada que foi declarado em camadas superiores (variáveis, classes, funções) podem ser usadas em camadas inferiores. O mesmo para estrutura de dados, nenhum formatos de dado de camadas externas podem ser usadas em camadas internas, principalmente se criados por algum framework.


![[Pasted image 20240716145924.png]]
Assim como em outros padrões de arquitetura procuram fornecer um método para melhor construir aplicações, permitindo uma melhor manutenção, atualização e menos dependência. 
## Camadas da Arquitetura Limpa
### Entidades
É uma classe que tem uma identidade. São regras de negócio usadas por toda a corporação. Pode ser objetos com métodos,  estrutura de dados ou funções.  
### Casos de Uso
São regras de negócio de uma aplicação. Eles orquestram as entidades para atenderem um objetivo específico. 

Se essa camada for alterada, não é esperado que se precise alterar as entidades. Também, não se espera que essa camada precise ser alterada caso um banco de dados seja alterado. Mas, é esperado que se uma regra de negócio da aplicação for alterada, essa camada deverá ser impactada.
### Controladores, Adaptadores ou Interfaces
São conversores de dados de uma forma que seja conveniente para que um caso de uso ou uma entidade o utilize corretamente. 
### Conexões Externas 
São Detalhe de Infraestrutura / Drivers e Frameworks, toda a conexão específica com o 'mundo exterior da aplicação. É composto por ferramentas e frameworks como banco de dados, frameworks web. Geralmente não se constrói muito código nessa camada, só classes que juntam as peças.  
## Como trafegar entre camadas
No canto inferior direito se vê um fluxo em que se começa pelo controlador e depois chega na camada de apresentação. Porém, não tem tem a chamada explicita entre eles. Isso é resolvido através do [[Princípio de Inversão de Dependência]]
## Dados passando pelas camadas
Aquilo que passa entre as camadas são geralmente estrutura de dados,  DTO (Data Transfer Objects), argumentos em uma chamada, um hashmap ou um objeto.  Não se deseja passar as entidades ou linhas de uma tabela. 
## Exemplo de aplicação
Em um aplicação Dart se pode utilizar a arquitetura limpa da seguinte forma:
![[Pasted image 20241007062614.png]]

O padrão [[Repository Pattern]] é aplicado nessa estrutura. Ficam claras as estruturas de :
- Apresentação
- Domínio
	- Casos de uso
	- Entidades
- Dados
	- Fontes de Dados
	- Repositórios

Existe um exemplo desse tipo de arquitetura [nesse repositório](https://github.com/md-siam/getx_clean_architecture)
## Contraponto
Existe uma outra visão de que traz muita complexidade no código. Nesse [link ](https://medium.com/@yurinovicow/flutter-what-is-clean-architecture-and-why-you-should-never-use-it-2a544fa4ed96)o autor discute a complexidade que se traz uma aplicação desse tipo. A alternativa é se ter uma arquitetura de feature first

![[Pasted image 20241007063614.png]]

# Fonte

https://medium.com/luizalabs/descomplicando-a-clean-architecture-cf4dfc4a1ac6
https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/cover.xhtml
https://cursos.alura.com.br/extra/alura-mais/clean-architecture-arquitetura-limpa-o-que-e--c204

É um [[Arquitetura de Software]] criado por Robert C. Martin em seu livro [Clean Architecture: A Craftsman’s Guide to Software](Structure_https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/cover.xhtml).

https://github.com/md-siam/getx_clean_architecture
---------------------------------------------
Fontes de estudo:
O que é o pattern repository e clean arquitecture
https://medium.com/@adityagmhatre/building-clean-architecture-in-flutter-with-repository-pattern-2af302fc22f2
https://proandroiddev.com/the-real-repository-pattern-in-android-efba8662b754
https://levelup.gitconnected.com/riverpod-inversion-of-control-dependency-injection-dependency-inversion-and-service-locator-24a1c6972ed6
E o contraponto
https://medium.com/@yurinovicow/flutter-what-is-clean-architecture-and-why-you-should-never-use-it-2a544fa4ed96
