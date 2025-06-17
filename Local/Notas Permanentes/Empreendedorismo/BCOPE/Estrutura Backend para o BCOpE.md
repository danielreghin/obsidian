---
tags: 
revisões: -1
criado: 
título_alternativo:
---
Deve existir um componente para cada módulo. Toda as regras de negócio, conexão com banco, filas, devem ser descritas nesse componente.

Estrutura de pastas:
	**lib**
		**common**: configuração de log e de outros atributos
		**features:** pasta por funcionalidade, sendo que cada contém:
			**data**: Objetos DTO, Models para transferência de dados
			**domain**: Regras de negócio
			**presentation**: Camada de exposição de serviços REST ou GRPC
		**server**: Classe main para a subida dos servidores
	**routes**
		Contém a exposição dos serviços REST do padrão dart_frog. A separação é feita por endpoints. 

![[Pasted image 20250211175703.png|700x426]]


Para cada feature, se deve ter uma estrutura de pastas da seguinte forma:
 **data**: 
	 Contém a conexão com os dados ou de entidades externas, independente da forma de acesso a esses dados
	 Pode ter um estrutura de dados do domínio, para que se possa facilitar a conversão e/ou chamadas
**domain**: 
	 Contém os Use Cases. É uma  implementação, genérica independente do formato de exposição , seja via eventos, serviços (REST ou GRPC). 
	 Ele pode ser de dois tipos: atômicos, que chamam as suas bases de dados e não têm regras de negócios de agregação ou transformação complexa; orquestrador, que possuem transformações, agregações e chamadas de outro use cases. Ou seja Se for dentro da mesma estrutura de pastas, ele pode chamar diretamente um database  Se precisar chamar regras de outras pastas, deve chamar outros use cases ou serviços rest.
	 
 **presentation**: 
	Contém  os controllers: A implementação dos serviços REST (GET,PUT,DELETE e etc). Nessa classe que se converte de JSON para um grupo de objetos que o backend entende e vice e versa.

## Comunicação Frontend para Backend e vice-versa

## Objetos e Modelos
Existem dois tipos de objetos de dados, chamados também de modelos: 

O primeiro é aquele que é gerado e manipulado no domínio do backend. Ao executar uma query esse objeto é populado.  Já o segundo é o objeto retornado na camada de apresentação. Ele é definido no componente common. Existe um objeto para REST e outro para serviços GRPC

Os objetos abaixo são armazenados na estrutura de backend
	*Objeto*Model: Domínio do backend e é populado ao executar uma query.
	
Já os objetos abaixo são armazenados no Common e compartilhados entre backend e frontend.
	*Objeto*ProtoResponse: Encapsula um retorno de uma chamada GRPC em formato protobuf
	*Objeto*ProtoRequest: Encapsula uma objeto de uma chamada GRPC em formato protobuf.
	*Objeto*ProtoModel: Retorno ou chamada de serviços GRPC em formato profobuf
	*Objeto*RestResponse: Encapsula um retorno de uma chamada REST em formato json
	*Objeto*RestRequest: Encapsula uma objeto de uma chamada REST em formato json.
	*Objeto*RestModel: Retorno ou chamada de serviços REST em formato json
		
Tenho que ter um objeto Model em data que é o objeto do backend (interno) e a depender de como o objeto é exposto há a conversão na última camada para o objeto externo.

## Lançamentos de exceções

### REST
Dentro de um serviço Rest eu estava usando um Either como opção de retorno
  
```
  Future<Either<RestFailure, Map<String, dynamic>>> parseBody({
       return Right(json);
       ou
       return Left(e.toFailure());
```

Porém, tomei a decisão de dentro do backend todos os erros serão propagados via execção para que não haja perda de rastreamento de problemas e simplificando o mapa mental.

No Frontend qualquer erro que é lançado é feito com o
	DioRemoteServiceException, vou transformar para outra exceção para ser melhor organizado e eventualmente guardar em algum lugar.

SERVICE - Facilitar a criação do DIO no frontend, para que não haja erro de conversão de objetos. Há duplicidade de classe, mas que faz sentido.

### GRPC
Quando o serviço é um gRPC as exceções lançadas são padrões, GRPC com código "unknown" e a mensagem capturada da exceções. Portanto, na camada Service vou capturar as exceções e traduzir para o código correto.

