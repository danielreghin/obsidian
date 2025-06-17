---
tags:
  - tecnologia/microserviço
revisões: -1
criado: ""
título_alternativo: Serviço de Ponta
---
É uma forma de dividir um [[API Gateway]] para cada tipo de cliente. Assim você pode modificar o resultado de uma API agregando dados para um cliente específico. Pode, por exemplo: no desktop retornar a transcrição e no celular não.

Para isso, se identifique o cliente, as necessidades, construir contratos específicos para o cliente, modificar os dados a serem transferidos. Ao invés de se ter um único API Gateway se tem vários Edges.
# Fonte
https://cursos.alura.com.br/course/microsservicos-padroes-projeto/task/90633