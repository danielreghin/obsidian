---
tags:
  - tecnologia/dados
revisões: -1
criado: 2024-12-05
título_alternativo:
---
É uma arquitetura que utiliza o melhor dos mundos de [[Arquitetura Data lake]] e [[Arquitetura Data warehouse]], mesmo assim ainda não é uma [[Arquitetura Lakehouse]]. Ao utilizar soluções em nuvem os benefícios ainda são potencializados.


![[Pasted image 20241205110005.png]]

## Benefícios
- Vantagem de uso de cloud: Ao usar nuvem há os benefícios naturais de cloud como provisionamento, auto escalonamento e flexibilidades de preços e recursos.
- Formato de dados: Se tem os dados crus no lake e curados no warehouse para os fins específicos conforme gráfico. Além de ter acesso aos dados estruturados, semi e não estruturados.
- Tipos de trabalhos: Se permite o uso de AI, bem como BI nas suas bases específicas.
- Atende diversos públicos: Atende diversos públicos dado a flexibilidade.

## Limitações
- Duplicidade de dados: Os dados do lake são duplicados para o warehouse e muitas vezes é necessário copiar do warehouse para o lake após a transformação em casos de trabalhos de ML.
- Confusão com metadados: Os metadados das duas plataformas são diferentes e geram confusão um com outro. 
- Concessão de acesso: Há dificuldade de manusear as permissões nas duas plataformas.
- Experiência ruim: Você não sabe onde os dados estão, se no warehouse ou no lake e há confusão e dificuldade de agregar os dados dos dois mundos.
# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch02.html#standalone_approach