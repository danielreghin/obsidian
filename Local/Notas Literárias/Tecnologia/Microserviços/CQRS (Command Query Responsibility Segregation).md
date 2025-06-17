---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-06
título_alternativo:
---
É a técnica que podemos ter modelos diferentes para inserir uma informação e buscar o dado. Fazer isso pode gerar risco e complexidade. Pode-se ter um banco de dados para escrita e outro para leitura, por exemplo, um noSql. 

- Um modelo de escrita e outro de leitura
- O modelo de leitura pode ter informações agregadas de outros domínios
- O modelo de escrita pode ter dados automaticamente gerados
- Aumenta MUITO a complexidade.

![[Pasted image 20240906142910.png]]

Implementar o CQRS não é sobre dividir o banco de dados sempre, mas também usar alguma tecnologia de cache, por exemplo, como Redis.


# Fonte
https://cursos.alura.com.br/course/microsservicos-padroes-projeto/task/90635
https://www.youtube.com/watch?v=yd6V4w19iJU