---
tags: 
revisões: -1
criado: ""
título_alternativo: IaC - Infra as code
---
É uma estratégia de se automatizar a criação, manutenção e exclusão de ambientes de infraestrutura através de código.  Isso mitiga os problemas de se ter ambientes como desenvolvimento, qualidade e produção diferentes entre si. Lembrando que um ambiente é composto de ativos de máquinas como disco, memória, ativos de software como SO, bibliotecas e aplicações e também com configurações como gateways e firewalls.

A abordagem tradicional é fazer checklists através de gestão de mudanças na infraestrutura. Uma alternativa é criar virtualização completa com o **Vagrant** ou com [[Container]] com **Docker**  para dimensionar e ter ferramentas de automação. 

Abaixo uma figura de automação com o Vagrant.  (setup-vagrant.sh)
![[Pasted image 20240912085444.png]]

No final se pode armazenar toda a configuração do ambiente do gerenciador de código como github.
# Fonte
https://cursos.alura.com.br/extra/alura-mais/o-que-e-infraestrutura-como-codigo-iac--c139