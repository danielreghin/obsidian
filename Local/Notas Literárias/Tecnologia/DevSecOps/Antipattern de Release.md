---
tags:
  - tecnologia/devops
revisões: 0
criado: 2024-09-10
título_alternativo:
---
Alguns antipatterns podem ajudar a dar clareza no que é importante ser feito em uma entrega contínua. 
## Gerenciamento manual de ambientes
É a ação de criar ambientes manualmente. Eles são complexos para serem criados. Por exemplo: o ambiente de produção teve uma alteração manual e que não aconteceu em um ambiente de testes. O ideal é tratar cada ambiente como código, [[Infra as code]].
## Deploy manual
Deploys descritos via texto em uma GMUD. As pessoas não tem conhecimento do ambiente e os deploys são feitos com pouca frequência. Quando há rollbacks não automatizados e frequentes.

## Deploy pouco frequentes
Deploys feitos somente ao final do ciclo quando de implantação. Os problemas só irão aparecem no final da entrega do produto. O deploy deve ser feito durante o desenvolvimento.
# Fonte
https://cursos.alura.com.br/course/entrega-continua-confiabilidade-qualidade/task/71981