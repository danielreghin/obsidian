---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-11
título_alternativo:
---
Uma solução para evitar que se tenha necessidade de criação de diversas máquinas para implantação de soluções de software.  Além disso, evita ter máquinas diferentes entre diversos ambientes. A gestão do sistema operacional não é mais um problema. Containers são mais leves, sem custo de vários Sistemas Operacionais e é mais rápido para provisionar. 

Antes de container, se precisava se ter uma máquina para cada solução
![[Pasted image 20240911175557.png]]

Depois, se criaram máquinas virtuais em que se compartilhava uma máquina com diversas 'máquinas virtuais' que tem o OS e as aplicações. Já em containers, se tem um gestor de containers que simula um sistema operacional separado. Ou seja, a aplicação 1, 2 e 3 entendem que estão rodando em máquinas independentes.

![[Pasted image 20240911175925.png]]


Os gestores de containers mais utilizados são: 
- Kubernetes
- Docker Swarm
- Red Hat OpenShift
- Amazon ECS (Elastic Container Service)
# Fonte
https://cursos.alura.com.br/extra/alura-mais/o-que-sao-containers--c1141