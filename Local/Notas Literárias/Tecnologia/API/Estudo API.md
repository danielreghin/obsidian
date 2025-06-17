---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-06-04
título_inglês: 
ano_publicação: 
autor: 
qtd_páginas: 
ISBN:
---
# Conteúdo

# 1- Convenções para Path

A organização de nomes de uma URI traz clareza aos recursos disponibilizados
Se pode dividir o authority para representar subdivisões como multi tentant:
Recomendado até dois subníveis por recursos
## Versionamento

As versões major devem ser incluídas na URL, diferente das minors e patch versions.
A documentação devem conter o detalhamento das versões das APIs, conforme:

{MAJOR}.{MINOR}.{PATCH}

- **MAJOR** version when **incompatible** or **breaking** API changes are made,
- **MINOR** version when functionality is added in a backwards-compatible manner, and
- **PATCH** version when backwards-compatible bug fixes are made.

Backwards compatible changes include:

- Addition of a new field (non-mandatory) to a representation
- Addition of a new operation
- Addition or removal of HATEOAS links
- Additional support of a new media type (e.g. Accept: application/pdf)

The following changes are NOT considered backwards compatible:

- Removal of fields from representations
- Changes of field data types (e.g. string to boolean)
- Removal of an operation
- Removal of media type support
- New or tightened API security definitions

## Design Patterns

## **Canonical business resource pattern**

- The business resource represent the nouns of a system, such as ‘applications’ and ‘applicants’.
Format:
/{version}/{resource}/{resourceId}
Example:
GET /v1/subscriptions/12B34C

## **Parameter-driven filtering**

- A decoupled convention-over-configuration approach to filtering & field selection based on the business-information-resource model

Format:
/{version}/{resource}/{resourceId}?fields={name}/{version}/{resource}?{fieldName}={value}&fields={name1,name2}

Example:
GET /v1/claims?customerId=12B34C&fields=claimId,name

## **Command affordance pattern**

- A pattern to afford explicit state transitions or provide abstract functionality in the context of a business resource, or capability domain. The action is expressed as a verb that acts in the context of a resource instance or resource collection.

Format:
/{version}/{resource}/{resourceId}/{affordance-name}/{version}/{resource}/{affordance-name}

Example:
https://api.myorg.com/membership/v1/applications/12345/cancel

## **Versions pattern**

- Where versioned resource instances are maintained, such as document versions
- Typically the version-id is an incrementing integer
- GET request on the base resource always returns the latest version

Format:
/{api-version}/{resource}/{Id}/versions/{versionId}

Examples:
GET /v1/activity-reports/12345/versions/3GET /v1/activity-reports/12345           --> Latest

## **Job to be done (JTBD) pattern**

- Some specific process or regulatory obligation related to a business resource.

Format:
/{version}/{resource}/{job name}/{jobId}

Example:
POST /v1/consignments/receivals/987654

# 4 - Filtros

### Definição de campos de retorno

Possível descrever os campos a serem retornados

`GET /v1/subscriptions?subscriberId=12B34C&fields=subscriptionId,name`

Possível solicitar campos adicionais, além dos retornados por padrão.

`GET /applicants/12345?include=familyMembers,memberReferals`

### Ordenação

Listar os campos a serem ordenados com o atributo sort. Se o campo for ter a ordenação decrescente deve-se colocar um sinal de menor

?sort=name,lastModified
?sort=-name

### Paginação

# 3 - Payloads

## Ordem dos atributos

Os atributos devem ser organizados para facilitar a leitura.

- Atributos primitivos (int, string e etc)
- Objetos
- Collections

### Taxonomia para os Ids

Para evitar a ambiguidade os nomes dos recursos são declarados em cada um dos campos de ID.

- accountId
- customerId

### Retorno - Estrutura de Dados

Os dados devem ser estruturados da seguinte forma:

- data: Contém a representação de um objeto ou uma lista de objetos para o recurso consultado.
- pagination: Retornado quando o conteúdo das informação data for uma lista.
- meta: Contém informações referentes aos dados ou à requisição consultada como: links, nível de autorização e outros.
- links: Contém links para recursos ou operações desses recursos.
- messages:
- risk:
- errors:

Reserved top-level properties in this scheme might include: _“data”, “meta”, “links”_ (and/or _“_links”_)_, “messages”, “risk”_ (Open Banking) and _“errors”._

Exemplo:

POST /v1/applications{   
    "data": {
       "familyName": "SMITH",
       "givenName": "Jane",
       "birthDate": "1992-01-01"
    },
    "metadata": {
       "classification": "sensitive",
       "consent": "538d9bb1–95c9–4ceb-864c-80887776573"
    }
}

