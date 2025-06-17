---
tags:
  - tecnologia/devops
revisões: 0
criado: 2024-09-10
título_alternativo:
---
São duas técnicas diferentes para se juntar um código que é modificado por um grupo de pessoas terceiras. 
## Merge
O merge, no git, é quando se cria um novo commit na master com a junção do código entre master e a branch de desenvolvimento.
![[Pasted image 20240910152738.png]]

## Rebase
É a técnica de se juntas as atualizações na branch master com a branch de feature e depois disso commitar na master.
![[Pasted image 20240910152830.png]]
Porntato, as atualizações da master são atualizadas na branch da Feature e depois de ajustadas podem ir para a Master.

![[Pasted image 20240910152845.png]]
# Fonte
https://cursos.alura.com.br/course/desenvolvimento-software-integracao-continua/task/69870
