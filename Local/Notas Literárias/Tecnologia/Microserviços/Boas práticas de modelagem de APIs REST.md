---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-04
título_inglês:
---
## Usar recursos corretamente
Você utiliza recursos e não ações, então não usar verbos, mas sim usar substantivo.
- /getAllCars (X)    
- /cars (OK)    

Não misturar plural e singular. Para ele, o preferível é plural
- /cars ao invés de /car    
- /users ao invés de /user    

Se um endpoint que retorna todos os dados está no plural, aquele que retorna um também deve estar no plural.
## Usar sub-recursos
No controle de frotas de carros, pode se usar uma lista de motoristas de um carro
Ao invés de acessar /drivers e filtra por carro 711, se usar da seguinte forma:
- GET /cars/711/drivers/4    
- GET /cars/711/drivers (para retornar todos os motoristas)

## Idempotência
Quando se realiza a mesma operação por mais de uma vez, o resultado deve ser o mesmo.

Claro, se um carro for adicionado, o resultado modifica, mas sempre será retornado uma lista de carros. Exemplo, se usar o PUT mais de uma vez, o dado será atualizado sempre da mesma forma.
Já o POST não tem, porque, toda vez que se insere um dado, se terá um novo registro.

![[Pasted image 20240904145103.png]]

## Não ignore os cabeçalhos HTTP
O cabeçalho diz o formato de resposta, se você não sabe devolver naquele formato, responda com um erro.
- Content-type
- Accept
- Cache

Pode devolver informação de cache, por exemplo, se o dado só é atualizado de x em x tempo, você pode avisar que o cache pode ser considerado. Se uma nova informação pode ser atualizada, então não pode ser usado cache

## Use o nome (HATEOAS)
Hypermidia as the engine of the application state. É um grande assunto. A ideia é facilitar a interação com a API .Dizer o que pode fazer com um determinado recurso. Lista de operações permitidas para um determinado recurso. 

É colocar a tag 'links', com o detalhe de navegação para esse recurso. Com isso, o cliente pode saber se vai habilitar um botão de excluir o recurso, por exemplo. Existem vários formatos com que se pode utilizar.

![[Pasted image 20240904145223.png]]
## Filtro, ordenação, paginação e seleção de campos
A formatação pode ser feita como quiser. Tem várias sugestões.

- Para maior ou menor pode-se usar <=, gt    
- Para ordenação sort=name,adress    
- Filtros que quer mostrar: fields=model,id,color    
- Paginação: offset=10&limit=5    
    - Links: Retornar a primeira página, última e formas de navegar na aplicação.

![[Pasted image 20240904145331.png]]
## Versione a API
Sempre versione a API e se precisar mudar a versão o cliente vai ficar sabendo.
![[Pasted image 20240904145446.png]]
## Utilizar os status http corretamente
- Dentro de 100: Segura aí, alguma informação vem depois
- Dentro de 200: Sucesso, consegui fazer o que pediu.
- Dentro de 300: Recebi mas, você precisa tomar alguma ação, direcionar o usuário
- Dentro de 400: Você fez algo errado, tentou acessar algo que não existe, me mandou em um formato inválido. Alguma besteira você fez.
- Dentro de 500: Eu fiz alguma besteira, servidor fora, banco indisponível ou erro genérico.

![[Pasted image 20240904145536.png]]
# Fonte
https://cursos.alura.com.br/extra/alura-mais/boas-praticas-na-modelagem-de-api-s-rest-c1140
https://www.alura.com.br/artigos/rest-conceito-e-fundamentos