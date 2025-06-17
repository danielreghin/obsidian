---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-06
título_alternativo:
---
Temos alguns modelos de forma de dividir um banco de dados para microserviços.
## Single Service Database
Cada serviço tem um banco de dados. 
O benefício é de poder escalar cada banco de dados a depender do volume de acessos que tivermos. E inclusive o tipo de tecnologia para o tipo de problema que se quer resolver.
## Shared Service Database
Quando alguns dados precisam estar centralizados, seja por questão contratual ou outros problemas.
Mas, tratamos cada banco de dados como se fosse um banco único. Sem [[Sidecar Pattern]] no código, por exemplo.tec
# Fonte
https://cursos.alura.com.br/course/microsservicos-padroes-projeto/task/90634