Os erros devem conter informações suficientes para que seja possível resolver um potencial problema na aplicação. Quando detalhes técnicos forem apresentados, identificadores e etc, devem ser mascarados. Garantir que dados pessoais não sejam retornados.

{
    "errors": [{
        "errorId": "85024bfe-a602-7b3c-82be-301e7d0bd0a6",
        "origin": "myDomain.myApp",
        "code": "EMM-7b3c82be",
        "message": "Data validation error",
        "detail": "Future date not allowed",
        "source": "profile.birthDate"
    }]
}

# 7 - Padrões de Erro

## GET

Ordenação não suportada **_400 Bad Request_**

[API Bites — Request and Response Protocols | by TRGoodwill | API Central | Medium](https://medium.com/@trgoodwill/1f3a4f34cecf)

## 0 - Fontes

CONTINUAR A CONSOLIDAR COM BASE EM:

[Writing API Design Standards. An 8-step guide to tailoring API design… | by TRGoodwill | API Central | Medium](https://medium.com/@trgoodwill/writing-api-design-standards-84cb7cbb3fd7)

Existem vários padrões de nomenclatura.

A Google tem alguns padrões

[https://cloud.google.com/apis/design/resource_names?hl=pt-br](https://cloud.google.com/apis/design/resource_names?hl=pt-br)

A Microsoft tem padrões de Design de API

[https://github.com/microsoft/api-guidelines/blob/vNext/azure/Guidelines.md](https://github.com/microsoft/api-guidelines/blob/vNext/azure/Guidelines.md)

Um bom exemplo está no uso nesse artigo:

[REST API Naming Conventions and Best Practices | by Mehmet BAZ | Medium](https://medium.com/@mehmetbaz/rest-api-naming-conventions-and-best-practices-31635ee11c0d)

[Writing API Design Standards. An 8-step guide to tailoring API design… | by TRGoodwill | API Central | Medium](https://medium.com/@trgoodwill/writing-api-design-standards-84cb7cbb3fd7)

Menos pior: [Microservices Patterns (oreilly.com)](https://learning.oreilly.com/library/view/microservices-patterns/9781617294549/)

Outros podem ser definidos por áreas.

Padrões adotados na definição de elementos:

|**Elemento**|**Padrão**|**Exemplo**|
|---|---|---|
|path|**KebabCase**|/**credit-cards**|
|path parameter|**camelCase**|/credit-cards/{**creditCardId**}|
|header parameter|**Hyphenated-Pascal-Case**|**Accept** / **Cache-Control** / **Content-Type**|
|query parameter|**camelCase**|/credit-cards/{creditCardId}**?fullName=Jhon Mayden**|
|operationId|**camelCase**|**postInitiate**|

Padrões adotados na definição de elementos:

|**Elemento**|**Padrão**|**Exemplo**|
|---|---|---|
|schema element|**PascalCase**|InitiateCreditCardFacilityRequest|
|schema object properties element|**camelCase**|errors|
|parameters name element|**camelCase**|creditCardId|

# 2 - Taxonomia

# Recursos

### Nomenclatura

Devem ser usados substantivos e não verbos. Usar plural quando o recurso representar uma coleção.

- Correto:
    
    - /users (GET — list all users, POST — create a new user)
    - /users/{userId} (GET — get user details, PUT — update user details, DELETE — delete user)
- Incorreto:
    
    - /getUsers
    - /user

Em cenários onde se se representam controladores se pode usar uma ação através de um verbo:

- /users/{id-user}/export-bacen

Onde o objeto representar um único documento, descrevê-lo no singular

- /users/{id-user}/profile
- `https://api.myorg.com/membership/v1/applications/12345/cancel`

### Formato

- Nome de Recursos:
    
    - Kebab Case
        
        - /credit-accounts
        - /credit-cards/{id}/account-balance/

# Query Parameters

Se o campo representar um array, deve-se usá-lo no plural

- ?bankingAccount=xxx,xxxx,xxxx

### Formato

- Camel Case
    
    - ?clientName=’João’
    - ?filterPerPage=10

# Payloads

### Formato

- Camel Case
    
    - clientName:’XXXXXX’
    - clientAddress:’XXXXXXX’

# 5 - Segurança

Sempre trafegar atributos identificadores de forma criptografada nas URLs

- Correto:
    
    - GET `/v1/applicants/538d9bb1`
- Incorreto:
    
    - GET `/v1/applicants/123`

