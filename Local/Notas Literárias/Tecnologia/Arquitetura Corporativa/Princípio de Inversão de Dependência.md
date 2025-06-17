---
tags:
  - tecnologia/arquitetura
revisões: 0
criado: 2024-10-07
título_alternativo: DIP - Dependency Inversion Principle
---

É um princípio de arquitetura de desenvolvimento orientado a objetos cuja estratégia é a dependência de classes abstratas ou interfaces. Módulos de alto nível não devem depender de módulos de baixo nível, todos devem depender de abstrações. O [[Design Pattern - Injeção de Dependência]] é uma forma de amarrar essas abstrações nos módulos. 

Foi proposto inicialmente no *OO Design Quality Metrics (MARTIN 1994)* e definido como princípio na revista *C++ Report (MARTIN 1996)*. Faz parte dos princípios [[SOLID Principles]]. 

![[Pasted image 20241007164637.png]]

## Abstrações
Se resolve problema através de abstrações. Ou seja, as classes não devem ser acopladas a classes concretas ou que consigam ser instanciadas, elas devem ser acopladas através de interfaces ou classes abstratas. 

![[Pasted image 20240716163350.png]]
## Exemplo de código
Abaixo exemplos de código fonte com e sem o uso de Inversão de dependência

| Sem o uso                            | Com o uso                            |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20241007163311.png]] | ![[Pasted image 20241007163324.png]] |

# Fonte
https://medium.com/contexto-delimitado/o-princ%C3%ADpio-da-invers%C3%A3o-de-depend%C3%AAncia-d52987634fa9

https://levelup.gitconnected.com/riverpod-inversion-of-control-dependency-injection-dependency-inversion-and-service-locator-24a1c6972ed6