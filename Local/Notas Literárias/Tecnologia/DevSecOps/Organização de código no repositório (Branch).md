---
tags:
  - tecnologia/devops
revisões: 0
criado: 2024-09-10
título_alternativo:
---
Ao se trabalhar em um repositório de código é importante que os desenvolvedores combinem a melhor estratégia de organização de como se evoluirá o código.  Deve-se buscar uma simplificação do modelo para que haja menos burocracia, simplificação e facilidade.

Quanto mais branches, mais complexidade.

Veja um exemplo de organização:
![[Pasted image 20240910135233.png]]

Existem alguns modelos conhecidos, são eles:

- Temporários (branches locais)
- Feature Branches
- Historial Branches (Master e Develop)
- Environment Branches (Staging e Production)
- Maintenance Branches (Release e Hotfix)

## Trunk-Based Development
Reduz a distância de branches ao mínimo. Assim que o código é concluído ele já vai para o trunk.
![[Pasted image 20240910150058.png]]

## Feature Branch Workflow
A cada nova funcionalidade uma branch é criada e depois integrada à Master.
![[Pasted image 20240910150138.png]]
## Github Flow
(Feature Branche + Pull Request)
Pode-se associar esse modelo ao modelo de Pull Request. É uma forma de realizar um merge colaborativo de um código e depois enviar para o Master. É uma forma de criar uma barreira artificial para se commitar no Master. É comum em projetos OpenSource em que um moderador deve aceitar ou não um código. Também uso para equipes menos seniores. 

![[Pasted image 20240910150247.png]]
## Gitlab Flow 
Se junta Feature Branch + Pull Request + ENV Branches. 
Se cria um fluxo de branches para se saber quais versões estão nos ambientes

![[Pasted image 20240910150553.png]]
## Git Flow
Se junta Feature Branch + Pull Request + Maintenance Branches + Historical Branches
Nesse modelo, se cria branches com as funcionalidades que uma vez que estejam prontas são commitadas em uma branch de release que pode ou ir para produção e quando isso acontece vão para a Master. Se houver um hotfix uma nova versão é gerada e integrada na branch de develop.

![[Pasted image 20240910150816.png]]

## Outras estratégias

Outras estratégias de organizar o código para ser implantado podem ser usadas:
- [[Feature Toggle]]
- [[Branch by Abstraction]]
# Fonte
https://cursos.alura.com.br/course/desenvolvimento-software-integracao-continua/task/69868

Dicas dadas no curso, mas não lidas:
- [https://trunkbaseddevelopment.com/](https://trunkbaseddevelopment.com/)
- [https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)
- [https://guides.github.com/introduction/flow/](https://guides.github.com/introduction/flow/)
- [https://docs.gitlab.com/ee/topics/gitlab_flow.html](https://docs.gitlab.com/ee/topics/gitlab_flow.html)
- [https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html](https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html)