---
tags:
  - tecnologia/linguagem
revisões: 0
criado: 2024-03-27
título_inglês: 
ano_publicação: 
autor: yaml.org
qtd_páginas: 
ISBN:
---
# Síntese

Surgiu com o objetivo de simplificar a linguagem XML. A primeira biblioteca criada foi para Pearl em 2001. A versão 1.1 saiu em 2005 na mesma época que o JSON se tornou conhecido. JSON era quase um subconjunto completo de YAML (tanto sintaticamente quanto semanticamente). A versão 1.2 saiu em 2009 fazendo o YAML ser um superconjunto do JSON. Versão 1.2.2 saiu em 2021.

Os arquivos possuem as seguintes extensões: .yml ou .yaml

As informações dentro dele são case sensitive.

### Base

A indentação é usada com espaços e não com tabulações. Pares e valores, são descritos com :.

[https://www.tutorialspoint.com/yaml/yaml_indentation_and_separation.htm](https://www.tutorialspoint.com/yaml/yaml_indentation_and_separation.htm)

### Comentários

Cerquilha é o caractere para comentário

`# Aqui temos um comentário`

### Início e fim

O documento tem um início e um fim com --- para início e … para fim.

`#Doc 1`  
`--- # Start`  
`... # End`

### Tipos de dados

Pode-se ter textos, nulos, booleanos, inteiros ou pontos flutuantes.

Os textos podem ter aspas duplas “ “, simples ‘ ‘ ou não terem nada

`#Doc 1`  
`--- # Start`  
`tipo: "Teste" # ou 'Teste' ou teste`  
`teste: true`  
`numero: 1`  
`nulo: null`  
`... # End`

Para data, o padrão a ser seguido é ISO 8601. (yyyy-mm- ddThh:mm:ss.ffffff)

`#Doc 2`  
`---`  
`pessoa:`  
`nome: &nome Fulano`  
`sobrenome: Cicrano`  
`idade: 45`  
`data_nascimento: 1974-05-13 09:25:55`  
`"estado civil": null`  
`masculino: true`

Outros

null: ~
true: y
false: n

As listas podem ser apresentadas com colchetes [] Pode-se também não usar colchetes e listar os membros com um traço -

--- # Favorite movies
 - Casablanca
 - North by Northwest
 - The Man Who Wasn't There

--- # Shopping list
   [milk, groceries, eggs, juice, fruits]

- {name: John Smith, age: 33}
- name: Mary Smith
  age: 27

As listas podem começar sem uma chave valor, da seguinte forma:

-
 - Cat
 - Dog
 - Goldfish
-
 - Python
 - Lion
 - Tiger

### Collections

Se usa chaves {} e teremos grupo de chave e valor.

Escalares para escalares

hr: 87
avg: 0.298
rbi: 149

Escalares para listas

European:
- Boston Red Sox
- Detroit Tigers
- New York Yankees

national:
- New York Mets
- Chicago Cubs
- Atlanta Braves

LIsta de chave-valor

-
name: Mark Joseph
hr: 87
avg: 0.278
-
name: James Stephen
hr: 63
avg: 0.288

### Indentação

É necessário indentar de forma a todos os itens abaixo de uma lista ou objeto começarem um valor a frente do pai da lista.

--- !clarkevans.com/^invoice
invoice: 34843
date   : 2001-01-23
bill-to: &id001
   given  : Chris
   family : Dumars
   address:
      lines: |
            458 Walkman Dr.
            Suite #292
      city    : Royal Oak
      state   : MI
      postal  : 48046
ship-to: *id001
product:
    - sku         : BL394D
      quantity    : 4
      description : Basketball
      price       : 450.00
    - sku         : BL4438H
      quantity    : 1
      description : Super Hoop
      price       : 2392.00
tax  : 251.42
total: 4443.52
comments: >
    Late afternoon is best.
    Backup contact is Nancy
    Billsmer @ 338-4338.

### Reuso de valores

É possível utilizar uma variavel para reutilizar valores, para reutilizar guardar valores utilizar o &seguido pelo nome da variavel. Para reusar so colocar *seguido pelo nome da vari’vel

defaults: &defaults
   adapter:  postgres
   host:     localhost

development:
   database: myapp_development
   <<: *defaults

test:
   database: myapp_test
   <<: *defaults

### Caracteres de apoio

Se quiser que várias linhas sejam interpretadas como uma só, basta colocar > em frente.

>
Sammy Sosa completed another
fine season with great stats.
63 Home Runs
0.288 Batting Average
What a year!

O uso do pipe | mantém a estrutura de novas linhas caso seja assim que tenha sido criado.

|**Sr.No.**|**Character & Functionality**|
|---|---|
|1|**_**<br><br>It denotes a block sequence entry|
|2|**?**<br><br>It denotes a mapping key|
|3|**:**<br><br>It denotes a mapping value|
|4|**,**<br><br>It denotes flow collection entry|
|5|**[**<br><br>It starts a flow sequence|
|6|**]**<br><br>It ends a flow sequence|
|7|**{**<br><br>It starts a flow mapping|
|8|**}**<br><br>It ends a flow mapping|
|9|**#**<br><br>It denotes the comments|
|10|**&**<br><br>It denotes node’s anchor property|
|11|*****<br><br>It denotes alias node|
|12|**!**<br><br>It denotes node’s tag|
|13|**\|**<br><br>It denotes a literal block scalar|
|14|**>**<br><br>It denotes a folded block scalar|
|15|**`**<br><br>Single quote surrounds a quoted flow scalar|
|16|**"**<br><br>Double quote surrounds double quoted flow scalar|
|17|**%**<br><br>It denotes the directive used|

# Fonte
https://yaml.org/spec/1.2.2/#chapter-1-introduction-to-yaml