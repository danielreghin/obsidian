---
tags:
  - tecnologia/microserviço
revisões: 0
criado: ""
título_inglês: 
ano_publicação: 
autor: OpenApi
qtd_páginas: 
ISBN:
---
## 1 - Introdução

A _OpenAPI Specification_ ou OAS, descreve como acessar APIs remotas via HTTP e HTTPS. A descrição dessas APIs é chamado de _OpenAPI Description_ ou OSD.

APIs são métodos, com parâmetros e valores de retorno que são chamadas para que dois aplicativos se comuniquem. Elas podem ser locais ou seja funcionam na mesma máquina ou remotas. O foco da especificação é em APIs remotas que funcionam via uma rede.

- Provider: Quem oferece a API
- Consumer: Quem pode utilizar a API

Uma API não necessariamente precisa demonstrar como um certo serviço foi construído e portanto, seu _provider_ pode mudá-lo sempre que quiser.

Uma API também pode ser chamado de um **Contrato.** Esse O provedor dessa API promete não alterar o contrato dessa API a fim de não quebrar os serviços futuros.

### Problema

Os problemas de não se usar uma boa documentação de APIs é

- Interpretação incorreta de como usar.
- Documentação não existente ou incompleta
- Desatualizada
- Linguagem que o leitor não compreende

Tempo é desperdiçado para compreender como uma API pode ser chamada.

### Solução

Gerar uma documentação que pode ser lida por uma máquina e por uma pessoa. Uma arquivo de descrição de API ou um contrato deve ser o mais completo possível. Importante que o contrato não seja ambíguo.

Ao gerar uma documentação padronizada é possível automatizar o processamento e também é possível gerar um documento automaticamente que um humano possa compreender.

Em seguida é possível também gerar código padronizado, em diversas linguagens de programação, para que um a API seja invocada.

A descrição da API também permite incluir exemplos e testes simulados de invocações da API.

## A especificação OpenAPI

Ela foi baseada na especificação Swagger 2.0 doado pela SmartBear em 2015. Atualmente é mantida pela OpenAPI initiative (OAI), um consórcio de especialistas da indústria sobre uma governança aberta e sob o chapéu da fundação Linux. As decisões são públicas e todos podem propor mudanças.

A abertura provoca a criação de diversas ferramentas (OpenAPI tools).

Não é a expectativa da especificação descrever qualquer API, mas principalmente as com protocolo HTTP, ou protocolos parecidos com HTTP como CoAP ou WebSockets.

### Um pouco de história

Na computação nascente a única linguagem existe era o Assembly. E um combinado deveria ser feito para que um aplicativo chamasse o outro. Esse combinado eram espaços de memória com determinados parâmetros e respostas.

Evoluindo as linguagens de programação, métodos e interfaces foram construídos e o contrato de execução poderia ser validado em tempo de compilação de código.

No advento da internet o mesmo problema do Assembly emergiu nas chamadas remotas de APIs. Por isso, a especificação OpenAPI e equivalentes precisaram aparecer para dar luz a esse problema.

## 2 - Estrutura de uma OpenAPI Description ou OAD

Uma OAD ou OpenAPI description decreve uma API via HTTP-like.

Uma descrição de OpenAPI pode ser escrita em um ou mais documentos JSON ou YAML. Referências entre arquivos são criadas para conectá-las e fazer parte do todo.

A leitura do arquivo começa com um objeto OpenAPI que está em um documento que geralmente é chamado de

`openapi.json ou openapi.yaml`

### Arquivos

Representam números, textos, booleanos, valores nulos, listas ou objetos. A lista é um grupo de valores ordenados de vários tipos. Um objeto representado por um mapa é uma coleção de pares, chaves e valores com chave unívocas e valores que podem ser outros tipos, incluindo objetos e listas.

JSON não suporta comentários. Vírgulas são usadas para separar campos. Chaves {} são usados ao redor de objetos, aspas duplas “ “ ao redor de textos e colchetes [] ao redor de listas.

**JSON**
{
  "anObject": {
    "aNumber": 42,
    "aString": "This is a string",
    "aBoolean": true,
    "nothing": null,
    "arrayOfNumbers": [
      1,
      2,
      3
    ]
  }
}

YAML suporta comentários com cerquilha. Hífen - são usados antes de itens de uma lista. A indentação é fortemente usada. É geralmente preferido usá-lo contra o YAML por ser menor.

