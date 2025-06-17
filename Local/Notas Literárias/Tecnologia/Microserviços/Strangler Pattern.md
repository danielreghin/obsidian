---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-05
título_alternativo: Padrão de Estrangulamento
---
É um padrão de quebra de monolitos em microserviços. Pode-se começar o processo isolando os dados ou isolando o domínio.

Pode-se começar separando o banco de dados e fazendo uma conexão entre o banco de dados novo e o antigo.
Pode-se começar separando um serviço, mesmo que ele acesse o mesmo banco de dados do monolito. 

Vai separando processo por processo, domínio por domínio até que ele vira um microserviço. 
# Fonte
https://cursos.alura.com.br/course/microsservicos-padroes-projeto/task/90630