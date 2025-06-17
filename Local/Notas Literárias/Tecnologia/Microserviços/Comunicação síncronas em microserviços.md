---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-09
título_alternativo:
---
Em microserviços é quando se faz  uma requisição e se espera uma resposta do serviço. Pode ser feito via: 
- HTTP: Via API através do padrão Rest
- gRPC:  Protocolo criado pelo Google e transferência de binários ao invés de texto.
- Protocolos personalizado:  Através de padrões específicos ou transferências de arquivos.

Se vai chamar diretamente o serviço, vai afetar diretamente o serviço que é chamado. Ao fazer um pedido, pode-se demorar e termos problemas.
## Lidando com falhas
Para se lidar com falhas nas comunicações síncronas se têm duas estratégias.
#### Circuit breaker
É uma forma de evitar chamadas em serviços que estão com problemas. Se aguarda um tempo antes de fazer novas chamadas e emite um alerta para manutenção do serviço.

Pode-se criar um Edge Service ou um proxy que se identificar um erro no serviço subsequente aguarda um período (configurável) antes de chamar o serviço novamente. Esse edge service retorna mensagens de erro, claro. 
#### Cache
Se cria um cache para resultados não mutáveis e se retorna o resultado em cache ao invés de consultar o dado real, que seria retornado na chamada do serviço. 
# Fonte
https://cursos.alura.com.br/course/fundamentos-microsservicos-aprofundando-conceitos/task/95006