`Future<PessoaProtoModel> getPessoa(ServiceCall call, GetPessoaProtoRequest request) async {`
    `if (request.pessoaId <= 0) {`
      `throw GrpcError.invalidArgument('O ID da pessoa deve ser maior que zero.');`
    `}`
    `final pessoa = await buscarPessoaPorId(request.pessoaId);`
    `if (pessoa == null) {`
      `throw GrpcError.notFound('Pessoa com ID ${request.pessoaId} não encontrada.');`
    `}`
    `return pessoa.toPessoaProtoModel();`
  `}`

## Lançamento de erros GRPC e REST

Lançamento de erros:
- 400 (BadRequestException): Quando usuário enviou dados inválidos para a aplicação
- 401 (UnauthorizedException): Quando algum recurso não pode ser acessado por não estar autorizado.
- 404 (EntityNotFoundException): Quando usuário enviou dados válidos, mas o recurso não foi encontrado
- 422 (EntityNotProcessedException): Quando usuário enviou dados válidos, mas não foi possível executar o código por alguma regra de negócio.
		

Erros mais comuns:
1. **`422 Unprocessable Entity`**:
	- Este código é usado quando os dados enviados pelo cliente são válidos, mas não podem ser processados devido a restrições de negócio. 
	- Validações de negócio falharam (ex.: um campo obrigatório está ausente ou um valor não atende a uma regra de negócio).
	- Os dados enviados pelo cliente são válidos, mas não podem ser processados devido a restrições específicas (ex.: tentativa de criar um recurso que já existe).
- 500
	- Um erro de query é um problema interno e deve ser tratado como tal, indicando que o servidor encontrou uma condição inesperada.

| **HTTP Status Code** | **Descrição HTTP**    | **gRPC Error Code**             | **Descrição gRPC**                                                         |
| -------------------- | --------------------- | ------------------------------- | -------------------------------------------------------------------------- |
| `200`                | OK                    | `StatusCode.ok`                 | A operação foi concluída com sucesso.                                      |
| `400`                | Bad Request           | `StatusCode.invalidArgument`    | O cliente forneceu um argumento inválido.                                  |
| `401`                | Unauthorized          | `StatusCode.unauthenticated`    | O cliente não possui credenciais de autenticação válidas.                  |
| `403`                | Forbidden             | `StatusCode.permissionDenied`   | O cliente não tem permissão para executar a operação.                      |
| `404`                | Not Found             | `StatusCode.notFound`           | A entidade solicitada não foi encontrada.                                  |
| `409`                | Conflict              | `StatusCode.aborted`            | A operação foi abortada devido a um conflito, como falhas de concorrência. |
| `412`                | Precondition Failed   | `StatusCode.failedPrecondition` | O estado do sistema não atende aos pré-requisitos para a operação.         |
| `422`                | Unprocessable Entity  | `StatusCode.outOfRange`         | A operação foi tentada fora do intervalo válido.                           |
| `429`                | Too Many Requests     | `StatusCode.resourceExhausted`  | Algum recurso foi esgotado, como uma cota de usuário ou espaço em disco.   |
| `500`                | Internal Server Error | `StatusCode.internal`           | Um erro interno ocorreu no servidor.                                       |
| `501`                | Not Implemented       | `StatusCode.unimplemented`      | A operação não é suportada ou não está habilitada no serviço.              |
| `503`                | Service Unavailable   | `StatusCode.unavailable`        | O serviço está indisponível, geralmente devido a uma condição transitória. |
| `504`                | Gateway Timeout       | `StatusCode.deadlineExceeded`   | O prazo expirou antes que a operação pudesse ser concluída.                |
| `507`                | Insufficient Storage  | `StatusCode.dataLoss`           | Perda ou corrupção de dados irrecuperável.                                 |


# Construção de Queries
Em um dos modelos, as colunas são armazenadas no JSON
Dessa forma, fica flexível para mudar o nome das tabelas e colunas e dessa forma, o "de para" no JSON também é facilitado.

![[Pasted image 20250131133953.png]]

O outro modelo é facilitar capturar a query e jogar em alguma aplicação para poder executar e testar rapidamente.
![[Pasted image 20250131134039.png]]

## Nomenclatura
Para o GRPC a nomenclatura utilizada é essa: [Guia de projeto da API  |  Cloud API Design Guide  |  Google Cloud](https://cloud.google.com/apis/design?hl=pt-br)
