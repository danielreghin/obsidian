---
tags:
  - tecnologia/arquitetura
  - tecnologia/design_pattern
revisões: 0
criado: 2024-10-07
título_alternativo:
---
É um design pattern de aplicação que separa a responsabilidade de construção de objetos e o seu uso. Dessa forma, se poderia mudar o tipo do objeto a ser usado, caso se use uma abstração. As dependências para que uma classe funcione são passadas de fora ao invés de serem criadas pelas próprias classes.

Os benefícios são:
- Desacoplamento
- Facilidade nos testes
- Reuso
- Flexibilidade
- Facilidade de manutenção

## Exemplos de código

| Sem uso                              | Com uso                              |
| ------------------------------------ | ------------------------------------ |
| ![[Pasted image 20241007163052.png]] | ![[Pasted image 20241007163119.png]] |
# Fonte

https://levelup.gitconnected.com/riverpod-inversion-of-control-dependency-injection-dependency-inversion-and-service-locator-24a1c6972ed6