# Anything after a hash sign is a comment
anObject:
  aNumber: 42
  aString: This is a string
  aBoolean: true
  nothing: null
  arrayOfNumbers:
    - 1
    - 2
    - 3

Os arquivos são intercambiáveis, desde que usado YAML 1.2

Como YAML é um superconjunto do JSON as duas sintaxes podem ser misturadas.

anObject:
  aString: This is a string
  arrayOfNumbers: [ 1, 2, 3 ] # Abbreviated array representation

Todos os valores, tanto de um arquivo quanto de outro, são _case sensitives_

### Estrutura Básica

O OpenAPI Map ([https://openapi-map.apihandyman.io/](https://openapi-map.apihandyman.io/)) oferece um local fácil para se encontrar os atributos obrigatórios ou não. Abaixo os principais atributos obrigatórios

- openapi (string): Indica a versão do OAS que esse OAD está usado. ex: "3.1.0"
- info (objeto Info): Informação geral sobre a API, descrição, autore etc
    
    - title(tring): Nome da API. ex: "GitHub REST API"
    - version(string): Indica a versão da API
- paths (objeto Path): Contém todos os endpoints da API, parâmetros e respostas possívels.

openapi: 3.1.0
info:
  title: A minimal OpenAPI Description
  version: 0.0.1
paths: {} # No endpoints defined

Exemplo de um arquivo de API.

## 0 - Dicas

Acessar o mapa com todos os atributos e parâmetros
[https://openapi-map.apihandyman.io/](https://openapi-map.apihandyman.io/)

## 3 - Endpoints das APIs

Os endpoints de uma  API podem ser chamados de operações ou rotas (operations, routes), são chamados de caminhos no OAS (paths).

Acima uma estrutura básica de um path. É possível definir atributos padrões no objeto _component_ da raiz.

Um path começa sempre com uma barra /, dado que são concatenadas com a URL.

- path (path item object) lista de operações que podem ser executadas por esse path
    
    - operation (operation object) detalhe da operação.

paths:
  /board:
    get:
      # atributos
    put:
      # atributos

### Operações

O objeto operações (_operations object_) descreve o objetivo da operação.

paths:
  /board:
    get:
      summary: Get the whole board
      description: Retrieves the current state of the board and the winner.
      parameters:
        ...
      responses:
        ...

### Respostas

O objeto de respostas (_responses object_) descreve todos os códigos possíveis de retorno. O objeto respostas contém n objetos resposta (_response object)._

Ao mínimo uma resposta precisa ser declarada. É recomendado que seja dado uma reposta de sucesso, como 200. Wildcards podem ser usados como 1xx,2xx e etc.

paths:
  /board:
    get:
      responses:
        "200":
          ...
        "404":
          ...

**Resposta**

Contém uma descrição e conteúdo da resposta. O atributo _content_ é o mais importante e será descrito em outro tópico.

paths:
  /board:
    get:
      responses:
        "200":
          description: Everything went fine.
          content:
            ...

## 9 - Segurança das APIs

A definição de segurança é feito através do objeto _Security Scheme_ na qual é possível definir padrões de seguranças globais ou por operação. Os objetos aqui criados são referenciados por um objeto _Security Requirement_. São 5 os mecanismos de segurança existentes hoje e são definidos pelo atributo _type_:

- API Keys
- HTTP Authentication
- Mutual TLS
- OAuth 2.0
- OpenID Connect

### API Keys

Equivalente a uma senha que o consumidor e o provedor da API conhecem. O provedor pode usar o header http chamado api-key para enviar a chave. Daí, o Security Scheme pode ser definido para esse cenário:

components:
  securitySchemes:
    defaultApiKey:
      description: API key provided in console
      type: apiKey
      name: api-key
      in: header

O provedor da API pode definir esse Scheme para ser usado globalmente ou por operação.

openapi: 3.1.0
info:
  title: Tic Tac Toe
  description: |
    This API allows writing down marks on a Tic Tac Toe board
    and requesting the state of the board or of individual squares.
  version: 1.0.0
security:
  defaultApiKey: []
paths:
  /board:
    get:
      security:
        defaultApiKey: []

O array acima não populado é usado para OAuth Flow e OpenID Connect, para os outros é deixado vazio.

### Autenticação HTTP

Suporta a autenticação definida na RFC7235 que implementa um header _Authorization. O scheme_ utilizado e o parâmetro são enviados no formato: `Authorization: Basic b3BlbmFwaTppc2dyZWF0`

O exemplo abaixo usa Basic e Bearer token, nesse último se inclui um parâmetro adicional para informar o formato do Token, no cenário JWT.

components:
  securitySchemes:
    basicHttpAuthentication:
      description: Basic HTTP Authentication
      type: http
      scheme: Basic
    bearerHttpAuthentication:
      description: Bearer token using a JWT
      type: http
      scheme: Bearer
      bearerFormat: JWT

O onboarding e a troca de chaves está fora do escopo do OpenAPI.

### Mutual TLS

Bastante utilizado em serviços financeiros dado a sua capacidade de segurança. Para se definir é simples

type: mutualTLS

Estabelecer a infraestrutura de chave privada usado e troca de certificado é fora do escopo da OpenAPI

### OAuth 2.0

É bastante popular dado que as credenciais são repassadas através de um terceiro na qual é delegado a responsabilidade. É descrito usando o objeto _OAuth Flows_. É mais complexo porque define quais recursos devem ser acessados.

components:
  securitySchemes:
    oauth2Profiles:
      type: oauth2
      flows:
        clientCredentials:
          tokenUrl: https://learn.openapis.org/oauth/2.0/token
          scopes:
            board:read: Read the board
            board:write: Write to the board
        authorizationCode:
          authorizationUrl: https://learn.openapis.org/oauth/2.0/auth
          tokenUrl: https://learn.openapis.org/oauth/2.0/token
          scopes:
            board:read: Read the board
            board:write: Write to the board

Podem também ser definidos globalmente ou localmente

openapi: 3.1.0
info:
  title: Tic Tac Toe
  description: |
    This API allows writing down marks on a Tic Tac Toe board
    and requesting the state of the board or of individual squares.
  version: 1.0.0
security:
  oauth2Profiles:
    - board:read
    - board:write
paths:
  /board:
    get:
      security:
        oauth2Profiles: []

Se for necessário segregar os acessos é necessário criar um novo _Security Scheme_.

omponents:
  securitySchemes:
    **app2AppOauth**:
      type: oauth2
      flows:
        clientCredentials:
          tokenUrl: https://learn.openapis.org/oauth/2.0/token
            # Only reading the board allow with delegated access
            board:read: Read the board
    **user2AppOauth**:
        authorizationCode:
          authorizationUrl: https://learn.openapis.org/oauth/2.0/auth
          tokenUrl: https://learn.openapis.org/oauth/2.0/token
          scopes:
            # Reads and writes permitted via authorization code flow
            board:read: Read the board
            board:write: Write to the board

Daí, se descreve como _Security Requirements_ separados:

info:
  title: Tic Tac Toe
  description: |
    This API allows writing down marks on a Tic Tac Toe board
    and requesting the state of the board or of individual squares.
  version: 1.0.0

paths:
  /board:
    get:
      security:
        app2AppOauth:
        - board:read
      ...
  /board/{row}/{column}:
    put:
      security:
        user2AppOauth:
        - board:read
        - board:write
      ...

### OpenID Connect

É um tipo de OAuth 2.0 mas se abstrai o processo de descoberta do endpoint.

components:
  securitySchemes:
    openIdConnect:
      type: openIdConnect
      openIdConnectUrl: https://learn.openapis.org/.well-known/openid-configuration

Não é necessário declarar os escopos do OpenAPI Document. Você define os escopos no endpoint de descoberta.

openapi: 3.1.0
info:
  title: Tic Tac Toe
  description: |
    This API allows writing down marks on a Tic Tac Toe board
    and requesting the state of the board or of individual squares.
  version: 1.0.0
security:
  openIdConnect:
    - board:read
    - board:write

## 4 - Conteúdo da Mensagem / Corpo

Campo _content_ é encontrado nos objetos resposta e nos objetos de requisição.Nesse item trataremos sobre as mensagens de retorno. Elas podem ser retornadas em diferentes formatos e pode-se usar wildcards.

content:
  application/json:
    ...
  text/html:
    ...
  text/*:
    ...

### O objeto _media type_

Contém a estrutura do conteúdo e também oferece exemplos de como usar.A estrutura é a abaixo:

content:
  application/json:
    schema:
      ...

### O objeto _schema

Define um tipo de dados que pode ser primitivo, lista, ou um objeto. Isso é definido no atributo _type_

- type (string): number, string, boolean, array ou object. Dependendo do tipo escolhido, são obrigatórios outros campos.

Tipo Integer

content:
  application/json:
    schema:
      type: integer
      minimum: 1
      maximum: 100

Tipo String

content:
  application/json:
    schema:
      type: string
      enum:
      - Alice
      - Bob
      - Carl

Tipo Array

O tipo de itens que está no array também é definido por um objeto _schema._

content:
  application/json:
    schema:
      type: array
      minItems: 1
      maxItems: 10
      items:
        type: integer

Tipo Object

Contém um atributo chamado _properties_ que lista as propriedades em um mapa, com um objeto _schema_ os definindo.

content:
  application/json:
    schema:
      type: object
      properties:
        productName:
          type: string
        productPrice:
          type: number

## 5 - Parâmetros e Payload da operação
Existem duas formas de enviar parâmetros para uma API e que podem ser descritas no OpenAPI: parâmetros e _request body (message payload)._

Parâmetros geralmente são usados para identificar um recurso, enquanto o payload da mensagem é usado para passar o conteúdo necessário para aquele recurso.

### Objeto _Parameter_

O atributo _parameters_ no _path item_ e no _operation_ é uma lista contendo objetos do tipo _parameter._ Se são descritos no _path_, portanto ele é compartilhado por todas as operações.

Cada objeto do tipo _parameter_ descreve um parâmetro que tem os campos abaixo como obrigatórios:

- in (string): local do parâmetro
- name(string): _Case sensitive_. _Deve ser único para cada local_

Campos opcionais:

- description (string): Usado para documentação e pode conter exemplos
- required (boolean): Se deve estar presente ou não. Padrão é falso

**Local dos parâmetros**

Os parâmetros podem ser colocados em diferentes locais, que é indicado pelo parâmetro in.  São três os mais comuns:

- path: É parte da URL. O parâmetro deve estar na URL com chaves
    
    Ex: `/users/{id}`
    

paths:
  /users/{id}:
    get:
      parameters:
      - name: id
        in: path
        required: true

- query: O parâmetro é concatenado na query como parte da operação da URL
    
    Ex: `/users?id=1234` 
    

paths:
  /users:
    get:
      parameters:
      - name: id
        in: query

- header: O parâmetro é enviado no header do HTTP. Os parâmetros nesse caso são case insensitive

**Tipos de parâmetros**

Os parâmetros podem ser definidos na maioria das vezes através do objeto _schema_ detalhado no conteúdo 4 desse resumo. Em casos mais avançados pode-se usar o campo _content_. Deve-se definir ou _schema_ ou _content._

parameters:
- name: id
  in: query
  schema:
    type: integer
    minimum: 1
    maximum: 100

**Controles de serialização dos parâmetros**

O campo _style_ define como um atributo é serializado e isso depende do tipo, portanto, existe uma matriz para melhor compreender.

- Tipos primitivos

|style:|`simple`|`form`|`label`|`matrix`|
|---|---|---|---|---|
||`1234`|`id=1234`|`.1234`|`;id=1234`|

- Listas

O campo _explode_ pode ser usado para separar cada item da lista em um parâmetro separado.

|tyle:|`simple`|`form`|`label`|`matrix`|
|---|---|---|---|---|
|with `explode=false`|`1,2,3`|`ids=1,2,3`|`.1.2.3`|`;ids=1,2,3`|
|with `explode=true`|`1,2,3`|`ids=1&ids=2&ids=3`|`.1.2.3`|`;ids=1;ids=2;ids=3`|

- Objetos

Exemplo com objeto que tem três atributos R, G,B.

|style:|`simple`|`form`|`label`|`matrix`|
|---|---|---|---|---|
|with `explode=false`|`R,1,G,2,B,3`|`color=R,1,G,2,B,3`|`.R.1.G.2.B.3`|`;color=R,1,G,2,B,3`|
|with `explode=true`|`R=1,G=2,B=3`|`R=1&G=2&B=3`|`.R=1.G=2.B=3`|`;R=1;G=2;B=3`|

### Objeto _Request Body_

Quando se vai atualizar um objeto os parâmetros geralmente identificam o objeto enquanto o conteúdo do corpo da mensagem contém os dados do objeto que serão atualizados.

O único atributo padrão é o _content_, que já foi descrito na seção 4.

paths:
  /board:
    put:
      requestBody:
        content:
          application/json:
            schema:
              type: integer
              minimum: 1
              maximum: 100

## 6 - Múltiplos arquivos / Quebrando OAD em partes

Como os arquivos de um OAD podem ficar muito grandes é conveniente quebrá-los em múltiplos arquivos para facilitar a leitura. Isso é feito no atributo components na raiz do objeto OpenAPI

A maioria dos objetos no OAD podem ser substituídos por uma referência a um _component._ Isso reduz o tamanho do arquivo e também facilita a manutenção.

Nem todos os objetos podem ser refernciados, apenas como: _schemas, responses, parameters._

Cada campo no objeto _componentes_ é um mapa valor para o objeto que será reusado, exemplos:

components:
  schemas:
    coordinate:
      type: integer
      minimum: 1
      maximum: 3
  parameters:
    rowParam:
      name: row
      in: path
      required: true

Dois componentes, acima, foram definidos. Um coordinate que é um componente do tipo _schema_ e rowParam que é um componente do tipo _parameter._

### Referenciando um componente genérico

Todo objeto que pode ser colocado dentro do objeto _components_ pode ser referenciado depois. Na prática uma referência é como referências do JSON e são associados da forma $ref, conforme exemplo abaixo

$ref: 'https://gigantic-server.com/schemas/Monster/schema.yaml'

$ref: './another_file.yaml#rowParam'

Um exemplo completo pode ser visto abaixo

components:
  schemas:
    coordinate:
      type: integer
      minimum: 1
      maximum: 3
  parameters:
    rowParam:
      name: row
      in: path
      required: true
      schema:
        $ref: "#/components/schemas/coordinate"
    columnParam:
      name: column
      in: path
      required: true
      schema:
        $ref: "#/components/schemas/coordinate"
paths:
  /board/{row}/{column}:
    parameters:
      - $ref: "#/components/parameters/rowParam"
      - $ref: "#/components/parameters/columnParam"

## 7 - Exemplos e documentações

Além de ser claro para uma máquina ler a OAD fornece documentação para humanos poderem ler.

### Campo _description_

Quase todos os objetos possuem esse campo. Pode ser usado para descrever o propósito além do entendimento que pode ser compreendido só em analisar o nome. Alguns atributos que geralmente tem uma descrição mais longa como _path, operation_, podem ter um atributo _summary_

paths:
  /audio/volume:
    put:
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: integer
              minimum: 0
              maximum: 11
              description:
                Current volume for all audio output.
                0 means no audio output (mute). 10 is the maximum value. 11 enables
                the overdrive system (danger!).
                When set to 0 all other audio settings have no effect.
              ...

**Grandes descrições**

Antes é importante tomar cuidado com caracteres especiais como # ou :, nesses casos é importante colocar o texto entre aspas.

Existem dois modos de se escrever grandes textos

- Modo literal (Usando Pipe |): Quebras de linhas no arquivo são preservados.

description: |
  This is a string
  in multiple lines.

  And an extra one.

Resultado:

This is a string
in multiple lines.

And an extra one.

- Modo Folded (Usando >): Quebras de linha são removidas e o texto é concatenado. Se quiser quebrar uma linha, deixar uma linha em branco.

description: >
  This is a string
  in multiple lines.

  And an extra one.

Resultado:

This is a string in multiple lines.
And an extra one.

### Sintaxes comuns para ter um texto

- Títulos: Usar #
    
    - # Nível 1
    - ## Nível 2
    - ### Nível 3
- Ênfase:
    
    - *Baixa*
    - **Alta**
    - ***Duas***
- Listas:
    
    - - Item 1
    - - Item 2
    -   - Item 2.1
- Código:
    
    - Dentro de uma linha 'código'
    - '''
        
        Um bloco de código
        
        '''
        
- Links:
    
    - [Texto] (URL)
    - ![Alt texto] (Imagem URL)

### Adicionando Exemplos

Alguns objetos podem declarar exemplos explícitos ao invés de tê-los na descrição. Isso faz com que um aplicativo possa executá-los / Mockup.

São dois atributos: _example_ e _examples._ Um para um único e o segundo para múltiplos. O tipo campo deve coincidir com o tipo do campo na qual o exemplo foi feito para.

schema:
  coordinate:
    type: integer
    minimum: 1
    maximum: 3
    example: 1

Já o _examples_ oferece também um _summary_ e uma _description,_ além do _value._

responses:
  "400":
    description: The provided parameters are incorrect
    content:
      text/html: # This is a Media Type Object
        schema:
          type: string
        examples:
          illegalCoordinates:
            value: "Illegal coordinates."
          notEmpty:
            value: "Square is not empty."
          invalidMark:
            value: "Invalid Mark (X or O)."

